# GitHub Pages Setup Instructions

Follow these steps to enable GitHub Pages for this repository:

## Step 1: Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/hasagar97/public-key-host`
2. Click on **Settings** (top navigation bar)
3. Scroll down and click on **Pages** in the left sidebar
4. Under **Source**, select:
   - Source: **GitHub Actions**
   
   OR if using the classic method:
   - Source: **Deploy from a branch**
   - Branch: **main** (or **master**)
   - Folder: **/ (root)**
5. Click **Save**

## Step 2: Wait for Deployment

- GitHub will automatically build and deploy your site
- This usually takes 1-2 minutes
- You'll see a green checkmark when it's ready
- Your site will be available at: `https://hasagar97.github.io/public-key-host/`

## Step 3: Verify It's Working

Visit `https://hasagar97.github.io/public-key-host/` in your browser. You should see:
- A nicely formatted page listing your public keys
- Links to download individual keys

## Step 4: Add Your Public Keys

1. Replace the placeholder in `keys/ssh-rsa.pub` with your actual public key
2. Add more key files to the `keys/` directory as needed
3. Update `index.html` to list any new keys
4. Commit and push your changes

Example:
```bash
# Copy your SSH public key
cat ~/.ssh/id_rsa.pub > keys/ssh-rsa.pub

# Or add a new key type
cat ~/.ssh/id_ed25519.pub > keys/ssh-ed25519.pub

# Commit and push
git add keys/
git commit -m "Add my public keys"
git push
```

## Testing Your Keys

Once deployed, test that your keys are accessible:

```bash
# View the key
curl https://hasagar97.github.io/public-key-host/keys/ssh-rsa.pub

# Add to authorized_keys
curl https://hasagar97.github.io/public-key-host/keys/ssh-rsa.pub >> ~/.ssh/authorized_keys
```

## Troubleshooting

### Site not loading?
- Wait a few minutes after enabling Pages
- Check the Actions tab for deployment status
- Ensure the workflow has necessary permissions

### 404 errors?
- Verify the file exists in the `keys/` directory
- Check that file names match what's in `index.html`
- Clear your browser cache

### Changes not showing?
- GitHub Pages can take a few minutes to update
- Check the Actions tab to see if deployment succeeded
- Try hard refresh (Ctrl+Shift+R or Cmd+Shift+R)

## Security Reminders

- ✅ Only commit **public** keys
- ❌ Never commit private keys
- ✅ Keep private keys secure on your local machine
- ✅ Review what you commit before pushing
