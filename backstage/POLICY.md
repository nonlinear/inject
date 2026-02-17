# Inject Project Policy

**Project:** inject (CSS/JS injections for web apps)  
**Repository:** https://github.com/nonlinear/inject

---

## Skill Frontmatter Schema

All inject skills must follow this frontmatter structure:

### Universal Fields (all skills)

```yaml
---
name: skill-name-inject
description: "Brief description"
type: inject
version: X.Y.Z
status: production | beta | experimental
author: nonlinear
license: MIT
---
```

### Inject-Specific Fields

```yaml
inject:
  type: css | service-worker | browser-extension | bookmarklet | userscript
  app:
    name: AppName
    url: https://app-url.com
    version: X.Y.Z  # tested version
  platform: web | ios | android | desktop  # optional, default: web
  browser: chrome | firefox | safari | edge | all  # optional, if web
  reference: technique-doc.md  # link to canonical technique
```

### Field Descriptions

**`inject.type`** - Injection technique used
- `css` - Custom stylesheets
- `service-worker` - PWA Service Worker
- `browser-extension` - Chrome/Firefox extension
- `bookmarklet` - JavaScript bookmarklet
- `userscript` - Tampermonkey/Greasemonkey script

**`inject.app.name`** - Target application name

**`inject.app.url`** - Official app URL

**`inject.app.version`** - App version tested with this injection (for compatibility tracking)

**`inject.platform`** - Target platform (optional, default: `web`)

**`inject.browser`** - Browser compatibility (optional, if platform is `web`)

**`inject.reference`** - Link to canonical technique documentation in `inject/docs/`

---

## Technique Documentation

Shared injection techniques live in `inject/docs/`:

- `css-injection.md` - How CSS injection works
- `service-worker-injection.md` - How Service Worker injection works
- `browser-extension-injection.md` - How browser extensions work
- etc.

**Skills reference these docs** via `inject.reference` field.

**When technique improves:**
1. Update canonical doc in `inject/docs/`
2. All skills using that technique benefit automatically
3. Users know which skills are compatible (same `inject.type`)

---

## Example: OpenClaw CSS Injection

```yaml
---
name: openclaw-inject
description: "Clean OpenClaw webchat UI (hide noise, minimal layout)"
type: inject
version: 0.1.0
status: production
author: nonlinear
license: MIT
inject:
  type: css
  app:
    name: OpenClaw
    url: https://openclaw.ai
    version: 2026.2.9
  platform: web
  browser: chrome
  reference: css-injection.md
---
```

---

## Example: Kavita Service Worker

```yaml
---
name: kavita-inject
description: "Offline reading for Kavita (Service Worker cache)"
type: inject
version: 0.1.0
status: experimental
author: nonlinear
license: MIT
inject:
  type: service-worker
  app:
    name: Kavita
    url: https://kavitareader.com
    version: 0.7.14
  platform: web
  browser: all
  reference: service-worker-injection.md
---
```

---

## File Structure

```
inject/
├── README.md
├── backstage/
│   ├── ROADMAP.md
│   ├── CHANGELOG.md
│   ├── HEALTH.md
│   └── POLICY.md (this file)
├── docs/
│   ├── css-injection.md
│   ├── service-worker-injection.md
│   └── browser-extension-injection.md
├── openclaw-inject/
│   ├── SKILL.md
│   ├── redesign.css
│   └── open-claw.sh
├── kavita-inject/
│   ├── SKILL.md
│   └── service-worker.js
└── komga-inject/
    ├── SKILL.md
    └── service-worker.js
```

---

## Naming Convention

Skills named `{app}-inject` format:
- `openclaw-inject`
- `kavita-inject`
- `komga-inject`
- `figma-inject` (future)

**Why:** Clear app context + skill type in one name.

---

## Publishing

Each inject skill = separate npm package (optional):
- `@nonlinear/openclaw-inject`
- `@nonlinear/kavita-inject`

Share technique docs (`inject/docs/`) across all skills.

---

**Created:** 2026-02-17  
**Status:** Active
