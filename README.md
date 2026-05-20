# AI Business Cases

> AI-powered business process automation: real-world cases from 18+ years in commercial operations

---

## 👤 Автор

**Андрей Рыкунов** — заместитель коммерческого директора, 18+ лет в управлении продажами и внедрении CRM-систем.

- Руководил отделом до 85 человек, оборот >1 млрд руб.
- Внедрял MS Dynamics, 1C CRM, amoCRM
- Строил дашборды Power BI с 2016 года
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
│   │   └── metallprofil-price-tracker/
│   ├── power-bi-dashboards/     # Управленческие BI-дашборды
│   │   └── revenue-dashboard/
│   └── ai-automation/           # AI/N8N-автоматизации
│       ├── climate-sp-assistant/
│       └── meeting-audio-tasks-agent/
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
| 8 | [Автоматизация управленческой отчетности в Power BI](./cases/power-bi-dashboards/revenue-dashboard/) | ✅ Готов | Power BI, DAX | Screenshots |
| 9 | [Telegram-бот по климатическим данным СП](./cases/ai-automation/climate-sp-assistant/) | ✅ Готов | n8n, Telegram Bot API, JavaScript, JSON | [Demo App](https://kilevoy.github.io/climate-sp-atlas/) · [Data](https://kilevoy.github.io/climate-sp-atlas/settlements-climate.json) |
| 10 | [КМД → ведомость металла ИНСИ](./cases/business-calculators/metal-spec-parser-insi/) | 🚧 В разработке | Python, FastAPI, React, TypeScript, PDF/Excel parsing | [Code](https://github.com/kilevoy/KMD/tree/main/cases/metal-spec-parser-insi) |
| 11 | [ИИ-агент планерок: аудио → поручения → контроль задач](./cases/ai-automation/meeting-audio-tasks-agent/) | 🚧 В разработке | n8n, Telegram Bot API, OpenAI, Google Sheets | n8n Workflow · Portfolio case |

---

## 🛠 Стек технологий

**Инженерные и бизнес-инструменты:**
- Power BI, DAX, Power Query
- Excel-калькуляторы и workbook-backed reference data
- Нормативные справочники и расчетные таблицы
- Коммерческие расчеты, спецификации, подготовка КП

**Разработка:**
- TypeScript / JavaScript
- React / Vite
- HTML / CSS / PWA
- Python-скрипты для извлечения и сверки данных
- PDF parsing, JSON, локальная автоматизация

**Проверка и публикация:**
- Vitest / Playwright
- JSON-справочники и generated reference modules
- GitHub Pages
- GitHub Actions

---

## 🚀 Цель

Показать подход к автоматизации бизнес-процессов на стыке коммерческой работы, инженерных расчетов и разработки: переводить ручные Excel-сценарии, справочники и повторяемые расчеты в понятные веб-инструменты, которые ускоряют подготовку КП, снижают риск ошибок и стандартизируют работу команды.

---

## 📄 Лицензия

MIT — код и подходы можно свободно использовать с указанием автора.
