<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logos/openomsi-wordmark-light.svg">
    <img alt="openOMSI" src="assets/logos/openomsi-wordmark-dark.svg" width="420">
  </picture>
</p>

<p align="center">
  <a href="https://github.com/turbo-devv/openOMSI/releases/latest"><img alt="Версия" src="https://img.shields.io/github/v/release/turbo-devv/openOMSI?label=version&color=f47f30&style=for-the-badge"></a>
  <a href="https://github.com/turbo-devv/openOMSI/actions/workflows/release.yml"><img alt="Сборка" src="https://img.shields.io/github/actions/workflow/status/turbo-devv/openOMSI/release.yml?branch=main&style=for-the-badge&label=build"></a>
  <a href="https://turbo-devv.github.io/openOMSI/"><img alt="Документация" src="https://img.shields.io/badge/docs-website-2d3138?style=for-the-badge"></a>
  <a href="https://discord.gg/VG2EKVafYG"><img alt="Discord" src="https://img.shields.io/badge/discord-join%20us-5865F2?style=for-the-badge&logo=discord&logoColor=white"></a>
  <a href="https://buymeacoffee.com/usonskyyy"><img alt="Buy me a coffee" src="https://img.shields.io/badge/buy%20me%20a%20coffee-support-ffdd00?style=for-the-badge&logo=buymeacoffee&logoColor=black"></a>
  <a href="https://ko-fi.com/usonance"><img alt="Ko-fi" src="https://img.shields.io/badge/ko--fi-support-29abe0?style=for-the-badge&logo=kofi&logoColor=white"></a>
  <a href="LICENSE"><img alt="Лицензия" src="https://img.shields.io/github/license/turbo-devv/openOMSI?style=for-the-badge"></a>
</p>

> [!WARNING]
> **Ранний релиз. Ожидайте багов.** openOMSI находится на ранней стадии разработки: что-то
> может отсутствовать, быть сломанным или меняться между версиями. Пожалуйста, сообщайте о
> проблемах в [Issues](https://github.com/turbo-devv/openOMSI/issues) или в нашем
> [Discord-сервере](https://discord.gg/VG2EKVafYG).

**openOMSI** — это воссоздание с нуля симулятора автобуса **OMSI 2**, написанное на Rust:
64-битный, многопоточный, с современным рендерером (Metal / Vulkan / DirectX 12 через wgpu),
полностью совместимый с существующими картами, автобусами, декорациями и модами.

> [!IMPORTANT]
> **openOMSI требует оригинальной копии OMSI 2.** Он не содержит собственного игрового
> контента: он играет на картах, транспорте и других файлах установленной OMSI 2 и
> **не запустится без неё**.

## Скачать

Каждый коммит в `main` собирается GitHub Actions и публикуется на странице
[**Releases**](https://github.com/turbo-devv/openOMSI/releases):

| Платформа | Файл |
| --- | --- |
| Windows x64 / ARM64 | `openOMSI-<версия>-windows-x64.zip` / `-windows-arm64.zip` — запустить `openomsi.exe` |
| macOS (Apple silicon / Intel) | `openOMSI-<версия>-macos-arm64.zip` / `-macos-x64.zip` — открыть `openOMSI.app` |
| Linux x64 / ARM64 | `openOMSI-<версия>-linux-x64.zip` / `-linux-arm64.zip` — запустить `openomsi` |
| Android (arm64, 8.0+) | `openOMSI-<версия>-android-arm64.apk` — см. [docs/ANDROID.md](docs/ANDROID.md) |
| Выделенный сервер | `openOMSI-<версия>-server-linux-x64.zip` (также `-linux-arm64`, `-windows-x64`, `-windows-arm64`) — см. [docs/SERVER.md](docs/SERVER.md) |

Запустите игру, один раз укажите лаунчеру папку с OMSI 2, выберите карту, автобус и наряд —
и поезжайте. Моды кладутся в папку рядом с игрой (или устанавливаются через страницу
**Mods** в лаунчере); оригинальная установка никогда не изменяется.

Начиная с 0.1.7 лаунчер обновляется сам: когда выходит новая версия, он спрашивает при
запуске и, с вашего согласия, скачивает её, заменяет программу и запускается заново (на
Android — через системный установщик). Settings → Updates отключает проверку или
устанавливает без вопросов.

## Установка

**Вам нужна установленная OMSI 2** (Steam или retail, любая версия) с её стандартным
контентом — картами Grundorf и Berlin-Spandau и стандартными автобусами (MAN SD200/SD202,
NL). openOMSI не приносит собственного игрового контента; он играет на картах, автобусах
и модах оригинала.

1. **Скачайте** файл для вашей системы со страницы
   [Releases](https://github.com/turbo-devv/openOMSI/releases) (таблица выше) и распакуйте
   его в отдельную папку, в которую вы можете писать — в Документы, игровую папку или в
   саму папку OMSI 2. Не в `Program Files`: там лаунчер не смог бы обновлять себя.
2. **Запустите.**
   * **Windows:** `openomsi.exe`. Windows SmartScreen может предупредить о неизвестном
     приложении: *Подробнее* → *Выполнить в любом случае*.
   * **macOS:** откройте `openOMSI.app`. В первый раз macOS может отказаться открыть
     приложение из интернета: правый клик → *Открыть* → *Открыть*, или один раз выполните
     `xattr -dr com.apple.quarantine /path/to/openOMSI.app`.
   * **Linux:** `./openomsi` (выполните `chmod +x openomsi`, если не запускается). Нужен
     драйвер Vulkan или OpenGL (Mesa: `mesa-vulkan-drivers`, или драйвер вашего
     производителя GPU).
   * **Android:** см. [docs/ANDROID.md](docs/ANDROID.md) — папка OMSI 2 сначала копируется
     на телефон.
3. **Укажите путь к OMSI 2.** Лаунчер обычно находит установку сам (библиотеки Steam,
   обычные папки). Если нет — откройте **Setup** и выберите папку OMSI 2 — ту, в которой
   лежат `Omsi.exe`, `maps` и `Vehicles` (папку или сам `Omsi.exe`) — и нажмите **Save**.
   Версия из Steam находится в `…\Steam\steamapps\common\OMSI 2`.
4. **Поехали:** выберите автобус, карту и наряд на странице **Drive** и нажмите
   **Start the duty**.

**Моды** устанавливаются на странице **Mods** (папка или `.zip`, либо перетаскиванием в
окно) или помещением их в папку `Mods` рядом с игрой; папка OMSI 2 никогда не изменяется.

### Когда что-то идёт не так

* **«The original OMSI 2 was not found»** — выберите папку в Setup (шаг 3); сообщение
  скажет, чего не хватает в выбранной папке.
* **Игра закрывается через несколько секунд, или «the graphics device was lost»** —
  обновите драйвер графики (собственный от NVIDIA, AMD или Intel, а не тот, что
  устанавливает Windows). В Windows также можно переключиться на DirectX 12:
  Settings → Graphics API (лаунчер предлагает это после такого вылета).
* **Старая графическая карта** (без Vulkan): openOMSI сам переключается на DirectX 12, а
  затем на OpenGL; Settings → Graphics API выбирает один.
* **Застряли у моста или невидимой стены** на мод-карте: Esc → Options → *Collisions with
  objects* отключает коллизии с объектами карты (это есть и в Settings).
* **Мультиплеер: вы не встречаете других** — обоим игрокам нужна карта хоста (карта в
  папке OMSI 2 не передаётся; карта со страницы Mods — передаётся). Присоединяющаяся игра
  сама переключается на карту хоста и сообщает в HUD, если она не установлена.
* **Клавиши делают не то, что вы задали:** Controls — страница показывает, какие клавиши
  вождения используются; изменённая там клавиша вступает в силу сразу.
* **Всё остальное:** когда игра завершается с ошибкой, лаунчер показывает её с кнопками
  *Copy report* и *Report on GitHub*. Логи находятся в `~/.openomsi` (Windows:
  `C:\Users\<вы>\.openomsi`), `game.log` — за последнюю игру.

## Цели

1. **Поведение 1:1.** Каждый формат контента оригинала — карты, сплайны, объекты декораций,
   транспорт, скрипты, расписания, HOF-файлы, шрифты, погода, билеты, ситуации, плагины —
   загружается и ведёт себя точно как в OMSI 2.2.032. Существующие карты и моды работают
   без изменений.
2. **Никакого оригинального кода или ассетов.** Ничего из оригинала не копируется; форматы
   описаны в [docs/FORMATS.md](docs/FORMATS.md).
3. **Лучший движок.** 64-битное адресное пространство, потоковая загрузка и загрузка
   текстур в рабочих потоках, без лимита в 2 ГБ, без однопоточных задержек, LAN-мультиплеер
   и выделенный сервер.

## Документация

Полная документация на сайте: **https://turbo-devv.github.io/openOMSI/**. Те же страницы
лежат в [`docs/`](docs):

| Документ | Что в нём |
| --- | --- |
| [Руководство пользователя](docs/USER_GUIDE.md) | запуск, управление, лаунчер, настройки, моды, LAN-игра, отладочные переключатели |
| [Виртуальная реальность](docs/VR.md) | настройка OpenXR, VR-настройки и управление в Windows |
| [Android](docs/ANDROID.md) | мобильная версия: установка, сенсорное управление, сборка APK |
| [Моддинг](docs/MODDING.md) | снятые ограничения для моддеров: больше внутренних огней, крупнее текстуры, дополнения, которые OMSI 2 игнорирует |
| [PBR-материалы](docs/PBR.md) | карты normal, roughness, metalness и occlusion для модов |
| [Сборка](docs/BUILDING.md) | сборка из исходников на macOS, Windows, Linux и Android |
| [Форматы контента](docs/FORMATS.md) | каждый формат файлов OMSI 2 |
| [Архитектура](docs/ARCHITECTURE.md) | крейты, многопоточность, рендерер, план развития |
| [Маршруты](docs/ROUTES.md) | как оригинал работает с расписаниями, chrono, HOF, IBIS |
| [Плагины](docs/PLUGINS.md) | Lua-плагины (API и примеры), DLL-плагины OMSI и 32-битный хост плагинов |
| [Выделенный сервер](docs/SERVER.md) | хостинг сессии без окна |
| [Версионирование и релизы](docs/VERSIONING.md) | схема `MAJOR.MINOR.COMMIT` и CI |
| [Список изменений](CHANGELOG.md) | что изменилось в каждой версии |

## Сборка из исходников

```sh
git clone https://github.com/turbo-devv/openOMSI.git && cd openOMSI
scripts/build-macos.sh        # macOS   → dist/macos/openOMSI.app
scripts\build-windows.cmd     # Windows → dist\windows\openomsi.exe
scripts/build-linux.sh        # Linux   → dist/linux/openomsi
scripts/build-android.sh      # Android → dist/android/openOMSI-<версия>.apk
scripts/build-server.sh       # сервер  → dist/server
