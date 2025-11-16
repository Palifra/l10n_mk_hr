# Macedonia - HR Translations / Превод на Вработени

Odoo 18 module for Macedonian translations of the HR (Human Resources/Employees) module.

## Features / Функционалности

This module provides comprehensive Macedonian translations for all HR-related terms:

### Main Entities / Главни ентитети
- **Employee** (Вработен)
- **Department** (Оддел)
- **Job Position** (Работно место)
- **Contract Type** (Тип на договор)
- **Work Location** (Локација на работа)
- **Employee Tags** (Ознаки на вработени)

### Employee Information / Информации за вработен
- **Work Information**: Work Email (Работен е-маил), Work Phone (Работен телефон), Work Mobile (Работен мобилен), Work Address (Работна адреса)
- **Private Information**: Private Email (Приватен е-маил), Private Phone (Приватен телефон), Private Address (Приватна адреса)
- **Personal Details**: Date of Birth (Датум на раѓање), Place of Birth (Место на раѓање), Gender (Пол), Nationality (Националност)
- **Marital Status**: Single (Неженет/Немажена), Married (Женет/Мажена), Divorced (Разведен/а), Widower (Вдовец/Вдовица)
- **Education**: Certificate Level (Ниво на образование), Field of Study (Област на студирање), School (Училиште)
- **Documents**: Identification No (Број на лична карта), Passport No (Број на пасош), Work Permit (Работна дозвола), Visa (Виза)

### HR Features / HR функционалности
- **Resume/CV** (CV/Биографија)
- **Skills** (Вештини)
- **Manager** (Менаџер)
- **Coach/Trainer** (Тренер)
- **Subordinates** (Подредени)
- **Presence Status** (Статус на присуство)
- **Activities** (Активности)

### Employee Types / Типови на вработени
- Employee (Вработен)
- Student (Студент)
- Trainee (Практикант)
- Contractor (Изведувач)
- Freelancer (Фриленсер)

### Contract Types / Типови на договори
- CDD - Fixed-term (Договор на определено време)
- CDI - Permanent (Договор на неопределено време)
- Internship (Пракса)
- Apprenticeship (Чиракување)

## Installation / Инсталација

### Requirements
- Odoo 18.0
- HR module (`hr`) must be installed

### Standard Installation

1. Copy the `l10n_mk_hr` folder to your Odoo addons directory
2. Update the module list in Odoo
3. Install "Macedonia - HR Translations" from Apps menu

### Docker Installation

```bash
# Update module list
docker exec -i odoo_server odoo shell -d YOUR_DATABASE --no-http << 'EOF'
env['ir.module.module'].update_list()
env.cr.commit()
EOF

# Install module
docker exec -i odoo_server odoo shell -d YOUR_DATABASE --no-http << 'EOF'
module = env['ir.module.module'].search([('name', '=', 'l10n_mk_hr')])
module.button_immediate_install()
env.cr.commit()
EOF
```

## Usage / Употреба

1. After installation, ensure your user language is set to **Macedonian (mk_MK)**
2. Go to **Settings > Users & Companies > Users**
3. Edit your user and set **Language** to **Macedonian / македонски јазик**
4. Refresh the page
5. Navigate to **Employees** module - all terms should now appear in Macedonian

### Screenshots

The translated interface includes:
- Employee list view (Листа на вработени)
- Employee form view (Формулар на вработен)
- Department tree (Дрво на оддели)
- Job positions (Работни места)
- Employee tags (Ознаки на вработени)

## Translation Coverage / Покриеност на превод

The module provides translations for:
- Field labels and descriptions
- Menu items
- Action buttons (Save, Edit, Discard, Archive)
- Selection options (Gender, Marital Status, Employee Type, etc.)
- Help texts and tooltips
- Search filters and group by options
- Status values

### Total translations: **300+** terms

## Technical Details / Технички детали

- **Module Name:** `l10n_mk_hr`
- **Version:** 18.0.1.0.0
- **Category:** Human Resources/Localization
- **License:** LGPL-3
- **Dependencies:** `hr`

### File Structure

```
l10n_mk_hr/
├── __init__.py
├── __manifest__.py
├── README.md
└── i18n/
    └── mk.po          # Macedonian translations (300+ terms)
```

### Translation File Format

The `mk.po` file follows the standard GNU gettext PO format:

```po
#. module: hr
#: model:ir.model.fields,field_description:hr.field_hr_employee__name
msgid "Employee Name"
msgstr "Име на вработен"
```

## Customization / Прилагодување

### Adding More Translations

To add or modify translations:

1. Edit `i18n/mk.po` file
2. Add new entries in the format:
```po
#. module: hr
msgid "Original English Text"
msgstr "Превод на македонски"
```
3. Upgrade the module:
```bash
docker exec -i odoo_server odoo shell -d YOUR_DATABASE --no-http << 'EOF'
module = env['ir.module.module'].search([('name', '=', 'l10n_mk_hr')])
module.button_immediate_upgrade()
env.cr.commit()
EOF
```

### Exporting All Terms

To export all translatable terms from the HR module:

```python
# In Odoo shell
from odoo.tools import trans_export
# Use Odoo's built-in export functionality
```

## Dependencies / Зависности

- `hr` (Odoo Human Resources module)

## Changelog / Историја на промени

### Version 18.0.1.0.0
- Initial release
- Comprehensive Macedonian translations for HR module
- 300+ translated terms covering all major HR functionality
- Support for employee management, departments, job positions
- Personal information, education, documents translations
- Contract types and employee status translations
- Skills and resume translations

## Known Issues / Познати проблеми

- Some technical terms may need context-specific adjustments
- Field descriptions in Python code are translated only if marked for translation

## Support / Поддршка

For issues and feature requests, please create an issue on GitHub.

## Author / Автор

**ЕСКОН-ИНЖЕНЕРИНГ ДООЕЛ Струмица**

- Website: https://www.eskon.com.mk
- Email: info@eskon.com.mk
- GitHub: https://github.com/Palifra

## Related Modules / Поврзани модули

- [l10n_mk](https://github.com/Palifra/l10n_mk) - Macedonian Chart of Accounts
- [l10n_mk_delivery_note](https://github.com/Palifra/l10n_mk_delivery_note) - Macedonian Delivery Notes
- [l10n_mk_reverse](https://github.com/Palifra/l10n_mk_reverse) - Equipment Loan Management
- [l10n_mk_project](https://github.com/Palifra/l10n_mk_project) - Macedonian Project Management
- [l10n_mk_fleet](https://github.com/Palifra/l10n_mk_fleet) - Macedonian Fleet Management
- [l10n_mk_inventory](https://github.com/Palifra/l10n_mk_inventory) - Macedonian Inventory
- [l10n_mk_invoicing](https://github.com/Palifra/l10n_mk_invoicing) - Macedonian Invoicing

## License / Лиценца

This module is licensed under LGPL-3.

---

**Совет:** За најдобро искуство, поставете го јазикот на целиот систем на македонски и рестартирајте го серверот после инсталацијата на модулот.
