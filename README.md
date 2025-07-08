\# Mihrab Token System



<div align="center">

&nbsp; <h3>🕌 Design Tokens • Prayer Content • Smart Notifications • Multi-Platform Support</h3>

&nbsp; <p>A comprehensive token-based design system for the Mihrab Islamic prayer application</p>

</div>



---



\## 📋 Overview



The Mihrab Token System is a structured collection of design tokens, Islamic content, and configuration files that power the Mihrab prayer application across multiple platforms. This repository contains 62 carefully organized JSON files supporting 12 languages and various device types.



\## 🗂 Repository Structure



```

mihrab-token-system/

├── tokens/                          # All Token Studio compatible files

│   ├── design/                      # Design system tokens (6 files)

│   ├── awrad/                       # Islamic prayers/dhikr content (34 files)

│   ├── notifications/               # Smart notification system (5 files)

│   ├── localization/                # Multi-language UI strings (6 files)

│   ├── islamic-data/                # Core Islamic datasets (5 files)

│   └── features/                    # App features configuration (6 files)

├── platform-configs/                # Device-specific configurations

├── reference/                       # Merged/backup files (not for import)

├── docs/                           # Additional documentation

└── exports/                        # Generated files for platforms

```



\## 📊 Token Statistics



| Category | File Count | Description |

|----------|------------|-------------|

| Design Tokens | 6 | Colors, typography, spacing, layout |

| Awrad Content | 34 | Morning, evening, and situational prayers |

| Smart Notifications | 5 | Dynamic reminder rotations |

| Morning/Evening Bundle | 1 | Combined prayer collection |

| Islamic Datasets | 4 | 99 Names, prayer names, methods |

| Reseller Config | 1 | Business logic and packages |

| \*\*Total Production Files\*\* | \*\*51\*\* | Ready for Token Studio import |

| Reference Files | 11 | Backups and merged versions |



\## 🌍 Language Support



Full support for 12 languages:

\- 🇸🇦 Arabic (ar)

\- 🇬🇧 English (en)

\- 🇮🇩 Indonesian (id)

\- 🇹🇷 Turkish (tr)

\- 🇫🇷 French (fr)

\- 🇩🇪 German (de)

\- 🇪🇸 Spanish (es)

\- 🇷🇺 Russian (ru)

\- 🇵🇰 Urdu (ur)

\- 🇲🇾 Malay (ms)

\- 🇧🇩 Bengali (bn)

\- 🇮🇷 Persian (fa)



\## 🚀 Quick Start Guide



\### Prerequisites

\- Figma account

\- Token Studio plugin (free or Pro)

\- Git (optional)



\### Installation Steps



1\. \*\*Clone or Download Repository\*\*

&nbsp;  ```bash

&nbsp;  git clone https://github.com/YOUR\_USERNAME/mihrab-token-system.git

&nbsp;  cd mihrab-token-system

&nbsp;  ```



2\. \*\*Token Studio Setup\*\*

&nbsp;  - Open Figma

&nbsp;  - Launch Token Studio plugin

&nbsp;  - Connect to this repository or import files locally



3\. \*\*Import Order\*\* (Important!)

&nbsp;  ```

&nbsp;  1. Design tokens first (establish base styles)

&nbsp;  2. Islamic data tokens (reference data)

&nbsp;  3. Awrad content tokens (prayer content)

&nbsp;  4. Notification tokens (dynamic content)

&nbsp;  5. Feature tokens (app configuration)

&nbsp;  ```



\## 🎨 Token Categories Explained



\### Design Tokens (`/tokens/design/`)

Foundation of the visual design system:

\- `colors\_tokens.json` - Brand colors, semantic colors

\- `typography\_tokens.json` - Font families, sizes, line heights

\- `spacing\_tokens.json` - Consistent spacing scale

\- `layout\_tokens.json` - Grid and layout configurations

\- `ui\_strings\_multilingual.json` - UI text in 12 languages

\- `app\_metadata\_tokens.json` - App configuration data



\### Awrad Tokens (`/tokens/awrad/`)

Comprehensive collection of Islamic prayers and supplications:

\- Morning \& Evening adhkar

\- Prayer-related supplications

\- Situational duas (travel, food, protection)

\- Special occasion prayers



\### Smart Notifications (`/tokens/notifications/`)

Dynamic reminder system with contextual messages:

\- Daily goals tracking

\- Prayer time reminders

\- Quran reading motivation

\- Awrad encouragement

\- Fajr wake-up messages



\### Islamic Data (`/tokens/islamic-data/`)

Core Islamic reference data:

\- `asmaulhusna\_tokens.json` - 99 Names of Allah

\- `prayer\_names\_tokens.json` - Prayer names in multiple languages

\- `adhan\_audio\_tokens.json` - Call to prayer configurations

\- `juristic\_methods\_tokens.json` - Fiqh calculation methods



\## 🔧 Token Studio Configuration



\### Token Set Order

Configure in Token Studio for proper inheritance:



```json

{

&nbsp; "$themes": \[],

&nbsp; "$metadata": {

&nbsp;   "tokenSetOrder": \[

&nbsp;     "design",

&nbsp;     "islamic-data",

&nbsp;     "awrad",

&nbsp;     "notifications",

&nbsp;     "localization",

&nbsp;     "features"

&nbsp;   ]

&nbsp; }

}

```



\### Naming Convention

All tokens follow dot notation for clarity:

\- Design: `design.colors.primary.500`

\- Content: `awrad.morning.001.text`

\- UI: `ui.screens.home.title`

\- Features: `features.goals.daily.target`



\## 📱 Platform Support



The system supports multiple platforms through responsive tokens:

\- 📱 Mobile (iOS \& Android)

\- 💻 Tablet

\- 🖥 Desktop

\- 📺 TV

\- ⌚ Wearables



\## 🛠 Development Workflow



\### For Designers

1\. Use Token Studio Pro for visual editing

2\. Apply tokens to Figma components

3\. Test across different themes/languages

4\. Export changes back to repository



\### For Developers

1\. Import tokens to your platform (Flutter/React/etc)

2\. Use token references in code

3\. Maintain single source of truth

4\. Subscribe to repository updates



\## 📦 Export Formats



Tokens can be exported to:

\- \*\*Figma\*\*: Native variables (Pro feature)

\- \*\*Flutter\*\*: Dart theme files

\- \*\*Web\*\*: CSS/SCSS variables

\- \*\*iOS\*\*: Swift style files

\- \*\*Android\*\*: XML resources



\## 🔄 Version Control



\### Branching Strategy

\- `main` - Production-ready tokens

\- `develop` - Active development

\- `feature/\*` - New features

\- `hotfix/\*` - Quick fixes



\### Release Process

1\. Create feature branch

2\. Make changes in Token Studio

3\. Test thoroughly

4\. Create pull request

5\. Merge after review

6\. Tag release version



\## 🤝 Contributing



We welcome contributions! Please:

1\. Fork the repository

2\. Create your feature branch

3\. Commit changes with clear messages

4\. Push to your branch

5\. Create a Pull Request



\### Commit Convention

\- `feat:` New features

\- `fix:` Bug fixes

\- `docs:` Documentation

\- `style:` Token updates

\- `refactor:` Code restructuring



\## 📄 License



This project is proprietary to the Mihrab application. Please see LICENSE file for details.



\## 🆘 Support



\- \*\*Documentation\*\*: Check `/docs` folder

\- \*\*Issues\*\*: GitHub Issues

\- \*\*Token Studio Help\*\*: \[tokens.studio](https://tokens.studio)

\- \*\*Contact\*\*: \[your-email@example.com]



\## 🙏 Acknowledgments



\- Token Studio team for the excellent Figma plugin

\- Contributors to the Islamic content

\- Translation teams for 12 languages

\- Mihrab app users worldwide



---



<div align="center">

&nbsp; <p>Built with ❤️ for the Muslim Ummah</p>

&nbsp; <p>© 2024 Mihrab Token System</p>

</div>

