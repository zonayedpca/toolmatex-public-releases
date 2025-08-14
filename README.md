# 🛠 ToolMateX — Public Release Builds

Welcome to the **public release repository** for **ToolMateX**, the ultimate collection of developer, design, and productivity tools — available as a **desktop app** for macOS, Windows, and Linux.

This repo contains **prebuilt releases** for multiple platforms and architectures, plus an `app.json` manifest to help you (or the ToolMateX app) automatically find the correct download for your system.

---

## 📦 What's Inside

### 1. `releases/`  
Contains all downloadable builds, organized by platform and architecture:

```
releases/
├── macos/
│   ├── intel/
│   │   └── ToolMateX-x64.dmg
│   └── silicon/
│       └── ToolMateX-arm64.dmg
├── windows/
│   ├── x64/
│   │   ├── ToolMateX-x64.exe
│   │   └── ToolMateX-x64.msi
├── linux/
│   ├── deb/
│   │   └── ToolMateX-amd64.deb
│   ├── rpm/
│   │   └── ToolMateX.x86_64.rpm
│   └── appimage/
│       └── ToolMateX-x86_64.AppImage
```

---

### 2. `app.json`  
A **machine-readable manifest** that lists the latest build files for each platform, architecture, and package type.

**Example:**
```json
{
  "macos": {
    "intel": {
      "type": "dmg",
      "name": "ToolMateX-x64.dmg",
      "url": "https://github.com/yourname/toolmatex/releases/latest/download/ToolMateX-x64.dmg"
    },
    "silicon": {
      "type": "dmg",
      "name": "ToolMateX-arm64.dmg",
      "url": "https://github.com/yourname/toolmatex/releases/latest/download/ToolMateX-arm64.dmg"
    }
  },
  "windows": {
    "x64": {
      "exe": {
        "name": "ToolMateX-x64.exe",
        "url": "https://github.com/yourname/toolmatex/releases/latest/download/ToolMateX-x64.exe"
      },
      "msi": {
        "name": "ToolMateX-x64.msi",
        "url": "https://github.com/yourname/toolmatex/releases/latest/download/ToolMateX-x64.msi"
      }
    }
  },
  "linux": {
    "deb": {
      "name": "ToolMateX-amd64.deb",
      "url": "https://github.com/yourname/toolmatex/releases/latest/download/ToolMateX-amd64.deb"
    },
    "rpm": {
      "name": "ToolMateX.x86_64.rpm",
      "url": "https://github.com/yourname/toolmatex/releases/latest/download/ToolMateX.x86_64.rpm"
    },
    "appimage": {
      "name": "ToolMateX-x86_64.AppImage",
      "url": "https://github.com/yourname/toolmatex/releases/latest/download/ToolMateX-x86_64.AppImage"
    }
  }
}
```

---

## 💡 How to Download

You can **manually download** from the `releases/` folder or **automatically detect** your build using `app.json`.

### Manual
1. Go to the [`releases/`](./releases/) folder.
2. Choose your platform folder (`macos`, `windows`, `linux`).
3. Select the correct architecture (`intel`, `silicon`, `x64`).
4. Download your preferred installer type (`.dmg`, `.exe`, `.deb`, `.rpm`, `.AppImage`).

### Auto-Detection (Developers)
If you are building an updater or installer, simply:
```js
fetch('https://raw.githubusercontent.com/yourname/toolmatex/main/app.json')
  .then(res => res.json())
  .then(data => {
    // Example: detect macOS Intel
    const url = data.macos.intel.url;
    console.log("Download URL:", url);
  });
```

---

## 🔄 Updating Builds

When a new release is published:
1. Add the build files into the correct folder under `releases/`.
2. Update `app.json` with the new filenames & URLs.
3. Commit & push changes.

---

## 📜 License
This repository contains **prebuilt binaries** for ToolMateX.  
Source code is available in the [ToolMateX source repo](https://github.com/yourname/toolmatex-src).

---

## 🌐 Official Links
- **Website:** [https://toolmatex.com](https://toolmatex.com)  
- **Support:** [support@toolmatex.com](mailto:support@toolmatex.com)  
- **Twitter:** [@toolmatex](https://twitter.com/toolmatex)

---
