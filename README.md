# Decision Making in Reinforcement Learning

A comprehensive poster presentation showcasing robust decision making frameworks for reinforcement learning agents.

## 🚀 GitHub Pages Deployment

### Step 1: Create GitHub Repository

1. **Create a new repository on GitHub**
   - Repository name: `Dicision-RL` (or your preferred name)
   - Make it public
   - Don't initialize with README (we already have one)

2. **Upload your project**

   **Option A: Using deployment scripts (Recommended)**
   
   **Windows:**
   ```cmd
   # First time setup
   git remote add origin https://github.com/YOUR_USERNAME/Dicision-RL.git
   
   # Deploy (run this whenever you make changes)
   deploy.bat
   ```
   
   **Linux/Mac:**
   ```bash
   # First time setup
   git remote add origin https://github.com/YOUR_USERNAME/Dicision-RL.git
   
   # Deploy (run this whenever you make changes)
   chmod +x deploy.sh
   ./deploy.sh
   ```

   **Option B: Manual Git commands**
   ```bash
   # Initialize git (if not already done)
   git init
   
   # Add all files
   git add .
   
   # Commit
   git commit -m "Initial commit: Decision RL Poster"
   
   # Add remote origin (replace with your GitHub username)
   git remote add origin https://github.com/YOUR_USERNAME/Dicision-RL.git
   
   # Push to GitHub
   git push -u origin main
   ```

### Step 2: Enable GitHub Pages

1. **Go to Repository Settings**
   - Navigate to your repository on GitHub
   - Click on "Settings" tab
   - Scroll down to "Pages" section

2. **Configure Pages Source**
   - Under "Source", select "GitHub Actions"
   - The workflow will automatically deploy your site

3. **Access Your Site**
   - Your site will be available at: `https://YOUR_USERNAME.github.io/Dicision-RL`
   - It may take a few minutes for the first deployment

### Step 3: Customize Your Site

1. **Update Configuration**
   - Edit `_config.yml` to change:
     - Repository name in `baseurl`
     - Author information
     - Site title and description

2. **Modify Content**
   - Edit `_includes/poster-content.md` for poster content
   - Add/remove images in `assets/img/` folder
   - Images are automatically included in the poster

### Local Development (Optional)

If you want to preview changes locally:

1. **Prerequisites**
   - Ruby 3.1+
   - Bundler gem

2. **Setup**
   ```bash
   # Install dependencies
   bundle install
   
   # Serve locally
   bundle exec jekyll serve
   
   # Access at http://localhost:4000
   ```

## 📁 Project Structure

```
Dicision-RL/
├── _config.yml              # Jekyll configuration
├── _includes/
│   └── poster-content.md    # Main poster content
├── assets/
│   ├── img/                 # All images and visualizations
│   ├── css/                 # Custom styles
│   └── js/                  # JavaScript files
├── .github/workflows/       # GitHub Actions for deployment
├── Gemfile                  # Ruby dependencies
└── README.md               # This file
```

## 🖼️ Image Management

The poster automatically includes all images from the `assets/img/` folder:

- **Author photos**: `iman.jpg`, `amirreza.jpg`
- **Method diagrams**: `method.pdf`, `method_prev.pdf`
- **Results graphs**: `graph.pdf`, `graph_length.pdf`, etc.
- **Game samples**: `Breakout_target_sample.pdf`, `Pong_target_sample.pdf`, etc.
- **Logos**: `drl-logo.png`, `riml-logo.png`, `logo.png`

## 🎨 Customization

### Updating Content
- Edit `_includes/poster-content.md` to modify the poster content
- Add new images to `assets/img/` - they'll be automatically included
- Update `_config.yml` for site metadata

### Styling
- Modify `assets/css/style.scss` for custom styles
- Update the Jekyll theme in `_config.yml`

## 🔧 Configuration

### GitHub Pages
- Repository name should match `baseurl` in `_config.yml`
- Enable GitHub Actions in repository settings
- Site will be available at `https://username.github.io/repository-name`
- Automatic deployment on every push to main branch

## 📊 Features

- **Responsive Design**: Works on all devices
- **Interactive Elements**: Smooth scrolling and animations
- **Math Support**: LaTeX/MathJax integration
- **Image Gallery**: Automatic image organization
- **Professional Layout**: Academic poster styling

## 🛠️ Troubleshooting

### Common Issues

1. **Images not loading**
   - Check file paths in `assets/img/`
   - Ensure images are committed to repository

2. **Jekyll build errors**
   - Run `bundle install` to update dependencies
   - Check `_config.yml` syntax

3. **GitHub Pages deployment issues**
   - Check GitHub Actions tab for build logs
   - Ensure all files are committed and pushed
   - Verify repository name matches `baseurl` in `_config.yml`

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👥 Authors

- **Iman Ahmadi** - iman1234ahmadi@gmail.com
- **Amirreza Tanevardi** - amirreza.tanevardi@gmail.com

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

**Live Demo**: [View the deployed poster](https://iman1234ahmadi.github.io/Dicision-RL)
