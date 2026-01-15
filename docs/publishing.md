## Publishing

This project bundles code and dependencies into one version controlled file.  Transformations are applied to ensure it runs in the targeted node environment.  Modifications to code or dependencies should be accompanied by a final build for validation.

Each release has a git tag matching its package and release version; example v1.4.0.  A second tag for each major version is regularly updated to point to the recommended release; example v1 points to v1.4.0, then updated to point to v1.5.0.  Consumers of this project use this second tag to minimise configuration changes in their projects while always getting the recommended release.  Using a specific release tag will lock in older or newer releases.

Changing the major version tag is the final step in the publishing process.  This project automates its own releases (using the current stable version of itself) from git tags committed to the repository.  When testing and validation of the new release is complete, the major release tag updated to point to the same commit as the new release.  

Publishing example using git.

1. Identify the Target Commit
```bash 
git log --oneline
``` 

2. Force Move the Tag Locally
```bash 
git tag -fa <tag-name> -m "New tag message" <commit-hash>
``` 

3. Force-Push the Updated Tag to the Remote
```bash 
git push --force origin <tag-name>
``` 
