# Public Key Host

This repository hosts public keys using GitHub Pages, making them easily accessible via HTTPS URLs.

## 🌐 Live Site

Visit the hosted page at: `https://hasagar97.github.io/public-key-host/`

## 📁 Repository Structure

```
public-key-host/
├── index.html          # Main page listing available keys
├── keys/              # Directory containing public keys
│   └── ssh-rsa.pub   # SSH RSA public key
├── jwks/              # Directory containing JWKS files
│   └── epic.json     # JWKS JSON file
├── .nojekyll         # Ensures GitHub Pages serves files correctly
└── README.md         # This file
```

## 🔑 Adding Your Public Keys

1. Place your public key files in the `keys/` directory
2. Update `index.html` to list your new keys
3. Commit and push your changes
4. Your keys will be accessible at: `https://hasagar97.github.io/public-key-host/keys/<key-file-name>`

## 📝 Usage Examples

### Add SSH Key to authorized_keys

```bash
# Append key to authorized_keys
curl https://hasagar97.github.io/public-key-host/keys/ssh-rsa.pub >> ~/.ssh/authorized_keys

# Or set proper permissions after adding
chmod 600 ~/.ssh/authorized_keys
```

### Download a Key

```bash
# Download SSH key to current directory
curl -O https://hasagar97.github.io/public-key-host/keys/ssh-rsa.pub

# Download JWKS JSON to current directory
curl -O https://hasagar97.github.io/public-key-host/jwks/epic.json

# Download with custom name
curl -o my-key.pub https://hasagar97.github.io/public-key-host/keys/ssh-rsa.pub
curl -o epic-keys.json https://hasagar97.github.io/public-key-host/jwks/epic.json
```

### View Key Content

```bash
# View SSH key
curl https://hasagar97.github.io/public-key-host/keys/ssh-rsa.pub

# View JWKS JSON
curl https://hasagar97.github.io/public-key-host/jwks/epic.json
```

## ⚙️ Setting Up GitHub Pages

If you haven't already enabled GitHub Pages:

1. Go to your repository settings
2. Navigate to "Pages" section
3. Under "Source", select the branch (usually `main` or `master`)
4. Select "/ (root)" as the folder
5. Click "Save"

Your site will be published at `https://<username>.github.io/<repository-name>/`

## 🔒 Security Notes

- Only store **public** keys in this repository
- Never commit private keys
- Public keys are meant to be public - anyone can access them
- Regularly review and rotate your keys as needed

## 📦 Key Types Supported

You can host any type of public key:
- SSH keys (RSA, ED25519, ECDSA)
- GPG/PGP public keys
- SSL/TLS certificates
- Any other public key format

## 🤝 Contributing

To add or update keys:

1. Edit files in the `keys/` directory
2. Update `index.html` if adding new keys
3. Commit your changes
4. Push to the repository

Changes will be reflected on GitHub Pages within a few minutes.