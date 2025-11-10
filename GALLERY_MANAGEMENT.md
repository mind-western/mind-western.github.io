# Gallery Management Guide

This guide explains how to add and manage images and videos on the MIND Platform gallery page.

## Adding New Videos

### Step 1: Upload to YouTube
1. Upload your video to the MIND Platform YouTube channel
2. Copy the video ID from the URL (e.g., `https://www.youtube.com/watch?v=dQw4w9WgXcQ` → video ID is `dQw4w9WgXcQ`)

### Step 2: Update the Data File
Edit `_data/gallery/videos.yml` and either:

**Option A: Replace a placeholder**
Find a placeholder entry like:
```yaml
- title: "15.2T MRI Scanner Overview"
  description: "Tour of Canada's most powerful MRI scanner and its capabilities"
  youtube_id: "PLACEHOLDER_VIDEO_1"  # Replace this
  category: "equipment"
  date: "2025-06-01"
  duration: "TBD"  # Update this
```

Change to:
```yaml
- title: "15.2T MRI Scanner Overview"
  description: "Tour of Canada's most powerful MRI scanner and its capabilities"
  youtube_id: "dQw4w9WgXcQ"  # Your actual YouTube video ID
  category: "equipment"
  date: "2025-06-01"
  duration: "5:30"  # Actual duration
```

**Option B: Add a new entry**
Add a new video at the end of the `videos:` list:
```yaml
- title: "Your Video Title"
  description: "Description of what the video shows"
  youtube_id: "YOUR_VIDEO_ID"
  category: "equipment|research|events|training"
  date: "YYYY-MM-DD"
  duration: "MM:SS"
```

### Video Categories
- `equipment` - Equipment and facilities tours/demos
- `research` - Research highlights and visualizations
- `events` - Seminars, workshops, and events
- `training` - Educational and training content

## Adding New Images

### Step 1: Prepare Your Image
1. Optimize the image for web (1-2 MB max, 1200px+ width recommended)
2. Use a descriptive filename (e.g., `mri-scanner-control-room.jpg`)
3. Choose the appropriate category

### Step 2: Upload the Image
Place the image in the correct subdirectory:
```
assets/images/gallery/
├── equipment/     (equipment photos)
├── research/      (research visualizations)
├── events/        (event photos)
└── training/      (training materials)
```

### Step 3: Update the Data File
Edit `_data/gallery/images.yml` and add a new entry:
```yaml
- title: "MRI Control Room"
  description: "Control room for the 15.2T MRI scanner showing operator stations"
  image: "/assets/images/gallery/equipment/mri-scanner-control-room.jpg"
  category: "equipment"
  date: "2025-11-10"
```

## Categories Explained

### Equipment & Facilities
- Photos and videos of lab equipment
- Facility tours
- Equipment demonstrations
- Setup and installation documentation

### Research Highlights
- Brain imaging results
- Data visualizations
- Research findings
- Comparison images
- Scientific illustrations

### Events & Seminars
- Seminar recordings
- Workshop photos
- Team events
- Collaboration meetings
- Conference presentations

### Training & Education
- Tutorial videos
- Training materials
- Educational content
- How-to guides
- Software demonstrations

## Best Practices

### For Videos
- **Title**: Clear, descriptive titles (50 characters or less)
- **Description**: Brief but informative (100-150 characters)
- **Duration**: Include actual video length for user reference
- **Quality**: Upload at least 1080p resolution to YouTube
- **Thumbnails**: Use custom thumbnails on YouTube for consistency

### For Images
- **Format**: JPEG for photos, PNG for graphics/screenshots
- **Size**: Compress images before uploading (use tools like TinyPNG)
- **Resolution**: At least 1200px wide for good quality on all devices
- **Aspect Ratio**: 3:2 (e.g., 1200x800px) works best with the gallery layout
- **Filenames**: Use lowercase, hyphens instead of spaces

## Testing Your Changes

After adding content:
1. Push your changes to GitHub
2. GitHub Pages will automatically rebuild the site (takes 2-5 minutes)
3. Visit https://mind-western.github.io/gallery/ to see your changes
4. Test the category filters to ensure items appear correctly
5. Check that videos embed properly and images display in modals

## Troubleshooting

**Video not showing:**
- Verify the YouTube video is set to "Public" (not Unlisted or Private)
- Double-check the video ID is correct
- Ensure there are no extra spaces in the YAML file

**Image not displaying:**
- Verify the image path is correct and starts with `/assets/images/gallery/`
- Check the image filename matches exactly (case-sensitive)
- Ensure the image was uploaded to the correct subdirectory

**Category filter not working:**
- Ensure the `category` field matches exactly: `equipment`, `research`, `events`, or `training`
- Check for typos in the category name

## Regular Maintenance

- Update video placeholders as content is uploaded to YouTube
- Add new videos every couple of weeks as they become available
- Review and update descriptions for clarity
- Remove outdated or irrelevant content as needed
- Organize large collections into sub-categories if needed

## Questions?

For questions about managing gallery content, contact the MIND Platform web team.
