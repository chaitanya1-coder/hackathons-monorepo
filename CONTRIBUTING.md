# Contributing to the Stellar x Polkadot Hackerhouse BLR Submissions

Thank you for participating in the Stellar x Polkadot Hackerhouse BLR! This guide will help you submit your project successfully.

## Getting Started

### Prerequisites

- Git installed on your system
- A GitHub account (or access to the repository)
- Your hackathon project ready to submit

## Submission Process

### Step 1: Clone the Repository

```bash
git clone <repository-url>
cd hackathons
```

### Step 2: Create Your Submission Folder

Create a new folder in the `submissions/` directory with your team or project name:

```bash
mkdir submissions/your-project-name
cd submissions/your-project-name
```

**Important:** 
- Use lowercase letters, numbers, and hyphens only
- Make sure the name is unique and descriptive
- Avoid special characters and spaces

### Step 3: Add Your Project

#### For New Projects:
- Start building in your submission folder
- Follow the project structure guidelines

#### For Existing Projects:
- Copy your project files into your submission folder
- Ensure all dependencies are documented
- Test that everything works from the new location

### Step 4: Create Your README

Every submission must include a README.md file. Use the template in `submissions/TEMPLATE/README.md` as a starting point.

Your README should include:

1. **Project Overview**
   - What your project does
   - The problem it solves
   - Key features

2. **Team Information**
   - Team name
   - Team member names and GitHub handles
   - Roles/responsibilities

3. **Technical Details**
   - Technologies, frameworks, and tools used
   - Architecture overview (if applicable)
   - Smart contracts, APIs, or other key components

4. **Setup Instructions**
   - Prerequisites
   - Installation steps
   - How to run the project
   - Environment variables or configuration needed

5. **Demo & Links**
   - Live demo URL (if available)
   - Video demo link
   - Screenshots or diagrams
   - Deployed contract addresses (if applicable)

6. **Additional Information**
   - Challenges faced
   - Future improvements
   - Any other relevant information

### Step 5: Organize Your Files

Keep your project well-organized:

```
your-project-name/
├── README.md
├── LICENSE (optional)
├── src/              # Source code
├── tests/            # Test files
├── docs/             # Additional documentation
├── package.json      # Dependencies (if applicable)
└── ...              # Other project files
```

### Step 6: Commit and Push

```bash
# Navigate back to repository root
cd ../..

# Stage your changes
git add submissions/your-project-name/

# Commit with a descriptive message
git commit -m "Add submission: [Your Project Name] by [Team Name]"

# Push to the repository
git push origin main
```

## Best Practices

### Code Quality
- Write clean, readable code
- Add comments where necessary
- Follow language-specific best practices
- Include error handling

### Documentation
- Document your code
- Explain complex logic
- Include inline comments for non-obvious code
- Keep your README up to date

### Testing
- Test your project before submitting
- Include test files if applicable
- Document known issues or limitations

### Git Practices
- Use descriptive commit messages
- Don't commit sensitive information (API keys, private keys, etc.)
- Use `.gitignore` appropriately
- Keep commits focused and logical

## What NOT to Include

- ❌ API keys, private keys, or secrets
- ❌ Large binary files (use Git LFS if necessary)
- ❌ `node_modules/` or other dependency folders (document in README instead)
- ❌ Personal information that shouldn't be public
- ❌ Copyrighted material you don't have rights to

## Updating Your Submission

If you need to update your submission:

1. Make your changes in your submission folder
2. Commit the changes:
   ```bash
   git add submissions/your-project-name/
   git commit -m "Update submission: [description of changes]"
   git push origin main
   ```

## Troubleshooting

### Merge Conflicts
If you encounter merge conflicts:
1. Pull the latest changes: `git pull origin main`
2. Resolve conflicts manually
3. Commit and push again

### Large Files
If your project includes large files:
- Consider using Git LFS
- Or provide download links in your README
- Compress files when possible

## Questions?

If you have questions or encounter issues:
1. Check this guide first
2. Review the main README.md
3. Open an issue in the repository
4. Contact us

---

**Good luck with your submission! 🚀**

