# Journey - Love Memories Application - Claude Context

## 🎯 Project Overview
**Journey** is a romantic love journey application built with Laravel 12, designed to capture and celebrate special moments in a relationship. This is a personal project to create, manage, and cherish love keepsakes, memories, countdown and milestones.

**Repository:** https://github.com/hkai7706/journey  
**Project Status:** Active Development  
**Purpose:** Track love story, special moments, and relationship milestones

### Core Features
- ✨ Create and manage love keepsakes with photos
- 💝 Take love quizzes and surveys
- 📸 View photo galleries (4 different viewing styles)
- 📅 Track special moments with timeline and calendar views
- 💭 Add text to memory wall
- ⏰ Countdown to next anniversary
- 📤 Export memories and data

---
  
## 🛠️ Tech Stack

### Backend
- **Framework:** Laravel 12.x
- **PHP Version:** 8.2+ (minimum 8.1)
- **Database:** 
  - **Local Development:** MySQL
  - **Production:** PostgreSQL (Railway)
- **Package Manager:** Composer
- **Email Service:** MailerSend API

### Frontend
- **Template Engine:** Blade Templates
- **JavaScript:** Vanilla JavaScript (ES6+)
- **CSS:** Custom CSS with romantic pink theme
- **Build Tool:** Vite
- **Fonts:** Handwritten fonts for dates and romantic touches

### Deployment & Hosting
- **Free Hosting:** Byethost (free tier)
- **Production Platform:** Railway
- **Storage:** Base64 encoded images in database (Railway compatibility)
- **Version Control:** Git + GitHub

---

## 📁 Project Structure

```
journey/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── KeepsakeController.php      # Keepsake CRUD operations
│   │   │   ├── MemoryController.php        # Memory management
│   │   │   └── LovesurveyController.php    # Love survey handling
│   │   └── Middleware/
│   ├── Models/
│   │   ├── Keepsake.php                    # Keepsake model
│   │   └── Memory.php                      # Memory model
│   ├── Mail/
│   │   └── SurveySubmitted.php             # Email notification for surveys
│   └── Providers/
├── bootstrap/                              # Framework bootstrap files
├── config/                                 # Configuration files
├── database/
│   ├── migrations/                        # Database migrations
|   |   ├── 2025_11_15_044812_create_memories_table.php    # memories table
|   |   ├── 2025_11_18_002500_create_questions_table.php   #question table
|   |   └── 2025_12_15_081448_create_keepsake_table.php     # keepsake table        
│   │  
│   ├── seeders/                           # Database seeders
│   └── factories/                         # Model factories for testing
├── public/                                # Public assets
│   ├── css/
|   |   ├── main.css                       # Main css file 
|   |   └── love-quiz.css                  # love-quiz css file 
|   |    
│   ├── js/
|   |   ├── love-quiz.js                   # Main js file 
|   |   └── main.js                        # Love quiz js file 
|   |
│   └── images/                            # Main image location
|         
├── resources/
│   ├── views/
│   │   ├── components/
|   |   |   ├──navbar.blade.php            # navbar page 
│   │   │   └── footer.blade.php           # footer page
│   │   ├── emails/
│   │   │   └── survey-submitted.blade.php # survey-submit page
│   │   ├── keepsakes/
│   │   │   └── index.blade.php            # keepsake page
│   │   ├── memories/
│   │   │   └── index.blade.php            # Main landing page
|   |   ├── pages
│   │   |   └──gallery.blade.php           # Photo gallery page
|   |   ├── quiz
│   │   |   └──index.blade.php             # quiz page
|   |   ├──survey-complete.blade.php       # survey-complete
│   │   └── love-survey.blade.php          # Love survey form
│   ├── css/                               # CSS source files
│   └── js/                                # JavaScript source files
├── routes/
│   ├── web.php                            # Web routes
│   ├── api.php                            # API routes (if needed)
│   └── console.php                        # Console routes
├── storage/                               # Storage for logs, cache
├── tests/                                 # PHPUnit tests
├── .env.example                           # Environment template
├── composer.json                          # PHP dependencies
├── package.json                           # Node.js dependencies
└── vite.config.js                         # Vite build configuration
```

---

## 🎨 Design & Styling Guidelines

### Color Palette (Romantic Pink Theme)
- **Primary Pink:** `#FF1493` (Deep Pink) - Main CTAs, headers
- **Secondary Pink:** `#FF69B4` (Hot Pink) - Accents, hover states
- **Light Pink:** `#FFB6C1` - Backgrounds, soft touches
- **White/Cream:** `#FFF5F5` - Content backgrounds
- **Text Dark:** `#333333` - Primary text

### Responsive Design Principles
- **Mobile-First Approach:** Always design for mobile, then scale up
- **Use `clamp()` for responsive sizing:** 
  ```css
  font-size: clamp(1rem, 2vw, 1.5rem);
  padding: clamp(1rem, 3vw, 2rem);
  ```
- **Breakpoints:**
  - Mobile: < 768px
  - Tablet: 768px - 1024px
  - Desktop: > 1024px

### Image Optimization
- **Always use `loading="lazy"`** for lazy loading
- **Use `decoding="async"`** for better performance
- **Compress images to 75% quality** before upload
- **Storage Format:** Base64 encoded in database (for Railway)
- **Polaroid-style photo frames** for romantic aesthetic

### Typography
- **Handwritten fonts** for dates and romantic text
- **Clean sans-serif** for body content
- **Headers:** Romantic, elegant fonts

### Animation Guidelines
- **Target 60fps** for smooth animations
- **Reduce animations on mobile** for performance
- **Use CSS transforms** over position changes
- **Add `prefers-reduced-motion` support** for accessibility

---

## 🗄️ Database Schema

### Primary Table: `love_story`
Key fields expected:
- `id` - Primary key
- `title` - Memory/Keepsake title
- `description` - Detailed description
- `date` - Date of the memory
- `image` - Base64 encoded image data
- `type` - Type of memory (keepsake, moment, etc.)
- `created_at` / `updated_at` - Timestamps

### Storage Strategy
- **Images:** Base64 encoded strings stored in database
- **Reason:** Railway compatibility, no need for file storage
- **Alternative:** Consider `php artisan storage:link` for local file storage if needed

---

## 💻 Coding Standards & Best Practices

### Laravel Conventions
- **PSR-12 Coding Style:** Strictly follow PHP standards
- **Eloquent ORM:** Use Eloquent instead of raw queries
- **Type Hints:** Always use type hints for parameters and return types
- **Naming Conventions:**
  - Models: Singular PascalCase (e.g., `Keepsake`, `Memory`)
  - Controllers: PascalCase + `Controller` (e.g., `KeepsakeController`)
  - Migrations: snake_case descriptive (e.g., `create_keepsakes_table`)
  - Routes: kebab-case (e.g., `/love-survey`, `/keepsakes`)

### Code Quality
- **Clean Code:** Write self-documenting code with clear variable names
- **Comments:** Add comments for complex logic only
- **DRY Principle:** Don't Repeat Yourself - extract reusable logic
- **Single Responsibility:** Each class/method should do one thing well

### Blade Templates
- **Use Blade Components** for reusable UI elements
- **Keep logic minimal** in views - business logic belongs in controllers
- **Use `@` directives** (`@if`, `@foreach`, `@auth`, `@csrf`)

### JavaScript Best Practices
- **ES6+ syntax** (arrow functions, const/let, template literals)
- **No jQuery** - Use vanilla JavaScript
- **Mobile Performance:** Optimize for mobile devices
- **Event Delegation:** Use for dynamic content

### Accessibility (ARIA & Keyboard Navigation)
- **ARIA labels** for screen readers
- **Keyboard navigation** support (`tabindex`, focus states)
- **Alt text** for all images
- **Semantic HTML** (use proper heading hierarchy)

---

## ⚙️ Environment Configuration

### Local Development (.env)
```env
APP_NAME=Journey
APP_ENV=local
APP_KEY=base64:... # Generate with: php artisan key:generate
APP_DEBUG=true
APP_URL=http://localhost

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=journey
DB_USERNAME=root
DB_PASSWORD=

# MailerSend Configuration
MAIL_SCHEME=null 
MAIL_HOST=127.0.0.1 
MAIL_PORT=2525 
MAIL_USERNAME=null 
MAIL_PASSWORD=null 
MAIL_FROM_NAME="${APP_NAME}" 
MAIL_MAILER=mailersend 
MAIL_FROM_ADDRESS=noreply@test-p7kx4xw963eg9yjr.mlsender.net 
MAIL_FROM_NAME="love survey V2"
MAILERSEND_API_KEY=mlsn.4e0cd21ef12f75a3b5c900464d3f23071c6db0d91d895fcf8c4a5ff04b7f4b51
SURVEY_RECIPIENT_EMAIL=hkai7706@gmail.com
```

### Production (Railway - PostgreSQL)
```env
APP_ENV=production
APP_DEBUG=false
APP_URL=https://your-railway-app.railway.app

DB_CONNECTION=pgsql
DB_HOST=your-railway-db-host
DB_PORT=5432
DB_DATABASE=railway
DB_USERNAME=postgres
DB_PASSWORD=your_railway_password

# All files must be committed to Git for Railway
```

### Important Notes
- **DO NOT commit `.env` to GitHub** (it's in `.gitignore`)
- **Railway requires all project files** in Git repository
- **Use environment variables** for sensitive data

---

## 🚀 Common Development Commands

### Initial Setup
```bash
# Clone the repository
git clone https://github.com/hkai7706/journey.git
cd journey

# Install dependencies
composer install
npm install

# Setup environment
cp .env.example .env
php artisan key:generate

# Setup database
php artisan migrate
php artisan db:seed  # Optional: seed test data

# Link storage (if using file storage)
php artisan storage:link

# Start development servers
php artisan serve        # Backend (http://localhost:8000)
npm run dev             # Frontend (Vite hot reload)
```

### Daily Development
```bash
# Create new migration
php artisan make:migration create_keepsakes_table

# Create model with migration
php artisan make:model Keepsake -m

# Create controller
php artisan make:controller KeepsakeController --resource

# Run migrations
php artisan migrate

# Rollback last migration
php artisan migrate:rollback

# Fresh database (caution: deletes all data)
php artisan migrate:fresh --seed

# Clear caches
php artisan cache:clear
php artisan config:clear
php artisan view:clear
php artisan route:clear

# Or clear all at once
php artisan optimize:clear
```

### Frontend Build
```bash
# Development with hot reload
npm run dev

# Production build
npm run build

# Watch for changes
npm run watch
```

### Testing
```bash
# Run all tests
php artisan test

# Run specific test
php artisan test --filter=KeepsakeTest
```

---

## 📦 Current Features & Status

### ✅ Implemented Features
- [x] **Love Survey System**
  - Form submission with validation
  - Email notifications via MailerSend API
  - Survey results storage
  
- [x] **Keepsakes/Memories CRUD**
  - Create, Read, Update, Delete operations
  - Image upload with Base64 encoding
  - Date and description tracking
  
- [x] **Photo Gallery**
  - 4 different viewing styles (grid, masonry, slideshow, polaroid)
  - Lazy loading for performance
  - Responsive design
  
- [x] **Timeline View**
  - Chronological display of memories
  - Interactive timeline navigation
  
- [x] **Calendar View**
  - Monthly calendar with memory markers
  - Date-based memory filtering
  
- [x] **Export Functionality**
  - Export memories to file formats
  - Proper headers for downloads

### 🚧 In Progress / Planned Features
- [ ] **Swipe Gestures for Gallery** (mobile enhancement)
- [ ] **Gallery-Keepsake Integration** (connect gallery to keepsakes database)
- [ ] **Photo Upload UI Improvements** (drag-and-drop, preview)
- [ ] **Railway Deployment Optimization**
- [ ] **Memory Wall Feature** (text-based memory sharing)
- [ ] **Anniversary Countdown Widget**
- [ ] **Search and Filter Memories**
- [ ] **Tags/Categories for Memories**
- [ ] **Share Memories** (generate shareable links)

---

## ⚡ Performance Optimization Rules

### Image Optimization
1. **Compress images to 75% quality** before uploading
2. **Use `loading="lazy"`** on all `<img>` tags
3. **Use `decoding="async"`** for better rendering
4. **Base64 encoding** for database storage (Railway requirement)

### Frontend Performance
- **Minimize DOM manipulations** - batch updates when possible
- **Use CSS transforms** for animations (hardware accelerated)
- **Debounce/throttle** scroll and resize events
- **Reduce animations on mobile** - detect device and simplify
- **Lazy load images** below the fold
- **Minify CSS and JS** in production (`npm run build`)

### Backend Performance
- **Eager loading** for Eloquent relationships to avoid N+1 queries
- **Cache frequently accessed data** (config, routes)
- **Database indexing** on frequently queried columns (dates, IDs)
- **Optimize database queries** - use `select()` to limit columns

### Mobile-Specific
- **Touch-optimized buttons** (minimum 44x44px tap targets)
- **Reduce animation complexity** on mobile devices
- **Test on real devices**, not just browser emulators
- **Optimize for 3G connections**

---

## 🐛 Common Issues & Solutions

### Issue 1: Export API Not Working
**Problem:** Downloaded file is corrupted or not downloading  
**Solution:** 
```php
// Ensure proper headers in controller
return response()->download($filePath, $filename, [
    'Content-Type' => 'application/octet-stream',
    'Content-Disposition' => 'attachment; filename="' . $filename . '"'
]);
```

### Issue 2: Railway Deployment Failures
**Problem:** Missing files or environment issues  
**Solution:**
- Ensure ALL files are committed to Git (Railway pulls from Git)
- Check `.gitignore` isn't excluding necessary files
- Verify environment variables are set in Railway dashboard
- Use PostgreSQL syntax (not MySQL) for production queries

### Issue 3: Images Not Displaying
**Problem:** Images broken or not loading  
**Solution:**
- Check Base64 encoding is correct: `data:image/jpeg;base64,{encoded_string}`
- Verify image MIME type matches actual image format
- Ensure database column is `TEXT` or `LONGTEXT` for large images
- Compress images before encoding (max 2MB recommended)

### Issue 4: Animations Lagging on Mobile
**Problem:** Choppy animations, poor performance  
**Solution:**
- Use CSS `transform` and `opacity` (GPU accelerated)
- Add `will-change` property cautiously
- Reduce animation complexity for mobile devices
- Use `@media (prefers-reduced-motion)` for accessibility

### Issue 5: localStorage/sessionStorage Not Working
**Problem:** Storage APIs failing in artifacts or Railway  
**Solution:**
- **DO NOT use localStorage or sessionStorage** in Claude artifacts (not supported)
- Use JavaScript variables or React state instead
- For Railway: use database or server-side sessions

---

## 🎯 Claude AI Helper Preferences

### When Helping with Code
- ✅ **Provide complete, working code** (not pseudocode)
- ✅ **Include file paths** and where code should be placed
- ✅ **Add clear explanations** before code blocks
- ✅ **Follow Laravel 12+ best practices**
- ✅ **Use the romantic/cute aesthetic** for UI suggestions
- ✅ **Optimize for mobile** - always consider responsive design
- ✅ **Include proper error handling** and validation
- ✅ **Add accessibility features** (ARIA, keyboard nav)

### Code Generation Preferences
- Use **Eloquent ORM** over raw SQL
- Use **Blade components** for reusable UI
- Use **Resource Controllers** for CRUD operations
- Use **Form Request Validation** for complex validation
- Use **CSS `clamp()`** for responsive typography
- Use **Type hints** on all methods
- Add **PHPDoc comments** for complex logic

### Response Style
- Keep responses **concise and actionable**
- Provide **step-by-step instructions** when needed
- Suggest **performance optimizations** when relevant
- Mention **potential issues** and how to avoid them
- Include **testing recommendations**

---

## 📚 Quick Reference

### Laravel Eloquent Relationships
```php
// One to Many (e.g., User has many Keepsakes)
public function keepsakes() {
    return $this->hasMany(Keepsake::class);
}

// Belongs To (e.g., Keepsake belongs to User)
public function user() {
    return $this->belongsTo(User::class);
}

// Many to Many (e.g., Memories and Tags)
public function tags() {
    return $this->belongsToMany(Tag::class);
}
```

### Validation Examples
```php
// In Controller or Form Request
$validated = $request->validate([
    'title' => 'required|max:255',
    'description' => 'required|max:1000',
    'date' => 'required|date',
    'image' => 'required|image|max:2048', // 2MB max
]);
```

### Blade Component Example
```blade
{{-- resources/views/components/memory-card.blade.php --}}
<div class="memory-card">
    <h3>{{ $title }}</h3>
    <p>{{ $description }}</p>
    <span class="date">{{ $date }}</span>
</div>

{{-- Usage --}}
<x-memory-card 
    title="First Date" 
    description="The day we met" 
    date="2024-01-01" 
/>
```

### Responsive CSS with clamp()
```css
/* Responsive font sizing */
.title {
    font-size: clamp(1.5rem, 3vw, 2.5rem);
}

/* Responsive padding */
.container {
    padding: clamp(1rem, 3vw, 3rem);
}

/* Responsive gap */
.gallery {
    gap: clamp(0.5rem, 2vw, 1.5rem);
}
```

---

## 🔐 Security Best Practices

- **CSRF Protection:** Always use `@csrf` in forms
- **Mass Assignment:** Use `$fillable` or `$guarded` in models
- **SQL Injection:** Use Eloquent or parameterized queries
- **XSS Protection:** Blade auto-escapes, use `{!! !!}` carefully
- **File Upload Validation:** Validate file types and sizes
- **Environment Variables:** Never commit `.env` file
- **API Keys:** Store in `.env`, never in code

---

## 🌐 Deployment Checklist

### Pre-Deployment
- [ ] Run tests: `php artisan test`
- [ ] Build frontend: `npm run build`
- [ ] Clear and cache config: `php artisan config:cache`
- [ ] Clear and cache routes: `php artisan route:cache`
- [ ] Optimize Composer autoload: `composer install --optimize-autoloader --no-dev`
- [ ] Set `APP_DEBUG=false` in `.env`
- [ ] Set `APP_ENV=production` in `.env`

### Railway Specific
- [ ] Commit all files to Git
- [ ] Push to GitHub
- [ ] Configure environment variables in Railway dashboard
- [ ] Set database to PostgreSQL
- [ ] Verify build logs for errors
- [ ] Test deployment thoroughly

---

## 📖 Helpful Resources

- **Laravel 12 Documentation:** https://laravel.com/docs/12.x
- **Laravel Best Practices:** https://github.com/alexeymezenin/laravel-best-practices
- **Blade Templates:** https://laravel.com/docs/12.x/blade
- **Eloquent ORM:** https://laravel.com/docs/12.x/eloquent
- **Railway Docs:** https://docs.railway.app/
- **MailerSend API:** https://www.mailersend.com/help
- **CSS clamp() Guide:** https://web.dev/min-max-clamp/
- **Web Performance:** https://web.dev/performance/

---

## 📝 Notes

### Project Philosophy
This is a personal love journey application meant to be:
- **Romantic and beautiful** - aesthetics matter
- **Personal and intimate** - it's about cherishing memories
- **Easy to use** - simple, intuitive interface
- **Performant** - fast loading, smooth animations
- **Accessible** - usable by everyone

### Development Mindset
- **Mobile-first:** Most users will view on phones
- **Performance:** Optimize everything, especially images
- **Accessibility:** Make it usable for everyone
- **Clean code:** Future you will thank present you
- **Test often:** Don't wait until deployment to test

---

**Last Updated:** January 6, 2026  
**Maintainer:** hkai7706  
**Repository:** https://github.com/hkai7706/journey  
**Status:** Active Development 💝

---

## 🔄 Changelog

### Version 1.0 (Current)
- Initial project setup with Laravel 12
- Implemented keepsake CRUD operations
- Added love survey with email notifications
- Created gallery with 4 viewing styles
- Timeline and calendar views
- Export functionality

### Future Updates
- To be documented as features are added...