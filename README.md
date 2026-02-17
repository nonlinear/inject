# inject

Custom CSS/JS injections for various web apps.

**Philosophy:** Each app gets its own folder with custom styling, scripts, or Service Workers.

---

## Apps

### OpenClaw (`openclaw/`)
- **Purpose:** Clean webchat UI (hide noise, minimal layout)
- **Files:** `redesign.css`, `open-claw.sh`
- **Apply:** `./openclaw/open-claw.sh`

### Kavita (`kavita/`)
- **Purpose:** Offline reading (Service Worker cache)
- **Status:** TBD (see epic v0.4.0-offline-browser-storage)

### Komga (`komga/`)
- **Purpose:** Offline reading (Service Worker cache)
- **Status:** TBD (see epic v0.4.0-offline-browser-storage)

---

## Structure

```
inject/
├── README.md (this file)
├── openclaw/
│   ├── redesign.css
│   └── open-claw.sh
├── kavita/
│   └── (TBD: Service Worker)
└── komga/
    └── (TBD: Service Worker)
```

---

## How It Works

**Each app folder contains:**
- CSS/JS files (custom styling or behavior)
- Shell script or bookmarklet (apply injection)
- README (app-specific instructions)

**Generic backstage files (future):**
- ROADMAP.md (track injection features)
- CHANGELOG.md (version history)
- HEALTH.md (test injections work)
- POLICY.md (injection guidelines)

---

## Repo

**GitHub:** https://github.com/nonlinear/inject

---

**Created:** 2026-02-17  
**Status:** In development
