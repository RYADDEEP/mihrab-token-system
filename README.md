# 📘 Mihrab Token System

This repository holds the entire **Mihrab Token System**, structured for both **Design Tokens** (W3C DTCG-compliant) and **Content/Data Files** used across the Mihrab multi-device Islamic app.

---

## ✅ System Highlights

- 📦 **62 Files** across **10 organized folders**
- 🎨 **Design Tokens** – W3C DTCG format, Token Studio compatible
- 🕌 **Awrad, Names, Smart Reminders** – Native structured JSON for use in Flutter apps
- 🌍 **Multilingual** localization-ready JSON
- 🔄 **Dual Workflow**:
  - **Figma + Token Studio** (for design system integration)
  - **Flutter + GitHub** (for app development)

---

## 📁 Folder Structure

```
mihrab-token-system/
├── Awrad/                  # 34 JSON files of authentic Adhkar
├── Daily_Goals/            # Daily Qur'an, Prayer, Awrad goals
├── Design_Tokens/          # DTCG-compliant tokens for Figma & Token Studio
├── Group_System/           # JSON data for admin/member roles
├── Localization_Files/     # UI translations in 12 languages
├── Multi_Device/           # Metadata for TV, Smartwatch, etc.
├── Names99/                # 99 Names of Allah with meaning + reflection
├── Prayer_Names/           # Prayer labels & metadata
├── Prayer_Times/           # Daily/Weekly/Monthly + by country
├── SmartNotification/      # Rotation-based motivators & reminders
```

---

## 🔗 Token Studio Integration

Only the `Design_Tokens/` folder is pulled into Figma via Token Studio using W3C DTCG format.

1. Connect GitHub as remote source
2. Pull `Design_Tokens/` only
3. Bind to Figma Styles, Text, Color
4. Push changes back to GitHub

---

## 🚀 Development Pipeline

- ✅ GitHub Repo Created & Linked
- ✅ Git Configured Locally
- ✅ Token Studio License Activated
- ✅ Figma Integration Working
- ✅ All JSON Files Validated and Committed

---

## 🧪 Testing & Next Steps

- [ ] Final review inside Token Studio
- [ ] Sync all style-bound values
- [ ] Begin Figma → Flutter UI sync phase
- [ ] Add Contribution & LICENSE files
- [ ] Push release-ready `v1` branch

---

🕋 Built with love for the Ummah.