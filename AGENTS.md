# Контекст проекта: модпак «Darkside Adventure (Neoforge)»

## Что это
Рабочая папка профиля Minecraft (не git-репозиторий, не код-проект). Пользователь сам собирает
свою сборку поверх профиля TLauncher. OpenCode запущен здесь как «советчик по сборке».

## Железные факты
- Игра: **Minecraft 1.21.1 + NeoForge**, лаунчер **TLauncher** (пиратка/оффлайн — лицензионные
  сервисы типа Modrinth App недоступны, но **Modrinth API открыт и не требует лицензии**).
- Корень TLauncher: `%APPDATA%\.minecraft` (НЕ `~\.minecraft`!).
- Профиль сборки: `%APPDATA%\.minecraft\versions\Darkside Adventure (Neoforge)`.
  - mods: `<профиль>\mods` — **.jar-файлы лежат с URL-кодированием: «+» записан как `%2B`**,
    при работе с именами файлов учитывать.
  - настройки языка: `options.txt` → `lang:ru_ru` (уже русский).
- Направление сборки: китчен-синк с упором на **атмосферу, гигантскую генерацию мира,
  исследования, магию со свободой настройки и эффектными заклинаниями, квесты, Create Aeronautics**.

## Установленные моды (проверено в mods/)
Sodium 0.8.12 (neoforge-порт), Iris 1.8.14-beta.1, Sable 2.0.6, Distant Horizons 3.3.3,
Create 6.0.10 + Aeronautics + Big Cannons + Diesel Generators + Interiors + Ritchie's Projectile Lib,
Lithium, FerriteCore, ModernFix, EntityCulling, Sodium Dynamic Lights, Cloth Config,
Sophisticated Core/Backpacks, NeoForgeGGTU (Resolution Scale).
Тематика текущей базы: адвенчура/техно-креатив (небольшой пак, пользователь наращивает сам).

## Проверено по Modrinth API (1.21.1 + neoforge)
Есть: Tectonic, Terralith, Regions Unexplored, YUNG's Better *(кроме End City)*, Serene Seasons,
Create + Aeronautics, Ars Nouveau, Iron's Spells, Build A Spell, Mahou Tsukai, Cataclysm
(slug `l_enders-cataclysm`), The Aether, Ad Astra, Bountiful, ExtraQuests, Embeddium, Glowtone,
Naturalist, Environmental, Ecologics, Waystones, Comforts, Xaero's, JEI, Traveler's Backpack.
НЕТ (замена): Oculus→Glowtone/Iris · Botania→Ars · Alex's Mobs→Naturalist+Ecologics ·
Twilight Forest→Aether/Cataclysm · FTB Quests→ExtraQuests+Bountiful · Vibrant Visuals→шейдер-паки.
Slug'и, которые путаются: Cataclysm = `l_enders-cataclysm`, Iron's Spells = `irons-spells-n-spellbooks`.

## Незадача (в процессе): перевод интерфейсов настроек
Причина «части на английском»: у мода просто нет ключей в `ru_ru.json` (fallback на en_us).
Статус анализа:
- **Sodium-neoforge 0.8.12: файл ru_ru.json отсутствует ПОЛНОСТЬЮ** (в jar есть только вложенный
  `META-INF/jarjar/net.caffeinemc.sodium-neoforge-...-mod.jar` — это fabric-api-base заглушка;
  сам код на 72 класса, ключи не найдены регэкспом — разбираться дальше при необходимости).
- Distant Horizons 3.3.3 и Sable: только en_us (их GUI будет английским).
- Iris: не переведено 6 из 73 строк; Cloth/Create/Sophisticated/DynLights/EntityCulling/ModernFix: переводы есть.
План патча (не начат): извлечь ключи из классов → собрать `ru_ru.json` → положить либо правкой jar
(с бэкапом оригинала), либо отдельным мини-модом локализации в mods/.

## Предыстория решений
- Пользователь выбрал путь «собирать вручную в TL MODS / прямо в профиле», скрипт-автоматизацию
  через Modrinth API обсуждали, но он решил ставить сам; я подбираю составы и проверяю совместимость.
- Память профиля: советовать 6–8 ГБ при тяжёлой генерации + шейдеры.
- Связка рендера: Sodium (движок) → Iris (шейдеры) → пак в `shaderpacks/` (Complementary/Euphoria).
  Sodium и OptiFine взаимоисключающи. Замена Sodium→Embeddium потребует Oculus вместо Iris
  (Oculus на 1.21.1 нет) — не советовать без веской причины.
- Обсуждали внешние инструменты: Prism Launcher (offline-аккаунт, каталог Modrinth в UI) и
  modpacks.ch — пользователь пока остался на ручном пути в TLauncher.

## Стиль общения
Отвечать по-русски, по делу, с проверкой фактов по Modrinth API / содержимому профиля, а не «вообще».
