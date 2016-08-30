# Composer cheat sheet

[Composer](https://getcomposer.org) je správce závislostí pro PHP.

## Instalace composeru

### Windows
Jednoduše stáhnout [oficiální instalační balíček](https://getcomposer.org/Composer-Setup.exe), který provede instalaci composeru a provede potřebná nastavení.

### Linux, Mac OSX, Unix
Postupovat dle [návodu](https://getcomposer.org/download/)

> Pro ověření správnosti instalace stačí spustit v terminálu `composer --version`, příkaz vypíše aktuální nainstalovanou verzi.

## Aktualizace composeru

Aktualizaci lze jednoduše provést pomocí příkazu `composer self-update`, pokud je nainstalován globálně na UNIX-like systému (Linux, Mac OSX), je nutné provést update pod superuživatelem root `sudo composer self-update`.

## Použítí

### Přidání nové závislosti do projektu

Závislosti se dají vyhledávat v globálním repozitáři [Packagist](https://packagist.org).

`composer require doctrine/orm`

Přidání závislosti potřebné pouze pro vývoj:

`composer require phpunit/phpunit --dev`

Globální instalace:

`composer global require phpmd/phpmd`

> Při správné konfiguraci prostředí by mělo jít globálně nainstalované nástroje spustit z terminálu např. `phpmd`

### Instalace závislostí projektu

### Aktualizace závislostí projektu

### Odebírání závislostí

### Autoloading

