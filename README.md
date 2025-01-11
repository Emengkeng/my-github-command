# My GitHub Commands

A collection of useful GitHub commands for common operations and troubleshooting scenarios.

## Table of Contents
- [Remote Repository Management](#remote-repository-management)
- [Commit History Management](#commit-history-management)
- [Gitignore Management](#gitignore-management)

## Remote Repository Management

### Change Remote Origin URL
Instead of removing and re-adding the remote origin, use:
```bash
git remote set-url origin git://new.url.here
```

## Commit History Management

### Delete All Commit History
Follow these steps to completely reset your commit history:

1. Create an orphan branch (won't show in `git branch` command):
```bash
git checkout --orphan latest_branch
```

2. Add all files to the new branch:
```bash
git add -A
```

3. Commit the changes:
```bash
git commit -am "commit message"
```

4. Delete the main branch (WARNING: this is permanent):
```bash
git branch -D main
```

5. Rename current branch to main:
```bash
git branch -m main
```

6. Force update remote repository:
```bash
git push -f origin main
```

**Note:** This operation will permanently remove all commit history. Your repository will only show the new commit in its history.

## Gitignore Management

### Fix Ignored Files Not Being Ignored
If your `.gitignore` file is not working as expected, remove cached files:
```bash
git rm --cached <file_or_directory>
```

## References
- [Stack Overflow - Changing Remote URL](https://stackoverflow.com/a/16330439/17302876)
- [Stack Overflow - Deleting Commit History](https://stackoverflow.com/a/26000395/17302876)
- [Stack Overflow - Gitignore Issues](https://stackoverflow.com/a/45400404/17302876)

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
