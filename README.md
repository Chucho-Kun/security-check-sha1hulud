# security-check-sha1hulud
Steps to check if your repository is compromised by Sha1-Hulud: The Second Coming

### 1. Check npm dependencies
Look in your package.json and package-lock.json for packages from the following affected projects:
```
Zapier, ENS Domains, PostHog, Postman, AsyncAPI.
```
If you see any of these packages, check the installed version and compare it to the clean, official version in npm.
### 2. Audit your recent commits
Check your Git history for commits that you didn't make or that contain changes to installation scripts (preinstall, postinstall).

### 3. Examine installation scripts
The malware runs through npm preinstall scripts.
Open the packages installed in node_modules and look for scripts that:

#### * Exfiltrate environment variables.
#### * Delete directories or files.
#### * Install GitHub Actions runners without authorization.

### 4. Change your credentials
Immediately change your GitHub tokens, AWS keys, and passwords if you suspect your repository has been compromised.

### 5. Use security tools
Scan your project with services like [Socket.dev](https://socket.dev/), [JFrog Xray](https://jfrog.com/xray/), or [npm audit](https://docs.npmjs.com/cli/v10/commands/npm-audit) to detect compromised dependencies.

Enable Dependabot on GitHub to receive automatic security alerts.
