# 🖼️ Image Assets - VERANO ESTATE

This file documents the image assets for VERANO ESTATE and Chef Franko's professional site.

## 📦 Placeholder Images (Replace with Real Images)

The following SVG placeholders are provided for immediate deployment. Replace them with optimized real images when available:

### logo.svg → logo.png
- **Current:** `logo.svg` (placeholder)
- **Replace with:** Optimized Chef Franko logo
- **Recommended size:** 300x300px
- **Format:** PNG with transparency
- **Usage:** Main branding, headers, landing page

### chef-portrait.svg → chef-portrait.jpg
- **Current:** `chef-portrait.svg` (placeholder)
- **Replace with:** Professional chef photo
- **Recommended size:** 800x800px
- **Format:** JPG (quality 80-85%)
- **Usage:** About section, CV landing page

### wave-surf.svg → wave-surf.jpg
- **Current:** `wave-surf.svg` (placeholder)
- **Replace with:** Ocean/beach hero image
- **Recommended size:** 1920x1080px
- **Format:** JPG (quality 80-85%)
- **Usage:** Hero backgrounds, gallery sections

## 📂 Directory Structure

```
assets/images/
├── logo.svg (placeholder - replace with logo.png)
├── chef-portrait.svg (placeholder - replace with chef-portrait.jpg)
├── wave-surf.svg (placeholder - replace with wave-surf.jpg)
├── README.md (SOL portrait documentation)
├── IMAGES_INFO.md (this file)
├── branding/
│   └── logo-franko-chef.svg (existing brand logo)
└── menu/
    └── (menu and food images)
```

## 🎨 Image Optimization Guidelines

All images should be optimized before upload:

1. **Resize** to appropriate dimensions
2. **Compress** without visible quality loss (80-85% quality for JPG)
3. **Use appropriate formats:**
   - JPG for photos
   - PNG for logos/graphics with transparency
   - SVG for icons and simple graphics
4. **Target file sizes:**
   - Logos: < 100KB
   - Photos: < 300KB
   - Hero images: < 500KB

## 🔧 Optimization Tools

### Online Tools
- [TinyPNG](https://tinypng.com/) - Intelligent PNG/JPG compression
- [Squoosh](https://squoosh.app/) - Advanced image editor with preview
- [ImageOptim](https://imageoptim.com/) - Mac app for optimization

### Command Line (ImageMagick)
```bash
# Optimize and resize JPG
convert input.jpg -quality 85 -resize 1920x1080 output.jpg

# Optimize and resize PNG
convert input.png -resize 300x300 output.png

# Batch optimization
mogrify -quality 85 -resize 1920x1080 *.jpg
```

## ✅ Implementation Checklist

All images in the site already have:
- ✅ `loading="lazy"` for lazy loading (except hero images)
- ✅ Descriptive `alt` text for accessibility
- ✅ Appropriate dimensions defined in CSS
- ✅ Fallback to placeholders if real images not available

## 🔄 How to Replace Placeholders

```bash
# 1. Navigate to the images directory
cd assets/images/

# 2. Add your optimized images
cp /path/to/your/logo.png logo.png
cp /path/to/your/chef-portrait.jpg chef-portrait.jpg
cp /path/to/your/wave-surf.jpg wave-surf.jpg

# 3. Commit and push
git add logo.png chef-portrait.jpg wave-surf.jpg
git commit -m "Add optimized real images"
git push origin copilot/site-setup
```

**Note:** The site is fully functional with the SVG placeholders. Replace them at your convenience.

## 📖 Related Documentation

- [DEPLOYMENT_INSTRUCTIONS.md](../../DEPLOYMENT_INSTRUCTIONS.md) - Full deployment guide
- [README.md](./README.md) - SOL portrait documentation

---

© 2025 VERANO ESTATE - Chef Franko
