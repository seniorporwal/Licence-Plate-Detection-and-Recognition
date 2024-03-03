This the first iteration of the code, more inspections needs to be done 


had to remove the history of the project after encountering an error.

error: remote: error: File runs/detect/train6/demo3.mp4 is 125.45 MB; this exceeds GitHub's file size limit of 100.00 MB
remote: error: GH001: Large files detected. You may want to try Git Large File Storage - https://git-lfs.github.com.

If you've already deleted the demo3.mp4 file from your repository but are still encountering issues when pushing, it's possible that the file is still referenced in your Git history.


Check git history
git log --oneline -- path/to/demo3.mp4

rewrite git history
git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch path/to/demo3.mp4' --prune-empty --tag-name-filter cat -- --all

force push changes to origin main
git push origin main --force

