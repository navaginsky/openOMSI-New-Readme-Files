<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logos/openomsi-wordmark-light.svg">
    <img alt="openOMSI" src="assets/logos/openomsi-wordmark-dark.svg" width="420">
  </picture>
</p>

<p align="center">
  <a href="https://github.com/turbo-devv/openOMSI/releases/latest"><img alt="Версія" src="https://img.shields.io/github/v/release/turbo-devv/openOMSI?label=version&color=f47f30&style=for-the-badge"></a>
  <a href="https://github.com/turbo-devv/openOMSI/actions/workflows/release.yml"><img alt="Збірка" src="https://img.shields.io/github/actions/workflow/status/turbo-devv/openOMSI/release.yml?branch=main&style=for-the-badge&label=build"></a>
  <a href="https://turbo-devv.github.io/openOMSI/"><img alt="Документація" src="https://img.shields.io/badge/docs-website-2d3138?style=for-the-badge"></a>
  <a href="https://discord.gg/VG2EKVafYG"><img alt="Discord" src="https://img.shields.io/badge/discord-join%20us-5865F2?style=for-the-badge&logo=discord&logoColor=white"></a>
  <a href="https://buymeacoffee.com/usonskyyy"><img alt="Buy me a coffee" src="https://img.shields.io/badge/buy%20me%20a%20coffee-support-ffdd00?style=for-the-badge&logo=buymeacoffee&logoColor=black"></a>
  <a href="https://ko-fi.com/usonance"><img alt="Ko-fi" src="https://img.shields.io/badge/ko--fi-support-29abe0?style=for-the-badge&logo=kofi&logoColor=white"></a>
  <a href="LICENSE"><img alt="Ліцензія" src="https://img.shields.io/github/license/turbo-devv/openOMSI?style=for-the-badge"></a>
</p>

> [!WARNING]
> **Ранній реліз. Очікуйте на баги.** openOMSI перебуває на ранній стадії розробки: щось
> може бути відсутнім, зламаним або змінюватися між версіями. Будь ласка, повідомляйте про
> проблеми в [Issues](https://github.com/turbo-devv/openOMSI/issues) або на нашому
> [Discord-сервері](https://discord.gg/VG2EKVafYG).

**openOMSI** — це відтворення з нуля симулятора автобуса **OMSI 2**, написане на Rust:
64-бітний, багатопотоковий, із сучасним рендерером (Metal / Vulkan / DirectX 12 через wgpu),
повністю сумісний із наявними картами, автобусами, декораціями та модами.

> [!IMPORTANT]
> **openOMSI потребує оригінальної копії OMSI 2.** Він не містить власного ігрового
> контенту: він грає на картах, транспорті та інших файлах встановленої OMSI 2 і
> **не запуститься без неї**.

## Завантажити

Кожен коміт у `main` збирається GitHub Actions і публікується на сторінці
[**Releases**](https://github.com/turbo-devv/openOMSI/releases):

| Платформа | Файл |
| --- | --- |
| Windows x64 / ARM64 | `openOMSI-<версія>-windows-x64.zip` / `-windows-arm64.zip` — запустити `openomsi.exe` |
| macOS (Apple silicon / Intel) | `openOMSI-<версія>-macos-arm64.zip` / `-macos-x64.zip` — відкрити `openOMSI.app` |
| Linux x64 / ARM64 | `openOMSI-<версія>-linux-x64.zip` / `-linux-arm64.zip` — запустити `openomsi` |
| Android (arm64, 8.0+) | `openOMSI-<версія>-android-arm64.apk` — див. [docs/ANDROID.md](docs/ANDROID.md) |
| Виділений сервер | `openOMSI-<версія>-server-linux-x64.zip` (також `-linux-arm64`, `-windows-x64`, `-windows-arm64`) — див. [docs/SERVER.md](docs/SERVER.md) |

Запустіть гру, один раз укажіть лаунчеру папку з OMSI 2, виберіть карту, автобус і наряд —
і їдьте. Моди кладуться в папку поруч із грою (або встановлюються через сторінку
**Mods** у лаунчері); оригінальна установка ніколи не змінюється.

Починаючи з 0.1.7 лаунчер оновлюється сам: коли виходить нова версія, він запитує при
запуску і, з вашої згоди, завантажує її, замінює програму та запускається знову (на
Android — через системний інсталятор). Settings → Updates вимикає перевірку або
встановлює без запитань.

## Встановлення

**Вам потрібна встановлена OMSI 2** (Steam або retail, будь-яка версія) з її стандартним
контентом — картами Grundorf і Berlin-Spandau та стандартними автобусами (MAN SD200/SD202,
NL). openOMSI не приносить власного ігрового контенту; він грає на картах, автобусах
і модах оригіналу.

1. **Завантажте** файл для вашої системи зі сторінки
   [Releases](https://github.com/turbo-devv/openOMSI/releases) (таблиця вище) і розпакуйте
   його в окрему папку, у яку ви можете писати — у Документи, ігрову папку або в
   саму папку OMSI 2. Не в `Program Files`: там лаунчер не зміг би оновлювати себе.
2. **Запустіть.**
   * **Windows:** `openomsi.exe`. Windows SmartScreen може попередити про невідомий
     застосунок: *Докладніше* → *Виконати все одно*.
   * **macOS:** відкрийте `openOMSI.app`. Першого разу macOS може відмовитися відкрити
     застосунок з інтернету: правий клік → *Відкрити* → *Відкрити*, або один раз виконайте
     `xattr -dr com.apple.quarantine /path/to/openOMSI.app`.
   * **Linux:** `./openomsi` (виконайте `chmod +x openomsi`, якщо не запускається). Потрібен
     драйвер Vulkan або OpenGL (Mesa: `mesa-vulkan-drivers`, або драйвер вашого
     виробника GPU).
   * **Android:** див. [docs/ANDROID.md](docs/ANDROID.md) — папка OMSI 2 спочатку копіюється
     на телефон.
3. **Укажіть шлях до OMSI 2.** Лаунчер зазвичай знаходить установку сам (бібліотеки Steam,
   звичайні папки). Якщо ні — відкрийте **Setup** і виберіть папку OMSI 2 — ту, в якій
   лежать `Omsi.exe`, `maps` і `Vehicles` (папку або сам `Omsi.exe`) — і натисніть **Save**.
   Версія зі Steam знаходиться в `…\Steam\steamapps\common\OMSI 2`.
4. **Поїхали:** виберіть автобус, карту та наряд на сторінці **Drive** і натисніть
   **Start the duty**.

**Моди** встановлюються на сторінці **Mods** (папка або `.zip`, або перетягуванням у
вікно) чи розміщенням їх у папці `Mods` поруч із грою; папка OMSI 2 ніколи не змінюється.

### Коли щось іде не так

* **«The original OMSI 2 was not found»** — виберіть папку в Setup (крок 3); повідомлення
  скаже, чого бракує у вибраній папці.
* **Гра закривається через кілька секунд, або «the graphics device was lost»** —
  оновіть драйвер графіки (власний від NVIDIA, AMD або Intel, а не той, що
  встановлює Windows). У Windows також можна переключитися на DirectX 12:
  Settings → Graphics API (лаунчер пропонує це після такого вильоту).
* **Стара графічна карта** (без Vulkan): openOMSI сам переключається на DirectX 12, а
  потім на OpenGL; Settings → Graphics API вибирає один.
* **Застрягли біля мосту або невидимої стіни** на мод-карті: Esc → Options → *Collisions with
  objects* вимикає колізії з об'єктами карти (це є і в Settings).
* **Мультиплеєр: ви не зустрічаєте інших** — обом гравцям потрібна карта хоста (карта в
  папці OMSI 2 не передається; карта зі сторінки Mods — передається). Гра, що приєднується,
  сама переключається на карту хоста і повідомляє в HUD, якщо вона не встановлена.
* **Клавіші роблять не те, що ви задали:** Controls — сторінка показує, які клавіші
  водіння використовуються; змінена там клавіша набуває чинності одразу.
* **Усе інше:** коли гра завершується з помилкою, лаунчер показує її з кнопками
  *Copy report* і *Report on GitHub*. Логи знаходяться в `~/.openomsi` (Windows:
  `C:\Users\<ви>\.openomsi`), `game.log` — за останню гру.

## Цілі

1. **Поведінка 1:1.** Кожен формат контенту оригіналу — карти, сплайни, об'єкти декорацій,
   транспорт, скрипти, розклади, HOF-файли, шрифти, погода, квитки, ситуації, плагіни —
   завантажується і поводиться точно як в OMSI 2.2.032. Наявні карти та моди працюють
   без змін.
2. **Жодного оригінального коду чи ассетів.** Нічого з оригіналу не копіюється; формати
   описані в [docs/FORMATS.md](docs/FORMATS.md).
3. **Кращий движок.** 64-бітний адресний простір, потокове завантаження та завантаження
   текстур у робочих потоках, без ліміту в 2 ГБ, без однопотокових затримок, LAN-мультиплеєр
   і виділений сервер.

## Документація

Повна документація на сайті: **https://turbo-devv.github.io/openOMSI/**. Ті самі сторінки
лежать у [`docs/`](docs):

| Документ | Що в ньому |
| --- | --- |
| [Посібник користувача](docs/USER_GUIDE.md) | запуск, керування, лаунчер, налаштування, моди, LAN-гра, налагоджувальні перемикачі |
| [Віртуальна реальність](docs/VR.md) | налаштування OpenXR, VR-налаштування та керування в Windows |
| [Android](docs/ANDROID.md) | мобільна версія: встановлення, сенсорне керування, збірка APK |
| [Модифікація](docs/MODDING.md) | зняті обмеження для модерів: більше внутрішніх вогнів, більші текстури, доповнення, які OMSI 2 ігнорує |
| [PBR-матеріали](docs/PBR.md) | карти normal, roughness, metalness та occlusion для модів |
| [Збірка](docs/BUILDING.md) | збірка з вихідних кодів на macOS, Windows, Linux та Android |
| [Формати контенту](docs/FORMATS.md) | кожен формат файлів OMSI 2 |
| [Архітектура](docs/ARCHITECTURE.md) | крейти, багатопотоковість, рендерер, план розвитку |
| [Маршрути](docs/ROUTES.md) | як оригінал працює з розкладами, chrono, HOF, IBIS |
| [Плагіни](docs/PLUGINS.md) | Lua-плагіни (API та приклади), DLL-плагіни OMSI та 32-бітний хост плагінів |
| [Виділений сервер](docs/SERVER.md) | хостинг сесії без вікна |
| [Версіонування та релізи](docs/VERSIONING.md) | схема `MAJOR.MINOR.COMMIT` та CI |
| [Список змін](CHANGELOG.md) | що змінилося в кожній версії |

## Збірка з вихідних кодів

```sh
git clone https://github.com/turbo-devv/openOMSI.git && cd openOMSI
scripts/build-macos.sh        # macOS   → dist/macos/openOMSI.app
scripts\build-windows.cmd     # Windows → dist\windows\openomsi.exe
scripts/build-linux.sh        # Linux   → dist/linux/openomsi
scripts/build-android.sh      # Android → dist/android/openOMSI-<версія>.apk
scripts/build-server.sh       # сервер  → dist/server
