# MIND Platform Website

The MIND Platform website (mind-western.github.io) was built using Jekyll and GitHub Pages. The MIND Platform is the Mesoscopic Integrated Neuroimaging Data platform that revolutionizes brain research by combining Canada's most powerful MRI scanner with cutting-edge microscopy technology.

## Website Structure

The website organization is structured such that each page's associated data has a corresponding folder (if necessary) under `_data` and `_assets` (for images). The exception to this are individual pages, which are under `people/_posts`. Page templates and common elements are stored in `_layouts` and `_includes` respectively.

_A Jupyter notebook with a GitHub Actions cron job is utilized to update recent publications on a monthly basis._

The design of the website and use of Jekyll was inspired by [nbclab.github.io](https://github.com/NBCLab/nbclab.github.io).

All required packages are managed via [Poetry (v1.2.x)](https://python-poetry.org/). Click on the package link to see setup instructions.
_This is only required to run the Jupyter notebook._

## Updating website

See below for instructions on modifying each page. To modify or update a page, please make the necessary changes and create a pull request to the repository! 

GitHub Pages automatically builds and deploys the site when changes are merged to the master branch.

To preview these changes on your local machine prior to publishing, follow the instructions on the [following page](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll).

### `people`

This page contains all present and past platform members and collaborators. Each member's profile can be found in a markdown file under `people/_posts`. Within the front matter of each these files, contains information such as email, department, a link to a profile picture (a placeholder is used if not provided). 

In order to facilitate sorting on the page, a `year-month-date` format has been utilized. The `year` and `date` are irrelevant, but the `month` is used to identify the member's role (e.g. Post-doc vs PhD). The mapping can be seen below:

```
01 - Staff
02 - Post-doc
03 - PhD Student
04 - Master's Student
05 - Undergraduate Student
```

A template has been drawn up and can be found in the `people/_drafts` directory. 

By clicking on each user's profile picture, a window will pop up with information in detail, including a short blurb about the user, if provided.

If you include an image and it does not show up on the website, please check to see if an image has been uploaded or if the path is correct!

### `news`

Similar to people, `posts` (found under `news/_posts`) are used to create articles. However, the date used here is important as it is used to sort and grab the latest articles.

### `software`

Similar to people, `posts` (found under `software/_posts`) are used to create and update the table of developed software. As before, these are sorted by date and is not currently relevant for this page.

### `publications`

A Jupyter notebook is used to grab all publications. GitHub Actions is used to automate this process. This is updated monthly, and is currently set to display the 3 most recent articles. A full list of publications found is stored in a spreadsheet found in `_data/publications/publications.csv`.

## Media Assets and Dimension Guidelines

The website now supports background videos and large visual content to enhance the user experience. All media assets should be optimized for web delivery and include appropriate fallbacks for accessibility.

### Background Video
- **Location**: `/assets/video/`
- **Filename**: `background-hero.mp4` (with optional `background-hero.webm` for better compression)
- **Dimensions**: **1920×1080** (Full HD)
- **Duration**: 10-30 seconds (will loop automatically)
- **Requirements**: Auto-play, muted, looped
- **Fallback**: `hero-background.svg` or `hero-background.jpg` (same dimensions)
- **Usage**: Homepage hero section background

### Banner/Hero Visuals
- **Location**: `/assets/placeholders/` or `/assets/images/banners/`
- **Dimensions**: **1280×720** (HD 720p landscape)
- **Format**: JPEG (optimized, 80-90% quality) or PNG
- **Alt format**: WebP for better compression
- **Usage**: Section headers, feature highlights, call-to-action areas

### Section Visuals
- **Location**: `/assets/placeholders/` or `/assets/images/sections/`
- **Dimensions**: **800×600** (flexible 4:3 aspect ratio)
- **Format**: JPEG (optimized) or PNG
- **Usage**: Research highlights, technology showcases, content illustrations

### Inline Videos
- **Location**: `/assets/video/`
- **Dimensions**: **1280×720** (HD 720p landscape)
- **Format**: MP4 (H.264 codec) with optional WebM
- **Requirements**: Include poster image (same dimensions)
- **Usage**: Embedded demonstration videos, research overviews

### Implementation Notes
- **Accessibility**: All visuals must include descriptive alt text
- **Performance**: Images should be compressed and optimized for web
- **Responsive**: All media adapts to different screen sizes
- **Fallbacks**: Provide static image fallbacks for videos
- **File Management**: Placeholder assets are clearly marked with TODO comments in code

### Replacing Placeholder Assets
1. **Video Assets**: Replace placeholder SVGs with actual MP4/WebM files in `/assets/video/`
2. **Image Assets**: Replace SVG placeholders with optimized JPEG/PNG files
3. **Code Comments**: Search for "TODO:" comments in HTML/CSS files for specific replacement instructions
4. **Alt Text**: Update alt attributes with descriptive text for actual content
5. **Testing**: Verify responsive behavior across different devices and browsers

### Current Placeholder Locations
- Background video: `index.html` - Hero video section (commented out, using SVG fallback)
- Banner images: `index.html` - Banner section
- Section visuals: `index.html` - Research highlights and technology sections
- All placeholders are in `/assets/placeholders/` with descriptive SVG graphics
