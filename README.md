# Research Project Showcase Page Tutorial

English Version | [中文版](README_zh.md)

This tutorial will guide you through creating a professional research project showcase page with modular design, easy to maintain and extend.

**Disclaimer: This project template is for research and learning purposes only and does not involve any commercial use.**

**The content referenced in this project is from the latest research presentation by Carnegie Mellon University's AirLab at IROS 2025.**

**This project does not target its research content but serves as a tutorial case for the page, not representing the position or views of any research institution.**

**If you are interested in this research project, welcome to visit the project homepage: [pipe-planner.github.io](https://pipe-planner.github.io)**

## Project Overview

This research project showcase page template is developed using pure HTML/CSS/JavaScript with the following features:
- **Modular Design**: Each functional module is developed independently for easy maintenance
- **Responsive Layout**: Supports adaptive desktop and mobile devices
- **Configuration-Driven**: Content managed through JSON configuration files, no code modification required
- **Modern UI**: Clean and beautiful interface design

## Project Structure

```
research-project-template/
├── configs/              # Configuration files directory
│   ├── signboard.json    # Top signboard configuration
│   ├── info.json         # Project basic information configuration
│   └── main.json         # Main content configuration
├── images/               # Image resources directory
│   ├── signboard/        # Signboard images
│   ├── main/             # Main content images
│   ├── video/            # Video files
│   └── favicon/          # Webpage icon directory
├── src/                  # Source code directory
│   ├── font.css          # Font styles file
│   ├── signboard.js      # Top signboard module
│   ├── info-button.js    # Info button module
│   ├── authors.js        # Author information module
│   ├── info.js           # Project information module
│   ├── main.js           # Main content module
│   ├── mobile.js         # Mobile adaptation module
│   └── copyright.js      # Footer copyright module
├── font/                 # Font resources directory
│   ├── Excursion.ttf     # Excursion font file
│   ├── Nunito.ttf        # Nunito font file
│   ├── Oxanium.ttf       # Oxanium font file
│   └── Poppins.ttf       # Poppins font file
└── index.html            # Main page file
```

## Quick Start

### 1. Environment Preparation

You only need a modern web browser and a local web server. You can start a local server using the following methods:

```bash
# Using Python built-in server
python -m http.server 8000

# Or using Node.js http-server
npx http-server -p 8000
```

### 2. Fork Project Template

Fork is the operation of copying someone else's repository to your own account on GitHub, allowing you to modify based on the existing template without affecting the original project.

#### 2.1 Fork Steps

1. **Access Project Repository**
   - Open your browser and visit the GitHub repository page of the project template
   - Click the **Fork** button in the upper right corner of the page

2. **Select Target Account**
   - If you have multiple GitHub accounts or organizations, select the target account to fork the project to
   - Usually select your personal account

3. **Wait for Fork Completion**
   - The system will automatically copy the entire project to your account
   - After completion, you will see the same repository as the original project, but under your account

#### 2.2 Clone to Local

After forking is complete, you need to clone the repository to your local machine for modification:

```bash
# Clone your forked repository (replace YOUR_USERNAME with your GitHub username)
git clone https://github.com/YOUR_USERNAME/research-project-template.git

# Enter project directory
cd research-project-template
```

#### 2.3 Configure Remote Repository

To keep synchronized with the original project, it is recommended to add the upstream repository:

```bash
# Add upstream repository (original project repository)
git remote add upstream https://github.com/original-author/research-project-template.git

# View remote repository configuration
git remote -v
```

### 3. Configure GitHub Pages

#### 3.1 Personalization Configuration

Before configuring GitHub Pages, perform personalization configuration first:

1. **Modify Configuration Files**
   - Edit the JSON configuration files in the `configs/` directory
   - Replace with your own project information, author information, etc.

2. **Replace Image Resources**
   - Replace the images in the `images/` directory with your own project images
   - Keep the filename structure for correct reference by configuration files

3. **Test Local Effect**
   ```bash
   # Start local server for testing
   python -m http.server 8000
   
   # Visit http://localhost:8000 in browser
   ```

#### 3.2 Commit and Push Changes

After completing the configuration, push the changes to your GitHub repository:

```bash
# Add all changes to staging area
git add .

# Commit changes
git commit -m "Personalize project configuration"

# Push to your GitHub repository
git push origin main
```

#### 3.3 Enable GitHub Pages

Now configure GitHub Pages to host your project page:

1. **Enter Repository Settings**
   - On your GitHub repository page, click the **Settings** tab
   - Find the **Pages** section in the left menu

2. **Configure Publishing Source**
   - In the **Source** section, select **Deploy from a branch**
   - Select the **main** branch (or your default branch)
   - Select **/(root)** folder

3. **Enable GitHub Pages**
   - Click the **Save** button
   - The system will start building your page

4. **Access Your Page**
   - After construction is complete, your site URL will be displayed at the top of the page
   - The format is usually: `https://YOUR_USERNAME.github.io/research-project-template`
   - Click the link to visit your project showcase page

#### 3.4 Custom Domain (Optional)

If you want to use a custom domain, you can configure it following these steps:

1. **Configure Domain in Repository Settings**
   - In the GitHub Pages settings page, find the **Custom domain** section
   - Enter your custom domain (e.g., `www.your-domain.com`)
   - Click **Save**

2. **Configure DNS Resolution**
   - Log in to your domain provider management backend
   - Add DNS records pointing to GitHub Pages servers:
     - Record type: `CNAME`
     - Host record: `www` (or `@` for root domain)
     - Record value: `YOUR_USERNAME.github.io`

3. **Enable HTTPS**
   - In GitHub Pages settings, check **Enforce HTTPS**
   - Wait for the certificate to take effect (usually takes a few minutes to a few hours)

### 4. Basic Configuration

#### 4.1 Top Signboard Configuration

Edit the `configs/signboard.json` file:

```json
{
    // Lab and college logo files need to be saved in the images/signboard/ directory
    "lab": {
        "logoSrc": "lab logo filename",
        "url": "lab website URL"
    },
    "college": {
        "logoSrc": "college logo filename",
        "url": "college website URL"
    }
}
```

#### 4.2 Project Information Configuration

Edit the `configs/info.json` file:

```json
{
    "top-title": "Your Project Title",
    "conference": "Conference Name and Year",
    "institution": {
        "1": "Institution 1",
        "2": "Institution 2",
        // You can add more institutions
    },
    "authors": {
        "Author Name": {
            "homepage": "Author homepage",
            "affiliation": "1",    // Corresponds to the key in institution above
            "equal_or_not": true   // If no equal contribution, delete this line, Equal Contributions will not be displayed in the page
        }
    },
    "info-button": {
        // Note: If any of the following information is missing, delete the corresponding line, and the corresponding button will be hidden
        "arxiv": "Paper's arXiv link",
        "code": "Project's code repository link",
        "video": "Project's video link",
        "demo": "Project's demo link",
        "related_research":{
            "Related Research 1": "Related Research 1 link",
            "Related Research 2": "Related Research 2 link",
            // You can add more related research
        }
    }
}
```

#### 4.3 Main Content Configuration

Edit the `configs/main.json` file,

This document supports stacking and splicing of multiple content modules, so you can fully unleash your creative ability to combine a showcase page that meets your project needs.

Each object in the json corresponds to a module, and the module type is determined by the key in the object. Braces correspond to a container, and containers are displayed alternately through white/light gray. Each container can contain multiple modules.

This template strictly follows the order in the json for display, truly achieving what you see is what you get.

Each module's configuration items have their specific meanings. Here are the detailed configuration items for each supported module:

- Video module, including video file path (videoSrc, videoLink, etc.), video description (description)
- Image-text module, including image path (image), title (title), content description (content)
- BibTeX citation module, including citation content (bibtex)
- Button interaction module, triggered by button, then add buttons (button_{number}) in sequence, each button includes button name (button_name), and all the above module configuration items

Note: If there are multiple modules of the same type, you can distinguish them by {module}_{number} to prevent conflicts.

Currently supported multi-module types are: description, image, title, content, button_{number}

Here is a simple example.

```json
[
    {
        "videoSrc": "Video filename/link, supports local videos and online videos, with width of 1000px",
        // Local videos need to be stored in the images/video/ directory, same for videoLink
        "description": "Project brief description, width follows the above videoSrc",
        "title": "Abstract",
        "content": "Project detailed content..."
    },
    {
        "videoLink": "Video filename/link, supports local videos and online videos, with width of 800px",
        "description": "Project brief description, width follows the above videoLink",
    },
    {
        "title": "Module Title",
        "image": "Image filename, supports local images, with width of 800px",
        // Local images need to be stored in the images/main/ directory
        "content": "Module content description..."
    },
    // Different modules can be stacked in different ways, there is no requirement for who must be above or below, stack according to your arrangement
    // For example, I want to make an image-text module, first write the title, then display the image-text, then follow the title, and the next image-text module...
    {
        "title_1": "Module Title 1",
        "image_1": "Image 1",
        "content_1": "Module Content 1",
        "title_2": "Module Title 2",
        "image_2": "Image 2",
        "content_2": "Module Content 2",
    },

    // Following is the button module, need to create button container first, then add buttons in sequence, for example...
    {
        "title": "Result Display",
        "button": {
            "button_1": {
                "button_name": "Button Name",
                "image": "Image filename, supports local images, with width of 800px"
            },
            "button_2": {
                "button_name": "Button Name",
                "content": "Content"
            },
            "button_3": {
                "button_name": "Button Name",
                "image": "Image",
                "content": "Content"
            }
        }
    }
    // As for whether buttons can be nested within buttons?
    // Sorry, the author didn't think it through, but I think this is just a showcase page, no need to be so complicated

    // Finally is the citation module, it is recommended to place the citation module at the end, because the height of the citation module is fixed and cannot adapt to content height
    {
        "bibtex": "@article{example,
            title={Example Article},
            author={Author, A. and Another, B.},
            journal={Example Journal},
            year={2023},
            volume={1},
            number={1},
            pages={1-10}
        }"
    }

]
```

#### 4.4 Webpage Icon Configuration

Place the webpage icon file (e.g. favicon.ico) in the `images/favicon/` directory.

In `index.html`, reference the icon:

```html
<link rel="icon" href="images/favicon/favicon.ico" type="image/x-icon">
```

### 5. Module Details

#### 5.1 Top Signboard Module (signboard.js)

- **Function**: Display laboratory and institution logos
- **Features**: Fixed at the top of the page, responsive design
- **Configuration**: Configure logo images and links through `signboard.json`

#### 5.2 Info Button Module (info-button.js)

- **Function**: Display paper-related link buttons
- **Supported Button Types**: arXiv, code repository, video, demo, etc.
- **Style**: Unified button style with hover effects

#### 5.3 Author Information Module (authors.js)

- **Function**: Display project author information
- **Features**: Supports author homepage links, institution identification, equal contribution marking
- **Layout**: Responsive grid layout

#### 5.4 Project Information Module (info.js)

- **Function**: Display project title, conference information, etc.
- **Features**: Large title display, supports subtitle
- **Style**: Modern font and color design

#### 5.5 Main Content Module (main.js)

- **Function**: Display the main content of the project
- **Supported Content Types**:
  - Video module
  - Image-text module
  - Button interaction module
  - BibTeX citation module
- **Layout**: Modular stacking, adaptive width

#### 5.6 Mobile Adaptation Module (mobile.js)

- **Function**: Provide responsive adaptation for mobile devices
- **Adaptation Content**:
  - Signboard vertical stacking
  - Font size adjustment
  - Container height adaptation
  - Touch-friendly interaction

#### 5.7 Footer Copyright Module (copyright.js)

- **Function**: Display footer copyright information
- **Features**: Supports custom links and styles
- **Content**: Copyright statement and project links

### 6. Custom Styles

#### 6.1 Font Configuration

Google Fonts can be configured in `index.html`:

```html
<link href="https://fonts.googleapis.com/css2?family=Google+Sans&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@400;500;700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css?family=Poppins" rel="stylesheet">
```

Of course, you can also customize the font. Just put the font file in the `font/` directory, and then reference it in `src/font.css` file, for example:

```css
@font-face {
    font-family: 'Excursion';
    src: url('font/Excursion.ttf') format('truetype');
}
```

Currently supported custom fonts:
- Excursion
- Nunito
- Oxanium
- Poppins

#### 6.2 Color Theme

Each module has independent CSS styles, and you can customize the color theme by modifying the style strings in the corresponding JavaScript files.

#### 6.3 Responsive Breakpoints

Mobile adaptation uses the following breakpoints:
- **Below 768px**: Tablet and mobile devices
- **Below 480px**: Small screen mobile devices

### 7. Deployment Guide

#### 7.1 Static Deployment

1. Upload all files to a web server
2. Ensure image paths are correct
3. Configure correct MIME types

#### 7.2 GitHub Pages Maintenance

If you have already configured GitHub Pages according to the quick start guide above, here is some maintenance-related information:

##### 7.2.1 Keeping Sync with Original Project

If the original project template has updates, you can merge these updates into your fork:

```bash
# Get the latest changes from the upstream repository
git fetch upstream

# Switch to your local main branch
git checkout main

# Merge changes from the upstream repository
git merge upstream/main

# Push updates to your GitHub repository
git push origin main
```

##### 7.2.2 Troubleshooting

**Common Issues and Solutions:**

1. **GitHub Pages Build Failure**
   - Check if file paths are correct
   - Ensure there are no syntax errors (especially in JSON configuration files)
   - Check the repository's Actions page for detailed error information

2. **Styles Not Displaying**
   - Ensure all files have been pushed correctly
   - Check file path case sensitivity (GitHub Pages is case-sensitive)
   - Clear browser cache and retry

3. **Custom Domain Not Taking Effect**
   - Check if DNS configuration is correct
   - Wait for DNS propagation to complete (usually takes 24-48 hours)
   - Confirm the domain resolves to the correct GitHub server

#### 7.3 Other Deployment Methods

In addition to GitHub Pages, you can also choose other deployment methods:

##### 7.3.1 Static Server Deployment

1. Upload all files to any web server that supports static files
2. Ensure image paths are correct
3. Configure correct MIME types

##### 7.3.2 Other Hosting Platforms

- **Netlify**: Supports drag-and-drop deployment, automatic HTTPS
- **Vercel**: Excellent performance and edge network
- **GitLab Pages**: GitLab solution similar to GitHub Pages

### 8. Best Practices

#### 8.1 Image Optimization

- Use WebP format to reduce file size
- Compress images to improve loading speed
- Provide different resolution images for different devices

#### 8.2 Performance Optimization

- Compress JavaScript and CSS files
- Use CDN to accelerate fonts and static resources
- Enable browser caching

#### 8.3 Content Organization

- Keep configuration file structure clear
- Use meaningful file naming
- Regularly backup important files

### 9. Troubleshooting

#### 9.1 Common Issues

**Q: Page styles not displaying**
A: Check if CSS styles are loading correctly, ensure JavaScript file paths are correct

**Q: Images not displaying**
A: Check if image paths are correct, ensure image files exist

**Q: Mobile display abnormalities**
A: Check viewport settings, ensure mobile adaptation module is loading correctly

#### 9.2 Debugging Tips

- Use browser developer tools to inspect elements
- View console error information
- Test by loading modules step by step

### 10. Extended Features

#### 10.1 Adding New Modules

1. Create a new JavaScript file in the `src/` directory
2. Add module reference in `index.html`
3. Create corresponding configuration files as needed

#### 10.2 Multi-language Support

Multi-language support can be achieved by creating multiple sets of configuration files, loading different configurations based on user language preferences.

#### 10.3 Theme Switching

You can add theme switching functionality to allow users to switch between light and dark themes.

## Summary

This tutorial provides a complete guide for creating research project showcase pages. Through modular design and configuration-driven approach, you can easily create professional research project showcase pages. The template has good scalability and maintainability, suitable for various academic research project display needs.

If you encounter problems during use, you can contact us through the following methods:
- Email: Conshein_Yuanxing@outlook.com
- GitHub: [Excursion-ConsHein](https://github.com/Excursion-ConsHein)

We hope you can create a research project showcase page that suits your needs!