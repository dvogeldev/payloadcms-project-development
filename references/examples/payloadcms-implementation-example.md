# PayloadCMS Backend Implementation Example

This is an example of what a PayloadCMS backend implementation might look like.

## payload.config.ts

```typescript
import { buildConfig } from 'payload'
import { Users } from './collections/Users'
import { Posts } from './collections/Posts'
import { Pages } from './collections/Pages'
import { Media } from './collections/Media'
import { Categories } from './collections/Categories'
import { Header } from './globals/Header'
import { Footer } from './globals/Footer'

export default buildConfig({
  serverURL: process.env.PAYLOAD_PUBLIC_SERVER_URL || 'http://localhost:3000',
  collections: [Users, Posts, Pages, Media, Categories],
  globals: [Header, Footer],
  typescript: {
    outputFile: 'src/payload-types.ts'
  },
  graphQL: {
    schemaOutputFile: 'src/generated-schema.graphql'
  },
  plugins: [
    // SEO plugin
    // search plugin
    // form plugin
  ],
  access: {
    // Global access rules if needed
  },
  hooks: {
    // Global hooks if needed
  }
})
```

## Collections Example: Posts Collection

```typescript
import { CollectionConfig } from 'payload'

export const Posts: CollectionConfig = {
  slug: 'posts',
  admin: {
    useAsTitle: 'title',
    defaultColumns: ['title', 'author', 'status', 'publishDate']
  },
  access: {
    read: () => true, // Anyone can read published posts
    read: ({ req: { user } }) => {
      if (user?.role === 'admin' || user?.role === 'editor') return true
      // Authors can only read their own posts
      return user ? { author: { equals: user.id } } : false
    },
    update: ({ req: { user } }) => {
      if (user?.role === 'admin' || user?.role === 'editor') return true
      // Authors can only update their own posts
      return user ? { author: { equals: user.id } } : false
    },
    delete: ({ req: { user } }) => {
      if (user?.role === 'admin' || user?.role === 'editor') return true
      // Authors can only delete their own posts
      return user ? { author: { equals: user.id } } : false
    },
    create: ({ req: { user } }) => {
      if (user?.role === 'admin' || user?.role === 'editor') return true
      // Authors can create posts
      return user ? { author: { equals: user.id } } : false
    }
  },
  fields: [
    {
      name: 'title',
      type: 'text',
      required: true
    },
    {
      name: 'slug',
      type: 'text',
      required: true,
      admin: {
        position: 'sidebar'
      }
    },
    {
      name: 'author',
      type: 'relationship',
      relationTo: 'users',
      required: true
    },
    {
      name: 'content',
      type: 'richText',
      required: true
    },
    {
      name: 'categories',
      type: 'relationship',
      relationTo: 'categories',
      hasMany: true
    },
    {
      name: 'status',
      type: 'select',
      options: [
        { label: 'Draft', value: 'draft' },
        { label: 'Published', value: 'published' },
        { label: 'Scheduled', value: 'scheduled' }
      ],
      defaultValue: 'draft'
    },
    {
      name: 'publishDate',
      type: 'date'
    }
  ]
}
```

## Hooks Example

```typescript
import type { CollectionAfterChangeHook } from 'payload'

export const resetSearchIndex: CollectionAfterChangeHook = async ({ doc, req: { payload } }) => {
  // Reset search index when post is updated
  if (payload.collections.posts) {
    await payload.update({
      collection: 'posts',
      id: doc.id,
      data: {},
      // This would trigger reindexing in a real implementation
    })
  }
}
```