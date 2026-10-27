# Darkside Adventure (NeoForge)

Персональная сборка Minecraft с упором на атмосферу, исследования, Create/Aeronautics и эффектную графику.

| | |
|---|---|
| Minecraft | **1.21.1** |
| Загрузчик | **NeoForge 21.1.264** |
| Лаунчер | TLauncher (offline) |
| RAM | рекомендуется 6–8 ГБ |
| Модов | 30 |
| Шейдерпаки | 10 |

## Состав

**Техно-креатив**
- Create 6.0.10 (+ Flywheel), Create Aeronautics (bundled), Create Big Cannons, Create Diesel Generators, Create Interiors, Ritchie's Projectile Lib
- FTB Chunks / Library / Quests / Teams + FTB Quest Translation

**Графика и рендер**
- Sodium (neoforge-порт), Iris 1.8.14-beta.1, Distant Horizons 3.3.3, Sable 2.0.6
- Sodium Dynamic Lights, EntityCulling, NeoForgeGGTU (Resolution Scale)

**Оптимизация**
- Lithium, FerriteCore, ModernFix

**Интерфейс и утилиты**
- JEI, Journeymap, Sophisticated Core / Backpacks, Waystones, Cloth Config, Balm, Architectury, Mezz Config

**Ресурспаки:** Enchantment Glows, Fresh Animations
**Шейдеры:** BSL, Noble, Horizon Reimagined, Vivid Horizon, MakeUp UltraFast, Aerial, Realistic

## Что лежит в репозитории

```
mods/           — сами .jar (30 шт.)
config/         — все конфиги модов
shaderpacks/    — шейдерпаки
resourcepacks/  — ресурспаки
options.txt     — графика, кейбинды, язык (ru_ru)
mods-manifest.txt — список модов с SHA-256 для проверки целостности
```

## Чего здесь нет и почему

`.gitignore` намеренно исключает всё личное и генерируемое при запуске:

- `saves/`, `journeymap/`, `schematics/` — миры и карты
- `logs/`, `crash-reports/`, `.mixin.out/` — логи и отчёты
- `natives/`, `.sable/`, `downloads/`, `server-resource-packs/` — кэш и нативные библиотеки
- `servers.dat`, `usercache.json`, `usernamecache.json`, `TLauncherAdditional.json` — аккаунт и список серверов

Дополнительно включён pre-commit хук (`.githooks/pre-commit`), который перед каждым коммитом вычищает `lastServer:` из `options.txt` — чтобы адрес сервера не утёк. После клонирования включить: `git config core.hooksPath .githooks`.

## Как восстановить сборку

1. Установить Minecraft **1.21.1** и **NeoForge 21.1.264** в отдельный профиль.
2. Скопировать в папку профиля содержимое этого репозитория (кроме `.git`, `.gitignore`, `README.md`, `AGENTS.md`).
3. Проверить целостность модов по `mods-manifest.txt` (по желанию).
4. Запустить игру, в настройках выбрать шейдерпак из `shaderpacks/`.
