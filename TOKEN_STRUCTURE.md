\# Token Structure Documentation



\## 🏗 Token Architecture Overview



This document provides detailed information about the token structure, naming conventions, and usage patterns for the Mihrab Token System.



\## 📐 Naming Convention



\### Base Pattern

All tokens follow a hierarchical dot notation pattern:

```

\[category].\[subcategory].\[element].\[variant].\[state]

```



\### Examples by Category



\#### Design Tokens

```

design.colors.primary.500

design.colors.semantic.success

design.typography.heading.h1

design.spacing.base.4

design.radius.medium

```



\#### Awrad Tokens

```

awrad.morning.001.text

awrad.morning.001.translation.en

awrad.evening.025.audio\_url

awrad.category.sleep.before\_sleep\_01

```



\#### UI Strings

```

ui.screens.home.title

ui.buttons.common.submit

ui.messages.error.network

ui.navigation.tabs.quran

```



\#### Feature Tokens

```

features.goals.daily.quran\_pages

features.notifications.smart.rotation\_interval

features.prayer\_times.calculation.method

```



\## 🗂 Token Set Organization



\### 1. Design Tokens (`/tokens/design/`)



\#### colors\_tokens.json

```json

{

&nbsp; "design": {

&nbsp;   "colors": {

&nbsp;     "primary": {

&nbsp;       "50": { "$value": "#e8f5e9" },

&nbsp;       "100": { "$value": "#c8e6c9" },

&nbsp;       "500": { "$value": "#4caf50" },

&nbsp;       "900": { "$value": "#1b5e20" }

&nbsp;     },

&nbsp;     "semantic": {

&nbsp;       "success": { "$value": "{design.colors.primary.500}" },

&nbsp;       "error": { "$value": "#f44336" },

&nbsp;       "warning": { "$value": "#ff9800" }

&nbsp;     }

&nbsp;   }

&nbsp; }

}

```



\#### typography\_tokens.json

```json

{

&nbsp; "design": {

&nbsp;   "typography": {

&nbsp;     "fontFamily": {

&nbsp;       "arabic": { "$value": "Amiri" },

&nbsp;       "latin": { "$value": "Inter" }

&nbsp;     },

&nbsp;     "fontSize": {

&nbsp;       "xs": { "$value": "12px" },

&nbsp;       "sm": { "$value": "14px" },

&nbsp;       "base": { "$value": "16px" }

&nbsp;     }

&nbsp;   }

&nbsp; }

}

```



\### 2. Awrad Tokens (`/tokens/awrad/`)



\#### Structure Pattern

Each awrad file contains:

```json

{

&nbsp; "awrad": {

&nbsp;   "\[category]": {

&nbsp;     "\[index]": {

&nbsp;       "text": { "$value": "Arabic text" },

&nbsp;       "translation": {

&nbsp;         "en": { "$value": "English translation" },

&nbsp;         "id": { "$value": "Indonesian translation" }

&nbsp;         // ... other languages

&nbsp;       },

&nbsp;       "audio\_url": { "$value": "https://..." },

&nbsp;       "repetition": { "$value": 3 },

&nbsp;       "category": { "$value": "morning" }

&nbsp;     }

&nbsp;   }

&nbsp; }

}

```



\#### File Categories

\- \*\*Time-based\*\*: morning, evening, night

\- \*\*Prayer-related\*\*: before\_prayer, after\_prayer, in\_prayer

\- \*\*Situational\*\*: travel, food, protection, health

\- \*\*Special occasions\*\*: ramadan, hajj, eid



\### 3. Smart Notifications (`/tokens/notifications/`)



\#### rotation\_daily\_goals.json

```json

{

&nbsp; "notifications": {

&nbsp;   "daily\_goals": {

&nbsp;     "messages": {

&nbsp;       "1": {

&nbsp;         "text": { "$value": "You're 50% to your Quran goal! 📖" },

&nbsp;         "trigger": { "$value": "goal\_progress" },

&nbsp;         "condition": { "$value": "percentage >= 50" }

&nbsp;       }

&nbsp;     }

&nbsp;   }

&nbsp; }

}

```



\### 4. Localization (`/tokens/localization/`)



\#### ui\_strings\_multilingual.json

```json

{

&nbsp; "ui": {

&nbsp;   "screens": {

&nbsp;     "home": {

&nbsp;       "title": {

&nbsp;         "ar": { "$value": "الرئيسية" },

&nbsp;         "en": { "$value": "Home" },

&nbsp;         "id": { "$value": "Beranda" }

&nbsp;         // ... 9 more languages

&nbsp;       }

&nbsp;     }

&nbsp;   }

&nbsp; }

}

```



\## 🔗 Token References \& Aliases



\### Using Token References

Tokens can reference other tokens using the `{}` syntax:



```json

{

&nbsp; "design": {

&nbsp;   "colors": {

&nbsp;     "text": {

&nbsp;       "primary": { "$value": "{design.colors.gray.900}" },

&nbsp;       "secondary": { "$value": "{design.colors.gray.600}" }

&nbsp;     }

&nbsp;   }

&nbsp; }

}

```



\### Semantic Aliases

Create meaningful names that reference base tokens:



```json

{

&nbsp; "semantic": {

&nbsp;   "prayer": {

&nbsp;     "card": {

&nbsp;       "background": { "$value": "{design.colors.primary.50}" },

&nbsp;       "text": { "$value": "{design.colors.primary.900}" }

&nbsp;     }

&nbsp;   }

&nbsp; }

}

```



\## 📋 Token Types in Token Studio



| Token Type | Usage | Example |

|------------|-------|---------|

| Color | Colors and gradients | `#4caf50` |

| Typography | Text styles | Font, size, weight |

| Dimension | Spacing, sizing | `16px`, `1rem` |

| Number | Numeric values | `3`, `1.5` |

| String | Text content | `"Home Screen"` |

| Boolean | True/false values | `true` |

| Asset | URLs, file paths | `"icon.svg"` |



\## 🎯 Token Set Order \& Inheritance



\### Recommended Order

```javascript

tokenSetOrder: \[

&nbsp; // 1. Foundation (loaded first)

&nbsp; "design",           // Base design tokens

&nbsp; 

&nbsp; // 2. Reference Data

&nbsp; "islamic-data",     // Static reference data

&nbsp; 

&nbsp; // 3. Content

&nbsp; "awrad",           // Prayer content

&nbsp; "localization",    // UI translations

&nbsp; 

&nbsp; // 4. Features

&nbsp; "notifications",   // Dynamic content

&nbsp; "features"         // App configuration

]

```



\### Inheritance Flow

```

design (base) 

&nbsp; ↓

islamic-data (references design)

&nbsp; ↓

awrad (uses design + islamic-data)

&nbsp; ↓

notifications (uses all above)

```



\## 🔍 Token Search \& Filtering



\### In Token Studio

Use search patterns:

\- `design.colors` - All color tokens

\- `awrad.morning` - All morning prayers

\- `.translation.en` - All English translations

\- `semantic.` - All semantic tokens



\### In Code

```javascript

// Filter tokens by category

const morningPrayers = tokens.awrad.morning;

const primaryColors = tokens.design.colors.primary;

const englishUI = tokens.ui.screens.home.title.en;

```



\## 📱 Platform-Specific Tokens



\### Responsive Tokens

```json

{

&nbsp; "design": {

&nbsp;   "spacing": {

&nbsp;     "mobile": { "$value": "16px" },

&nbsp;     "tablet": { "$value": "24px" },

&nbsp;     "desktop": { "$value": "32px" }

&nbsp;   }

&nbsp; }

}

```



\### Platform Overrides

```json

{

&nbsp; "design": {

&nbsp;   "typography": {

&nbsp;     "body": {

&nbsp;       "$value": "16px",

&nbsp;       "$extensions": {

&nbsp;         "platform": {

&nbsp;           "ios": { "$value": "17px" },

&nbsp;           "android": { "$value": "16px" }

&nbsp;         }

&nbsp;       }

&nbsp;     }

&nbsp;   }

&nbsp; }

}

```



\## 🏷 Metadata Structure



\### Token-Level Metadata

```json

{

&nbsp; "token\_name": {

&nbsp;   "$value": "token\_value",

&nbsp;   "$description": "Token purpose and usage",

&nbsp;   "$extensions": {

&nbsp;     "created": "2024-01-15",

&nbsp;     "author": "Designer Name",

&nbsp;     "category": "foundation"

&nbsp;   }

&nbsp; }

}

```



\### File-Level Metadata

```json

{

&nbsp; "$metadata": {

&nbsp;   "version": "1.0.0",

&nbsp;   "lastModified": "2024-01-15",

&nbsp;   "author": "Mihrab Team",

&nbsp;   "languages": \["ar", "en", "id", "..."],

&nbsp;   "tokenCount": 150

&nbsp; }

}

```



\## 🔄 Token Versioning



\### Version Tags

\- `v1.0.0` - Initial release

\- `v1.1.0` - New features

\- `v1.0.1` - Bug fixes



\### Deprecation Pattern

```json

{

&nbsp; "old\_token": {

&nbsp;   "$value": "#000",

&nbsp;   "$deprecated": true,

&nbsp;   "$deprecatedMessage": "Use design.colors.text.primary instead"

&nbsp; }

}

```



\## 📊 Token Statistics Summary



| Category | Token Count | Multilingual | File Size |

|----------|-------------|--------------|-----------|

| Colors | 50+ | No | ~15KB |

| Typography | 30+ | No | ~10KB |

| Spacing | 20+ | No | ~5KB |

| UI Strings | 200+ | Yes (12) | ~300KB |

| Awrad | 400+ | Yes (12) | ~2MB |

| Notifications | 100+ | Yes (12) | ~200KB |



\## 🛠 Best Practices



\### DO's ✅

\- Use semantic naming

\- Create aliases for common use cases

\- Document token purpose

\- Follow naming conventions

\- Use references to maintain consistency



\### DON'Ts ❌

\- Hard-code values

\- Create circular references

\- Use spaces in token names

\- Mix concerns in one token set

\- Skip documentation



\## 🚀 Advanced Usage



\### Conditional Tokens

```json

{

&nbsp; "theme": {

&nbsp;   "dark": {

&nbsp;     "background": { "$value": "#000000" }

&nbsp;   },

&nbsp;   "light": {

&nbsp;     "background": { "$value": "#ffffff" }

&nbsp;   }

&nbsp; }

}

```



\### Computed Values

```json

{

&nbsp; "spacing": {

&nbsp;   "base": { "$value": "4px" },

&nbsp;   "double": { "$value": "calc({spacing.base} \* 2)" }

&nbsp; }

}

```



\## 📚 Additional Resources



\- \[Token Studio Documentation](https://docs.tokens.studio)

\- \[Design Tokens W3C Spec](https://www.w3.org/community/design-tokens/)

\- \[Figma Variables Guide](https://help.figma.com/hc/en-us/articles/15339657135383)



---



Last Updated: January 2024

Version: 1.0.0

