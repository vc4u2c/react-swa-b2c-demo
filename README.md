# React Azure Static Web App With ADB2C Demo

React Azure Static Web App With ADB2C Demo

## Installation

```bash
cd C:\Users\Vinod Chandran\Documents\Source\Repos\React\
npx create-react-app react-swa-b2c-demo --template typescript --use-npm
cd react-semantic-release-demo
# Delete .git folder
git init -b main
git add .
git commit -m 'feat(app): Initial Create'
# In VS Code under Git extensions click on Publish Branch
# Ensure branch is published to GitHub

# Install Semantic Release Git and Changelog plugins
npm install --save-dev @semantic-release/git @semantic-release/changelog
```

### Add Semantic Release config to package.json

```json
  "private": true,
  "branches": ["main"],  
  "plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    "@semantic-release/changelog",
    "@semantic-release/github",
    "@semantic-release/npm",
    "@semantic-release/git"
  ],
  "release": {
    "prepare": [
      "@semantic-release/changelog",
      "@semantic-release/npm",
      {
        "path": "@semantic-release/git",
        "assets": [
          "package.json",
          "package-lock.json",
          "CHANGELOG.md"
        ],
        "message": "chore(release): ${nextRelease.version} [skip ci]\n\n${nextRelease.notes}"
      }
    ]
  }
```

### Commiting Code

```bash
git add .
git commit -m "feat: Add Semantic Release and Github Actions"
git push
```

### Running locally

```bash
# Start the development server
npm start
# Bundles the app into static files for production.
npm run build
# Starts the test runner.
npm test
# Removes this tool and copies build dependencies, configuration files and scripts into the app directory. If you do this, you can’t go back!
npm run eject

# React Semantic Release demo

```

## Notes
- https://github.com/codfish/semantic-release-action#basic-usage
- https://github.com/semantic-release/semantic-release
- https://semaphoreci.com/blog/automate-react-native-release
