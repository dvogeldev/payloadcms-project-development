# PayloadCMS Backend Schema Design Example

This is an example of what a PayloadCMS schema design document might look like.

## Collections

### Users
- email (email, required)
- password (password, required)
- role (select: ['admin', 'editor', 'author'], default: 'author')
- profile (relationship to Profiles collection)

### Posts
- title (text, required)
- slug (text, required, unique)
- content (richText)
- author (relationship to Users)
- categories (relationship to Categories, hasMany)
- status (select: ['draft', 'published', 'scheduled'], default: 'draft')
- publishDate (date)

### Pages
- title (text, required)
- slug (text, required, unique)
- content (blocks)
- template (select: ['default', 'landing', 'blog'], default: 'default')

### Media
- (Uses Payload's built-in Media collection)

### Categories
- name (text, required)
- slug (text, required, unique)

## Globals

### Header
- siteName (text)
- logo (upload to Media)
- navItems (blocks)

### Footer
- copyrightText (text)
- socialLinks (blocks)

## Access Control Rules

- Users can only edit their own profile
- Admins can manage all collections
- Editors can publish and edit all Posts and Pages
- Authors can edit only their own Posts
- Public can read published Posts and Pages

## SEO/Search Configuration

- Automatic slug generation from title
- SEO meta tags component for Posts and Pages
- Full-text search enabled on Post content
- Sitemap generation enabled