# FUPX ini updater

Автоматическое обновление конфигурации .ini (версий UPX) для FUPX | Automatic .ini configuration updates (UPX versions) for FUPX

---

## Описание | Description

**FUPX ini updater** - утилита для автоматического обновления конфигурационного файла `upx.ini`, используемого в программе **FUPX** (графическая оболочка для UPX)
Утилита сканирует директорию на наличие исполняемых файлов UPX и автоматически генерирует или обновляет `upx.ini` с актуальной информацией о всех доступных версиях упаковщика

**FUPX ini updater** - a utility that automatically updates the `upx.ini` configuration file used by **FUPX** (a graphical shell for UPX)
The tool scans a directory for UPX executables and generates or updates `upx.ini` with accurate data about all available UPX versions

<img width="624" height="144" alt="fupx_ini_updater1" src="https://github.com/user-attachments/assets/8ec8993b-4b7b-4d2e-8326-e2627cf480e3" />
<img width="338" height="350" alt="fupx_ini_updater" src="https://github.com/user-attachments/assets/fd720691-bb55-43ab-90d6-a305cd3414b5" />

---


## Возможности

  **Автоматическое обнаружение** - находит все `upx*.exe` в директории (включая поддиректории)

  **Определение разрядности** - автоматически определяет 64/32-битные исполняемые файлы

  **Извлечение даты релиза**

  **Сортировка версий** - сортирует версии по убыванию

  **Генерация INI** - создает правильно отформатированный `upx.ini` для FUPX

  **Отслеживание изменений** - показывает, какие версии были добавлены или удалены


## Features

  **Automatic Discovery** - finds all `upx*.exe` files in the directory (including subdirectories)

  **Architecture Detection** - automatically identifies 64/32-bit executables

  **Release Date Extraction**

  **Version Sorting** - sorts versions in descending order

  **INI Generation** - creates properly formatted `upx.ini` for FUPX

  **Change Tracking** - shows which versions were added or removed

---

## Использование | Usage

```
fupx_ini_updater.exe [путь_к_директории_с_UPX]
fupx_ini_updater.exe [path_to_upx_directory]
```

**Примеры | Examples:**

```bash
# Использовать директорию "upx" в текущей директории (по умолчанию)
# Use "upx" directory in the current directory (by default)
fupx_ini_updater.exe

# Абсолютный путь | Absolute path
fupx_ini_updater.exe C:\Tools\FUPX\upx

# Относительный путь | Relative path
fupx_ini_updater.exe ..\FUPX\upx
```

**Пример вывода | Output Example:**

```
FUPX ini updater (https://github.com/de-served/fupx_ini) | v1.0.0, 2026/01/28

Usage: fupx_ini_updater.exe [path]

Checking upx executables in upx\...
Updating ini...
Finished. Added [5.1.0 64-bit, 4.2.4 64-bit, 4.2.4 32-bit]. Removed [3.89 64-bit, 3.89 32-bit].
```

---

## Формат INI файла | INI File Format

Утилита генерирует `upx.ini` в следующем формате:

The utility generates `upx.ini` in the following format:

```ini
[510_64]
Version=5.1.0
ReleaseDate=2026.01.07
File=upx-5.1.0-win64\upx.exe
Bits=64
Caption=UPX 5.1.0 64-bit

[424_64]
Version=4.2.4
ReleaseDate=2024.05.09
File=424\upx64.exe
Bits=64
Caption=UPX 4.2.4 64-bit

[424_32]
Version=4.2.4
ReleaseDate=2024.05.09
File=424\upx32.exe
Bits=32
Caption=UPX 4.2.4 32-bit
```

**Формат названия секции:**
`{версия_без_точек}_{битность}` (например, `510_64` для версии 5.1.0 64-bit)

---

## Требования | Requirements

  * Windows 7+

  * Права на запись в директорию

  * Не требует никаких библиотек, независим (статический)

  * Directory write access

  * No need in libraries, independent (static)
