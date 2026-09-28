# 1. Create a clean showcase folder outside your private repo
mkdir d:\youtube-showcase
cd d:\youtube-showcase

# 2. Create an assets directory and copy your screenshots into it
mkdir assets

# 3. Create README.md (paste the template from Step 4)
# 4. Initialize git and push to your new public repository
git init
git add .
git commit -m "feat: initial showcase release and architecture documentation"
git branch -M main
git remote add origin https://github.com/yaseen720/youtube-automation-command-center.git
git push -u origin main
