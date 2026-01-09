# GitHub Pages Deployment Instructions

This repository is now configured to be hosted on GitHub Pages. Follow these steps to complete the deployment setup.

## Prerequisites

The repository has been configured with:
- **URL**: `https://anandkumar89.github.io`
- **Base URL**: `/scaling-eureka`
- **Deployment workflow**: `.github/workflows/deploy.yml` (already configured)

## Steps to Enable GitHub Pages

### 1. Enable GitHub Actions (if not already enabled)

1. Go to your repository on GitHub: `https://github.com/anandkumar89/scaling-eureka`
2. Click on the **Actions** tab
3. If prompted, click **"I understand my workflows, go ahead and enable them"**

### 2. Configure GitHub Actions Permissions

1. Go to **Settings** → **Actions** → **General**
2. Scroll down to **Workflow permissions**
3. Select **"Read and write permissions"**
4. Check **"Allow GitHub Actions to create and approve pull requests"**
5. Click **Save**

### 3. Trigger the Initial Deployment

The deployment workflow will automatically run when changes are pushed to the `main` branch. To trigger it:

1. Merge this PR to your `main` branch, OR
2. Go to **Actions** tab → **Deploy site** → **Run workflow** → Select `main` branch → **Run workflow**

### 4. Wait for the Deployment to Complete

1. Go to the **Actions** tab
2. Watch for the **Deploy site** workflow to complete (takes ~4-5 minutes)
3. Once complete, you should see a new `gh-pages` branch in your repository

### 5. Configure GitHub Pages Settings

1. Go to **Settings** → **Pages**
2. Under **Build and deployment**:
   - **Source**: Select **Deploy from a branch**
   - **Branch**: Select **gh-pages** (NOT main)
   - **Folder**: Select **/ (root)**
3. Click **Save**

### 6. Wait for GitHub Pages Deployment

1. Return to the **Actions** tab
2. Wait for the **pages-build-deployment** workflow to complete (~45 seconds)
3. Once complete, your site will be available at: **https://anandkumar89.github.io/scaling-eureka/**

## Verification

After deployment is complete, visit your site at:
- **Main URL**: https://anandkumar89.github.io/scaling-eureka/

## Automatic Updates

Once set up, your site will automatically rebuild and redeploy whenever you push changes to the `main` branch. The deployment workflow is triggered by changes to:
- Configuration files (`_config.yml`)
- Content files (`.md`, `.html`, `.liquid`)
- Assets (CSS, JS, images)
- Layouts and includes

## Troubleshooting

### If the deployment fails:

1. Check the **Actions** tab for error messages
2. Ensure GitHub Actions has write permissions (Step 2)
3. Verify the `gh-pages` branch exists
4. Check that GitHub Pages is set to deploy from `gh-pages` branch (Step 5)

### If the site doesn't load correctly:

1. Verify the URL settings in `_config.yml`:
   - `url: https://anandkumar89.github.io`
   - `baseurl: /scaling-eureka`
2. Clear your browser cache
3. Wait a few minutes for DNS propagation

## Customization

To customize your site:
1. Edit `_config.yml` to update site title, description, and personal information
2. Update content in `_pages/`, `_posts/`, `_projects/`, etc.
3. Modify styling in `_sass/` directory
4. See [CUSTOMIZE.md](CUSTOMIZE.md) for detailed customization instructions

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [al-folio Theme Documentation](https://github.com/alshedivat/al-folio)
- [Jekyll Documentation](https://jekyllrb.com/docs/)
