# ReTracer modpack

Список модов для Minecraft-сервера ReTracer (Minecraft 1.20.1, Forge 47.4.18).
Его читает лаунчер ReTracer: при каждом запуске сверяет папку `mods/` с манифестом,
докачивает недостающее и удаляет лишнее.

## Как это устроено

- Каждая версия сборки — отдельный [релиз](../../releases). В релизе лежит `modrinth.index.json`
  (формат Modrinth) и файлы модов, которых нет на Modrinth.
- Лаунчер всегда берёт манифест по ссылке
  `https://github.com/Really-Fun/ReTracer-modpack/releases/latest/download/modrinth.index.json`,
  поэтому новая сборка = новый релиз, обновлять лаунчер не нужно.
- Моды с Modrinth скачиваются напрямую с `cdn.modrinth.com` — здесь их файлов нет.
- Каждый файл проверяется по sha1 до того, как попадёт в папку игры.

## Моды, чьи файлы лежат в релизах

Перезаливаются только моды, лицензия которых это разрешает. Все права принадлежат авторам.

| Мод | Автор | Лицензия | Где взят |
|-----|-------|----------|----------|
| Krypton Reforged 0.2.3 | авторы Krypton Reforged (порт Krypton by astei) | LGPL-3.0 | [CurseForge](https://www.curseforge.com/minecraft/mc-mods/krypton-reforged) |
| Omega Flashlight 0.7.6-1.20.1 | omegaru010 | LGPL-3.0-only | [ModpackIndex](https://www.modpackindex.com/mod/159625/omega-flashlight) |

Текст LGPL-3.0: https://www.gnu.org/licenses/lgpl-3.0.html. Файлы модов не изменены.

Моды с лицензией All Rights Reserved сюда не выкладываются.

## Новая сборка

```bash
python3 tools/make_modpack.py --version 0.4.0 \
    --release-url https://github.com/Really-Fun/ReTracer-modpack/releases/download/v0.4.0
```

Затем создать релиз `v0.4.0` и загрузить в него всё из `dist/release-0.4.0/`.
