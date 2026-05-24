# AI Business Cases

> AI-powered business process automation: real-world cases from 18+ years in commercial operations

---

## 👤 Автор

**Андрей Рыкунов** — заместитель коммерческого директора, 18+ лет в управлении продажами и внедрении CRM-систем.

- Руководил отделом до 85 человек, оборот >1 млрд руб.
- Внедрял MS Dynamics, 1C CRM, amoCRM
- Строил управленческие дашборды продаж, маржи, склада и дебиторки
- Разрабатывал калькуляторы и сервисы, ускоряющие подготовку КП на 30%
- Сейчас: переход в AI-автоматизацию бизнес-процессов

**Контакты:** rykunov@gmail.com | [Резюме](https://kilevoy.github.io/hh/career-ops/)

---

## 📁 Структура репозитория

```
ai-business-cases/
├── cases/
│   ├── business-calculators/    # Инженерные и коммерческие инструменты
│   │   ├── lstk-profile-calculator/
│   │   ├── coating-processing-calculator/
│   │   ├── facade-cassette-calculator/
│   │   ├── insi-metalcalc/
│   │   ├── steel-building-calc/
│   │   ├── climate-sp-atlas/
│   │   ├── metal-spec-parser-insi/
│   │   ├── metallprofil-price-tracker/
│   │   └── one-chip-parser/
│   ├── power-bi-dashboards/     # Исторические BI-дашборды и React-дашборды
│   │   ├── revenue-dashboard/
│   │   └── b2b-auto-parts-dashboard/
│   └── ai-automation/           # AI/N8N-автоматизации
│       ├── climate-sp-assistant/
│       ├── meeting-audio-tasks-agent/
│       └── contract-risk-auditor/
├── assets/                      # Скриншоты, диаграммы, превью
├── docs/                        # Дополнительная документация
└── README.md
```

---

## 📊 Кейсы

| # | Кейс | Статус | Технологии | Ссылка |
|---|------|--------|-----------|--------|
| 1 | [Автоматизация подбора и расчета ЛСТК-профилей](./cases/business-calculators/lstk-profile-calculator/) | ✅ Готов | TypeScript, React, Vite, Tailwind | [Demo](https://kilevoy.github.io/gps/) · [Code](https://github.com/kilevoy/gps) |
| 2 | [Автоматизация расчета стоимости покрытия и переработки](./cases/business-calculators/coating-processing-calculator/) | ✅ Готов | JavaScript, CSS, LocalStorage | [Demo](https://kilevoy.github.io/coating-processing-calculator/) · [Code](https://github.com/kilevoy/coating-processing-calculator) |
| 3 | [Калькулятор фасадных кассет и НФС](./cases/business-calculators/facade-cassette-calculator/) | ✅ MVP | TypeScript, React, Vite, Excel import | [Demo](https://kilevoy.github.io/fasad/) · [Code](https://github.com/kilevoy/fasad) |
| 4 | [Автоматизация подбора металлокаркаса и ограждающих конструкций](./cases/business-calculators/insi-metalcalc/) | ✅ Готов | TypeScript, React, Vite, Vitest, Playwright | [Demo](https://kilevoy.github.io/insi-next/) · [Code](https://github.com/kilevoy/insi-next) |
| 5 | [Автоматизация подбора стального каркаса промышленных зданий](./cases/business-calculators/steel-building-calc/) | 🚧 В разработке | TypeScript, React, Vite, Vitest, HyperFormula | [Demo](https://kilevoy.github.io/steel-building-calc/) · [Code](https://github.com/kilevoy/steel-building-calc) |
| 6 | [Автоматизация поиска климатических данных по СП](./cases/business-calculators/climate-sp-atlas/) | ✅ Готов | HTML, CSS, JavaScript, JSON, PWA | [Demo](https://kilevoy.github.io/climate-sp-atlas/) · [Code](https://github.com/kilevoy/climate-sp-atlas) |
| 7 | [Автоматизация обновления и сравнения прайсов Металл Профиль](./cases/business-calculators/metallprofil-price-tracker/) | ✅ Готов | Python, PyMuPDF, HTML, CSS, JavaScript, JSON | [Demo](https://kilevoy.github.io/-metallprofil-price-tracker/) · [Code](https://github.com/kilevoy/-metallprofil-price-tracker) |
| 8 | [Автоматизация управленческой отчетности](./cases/power-bi-dashboards/revenue-dashboard/) | ✅ Готов | BI, DAX, Power Query | Screenshots |
| 9 | [Telegram-бот по климатическим данным СП](./cases/ai-automation/climate-sp-assistant/) | ✅ Готов | n8n, Telegram Bot API, JavaScript, JSON | [Demo App](https://kilevoy.github.io/climate-sp-atlas/) · [Data](https://kilevoy.github.io/climate-sp-atlas/settlements-climate.json) |
| 10 | [КМД → ведомость металла ИНСИ](./cases/business-calculators/metal-spec-parser-insi/) | 🚧 В разработке | Python, FastAPI, React, TypeScript, PDF/Excel parsing | [Code](https://github.com/kilevoy/KMD/tree/main/cases/metal-spec-parser-insi) |
| 11 | [ИИ-агент планерок: расшифровка → поручения → контроль задач](./cases/ai-automation/meeting-audio-tasks-agent/) | 🚧 В разработке | n8n, Telegram Bot API, OpenRouter, Google Sheets | n8n Workflow · Portfolio case |
| 12 | [B2B-дашборд продаж, маржи, склада и дебиторки автозапчастей](./cases/power-bi-dashboards/b2b-auto-parts-dashboard/) | ✅ Готов | TypeScript, React, Vite, Tailwind, Recharts | [Demo](https://kilevoy.github.io/dashboard/) · [Source](./cases/power-bi-dashboards/b2b-auto-parts-dashboard/app/) · [Deploy repo](https://github.com/kilevoy/dashboard) |
| 13 | [AI Contract Risk Auditor: Telegram-бот для юридического риск-аудита договоров](./cases/ai-automation/contract-risk-auditor/) | ✅ MVP | n8n, Telegram Bot API, OpenRouter, JavaScript, Markdown | n8n Workflow · Portfolio case |
| 14 | [Автоматизация конкурентной разведки и парсинга e-commerce каталога](./cases/business-calculators/one-chip-parser/) | ✅ Готов | Python, Requests, BeautifulSoup, Tkinter, PyInstaller | [Demo](https://kilevoy.github.io/one-chip-parser/) · [Code](https://github.com/kilevoy/one-chip-parser) |

---

## 🛠 Стек технологий

**Инженерные и бизнес-инструменты:**
- управленческие дашборды и коммерческая аналитика;
- Excel-калькуляторы и workbook-backed reference data;
- нормативные справочники и расчетные таблицы;
- коммерческие расчеты, спецификации, подготовка КП.

**Разработка:**
- TypeScript / JavaScript;
- React / Vite;
- HTML / CSS / PWA;
- Python-скрипты для извлечения и сверки данных;
- PDF parsing, JSON, локальная автоматизация.

**AI-автоматизация:**
- n8n Cloud;
- Telegram Bot API;
- OpenRouter / OpenAI-compatible API;
- LLM prompts, structured output, Markdown reports;
- Google Sheets и файловые workflow.

**Проверка и публикация:**
- Vitest / Playwright;
- JSON-справочники и generated reference modules;
- GitHub Pages;
- GitHub Actions.

---

## 🚀 Цель

Показать подход к автоматизации бизнес-процессов на стыке коммерческой работы, инженерных расчетов, AI-автоматизации и разработки: переводить ручные Excel-сценарии, справочники, договорные проверки и повторяемые расчеты в понятные инструменты, которые ускоряют подготовку КП, снижают риск ошибок и стандартизируют работу команды.

---

## 📄 Лицензия

MIT — код и подходы можно свободно использовать с указанием автора.