# FCJ Workshop Template

A template repository using **Hugo** to build static websites.

## 1) Requirements
- **Git**
- **Hugo Extended** (recommended to use the *extended* version for SCSS/pipe support)

Quick check:
```bash
git --version
hugo version
```

---

## 2) Clone the source
```bash
git clone https://github.com/truongnv127/fcj-workshop-template.git
cd fcj-workshop-template
```

---

## 3) Install Hugo

### macOS (Homebrew)
```bash
brew update && brew upgrade
brew install hugo-extended
```

### Windows (Chocolatey, run PowerShell **as Administrator**)
```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
choco install hugo-extended -y
```

### Linux (Snap or APT)
**Snap:**
```bash
sudo snap install hugo --channel=extended --classic
```
**Debian/Ubuntu with APT (may not be the latest/extended version):**
```bash
sudo apt-get update
sudo apt-get install hugo
```

> If you need the latest **extended** version, prefer Snap or download the binary from Hugo’s release page.

Verify installation:
```bash
hugo version
# Example: Hugo Static Site Generator v0.xx.x-XXXXXXX/extended
```

---

## 4) Run in development mode
Inside the project directory:
```bash
hugo server -D
```
- Visit: `http://localhost:1313/`
- The `-D` flag also renders content marked with `draft: true`.

If you encounter missing theme/module errors:
```bash
hugo mod get all   # if the project uses Hugo Modules
# or
git submodule update --init --recursive  # if using Git submodules
```

---

## 5) Create new content (optional)
For example, to create a new post:
```bash
hugo new content/posts/hello-world.md
```
Then open the generated file and change `draft: true` to `false` when it’s ready.

---

## 6) Build for production
```bash
hugo
```
- The build output will be in the `public/` directory, ready for deployment.

---

## 7) Quick commands
| Purpose           | Command                                     |
|-------------------|---------------------------------------------|
| Clone repo        | `git clone ... && cd fcj-workshop-template` |
| Run dev server    | `hugo server -D`                            |
| Create post       | `hugo new content/posts/<name>.md`          |
| Production build  | `hugo`                                      |

---

## 8) Common issues
- **Not using Hugo Extended**: `hugo version` does not show `extended` → reinstall the *extended* version.
- **Missing module/theme**: run `hugo mod get all` or `git submodule update --init --recursive`.
- **Port already in use**: `hugo server -D --port 1314` (use another port).
- **Post not showing**: remove `draft: true` or run with `-D`.

---

## 9) License
Depends on the repository configuration. If no LICENSE is provided, please contact the maintainer.
