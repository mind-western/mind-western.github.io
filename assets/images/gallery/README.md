# Gallery Images

This directory contains images for the MIND Platform gallery page.

## Directory Structure

Organize images by category:
- `equipment/` - Photos of equipment and facilities
- `research/` - Research highlights and visualizations
- `events/` - Event and seminar photos
- `training/` - Training and educational materials

## Adding New Images

1. Place your image file in the appropriate subdirectory
2. Update `/home/runner/work/mind-western.github.io/mind-western.github.io/_data/gallery/images.yml` with the new entry:

```yaml
- title: "Your Image Title"
  description: "Brief description of the image"
  image: "/assets/images/gallery/category/filename.jpg"
  category: "equipment|research|events|training"
  date: "YYYY-MM-DD"
```

## Image Requirements

- **Format**: JPEG, PNG, or WebP
- **Size**: Optimized for web (max 1-2 MB per image)
- **Resolution**: At least 1200px wide for best quality
- **Aspect Ratio**: 3:2 recommended (e.g., 1200x800px)

## Best Practices

- Use descriptive filenames (e.g., `mri-scanner-front-view.jpg`)
- Compress images before uploading to reduce load times
- Include alt text descriptions for accessibility
