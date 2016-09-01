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

Pokud projekt obsahuje soubor `composer.json` provedu jednoduše instalaci všech zavislostí pomocí příkazu `composer install`, který spustím v terminálu ve stejné složce, jako se nachází soubor `composer.json`.

> Pokud se ve stejné složce nachází také soubor `composer.lock`, provede příkaz `composer install` instalaci závislostí v konkrétních verzích. Proto se hodí, aby byl soubor `composer.lock` součástí repozitáře, díky tomu budou všichni vývojáři, kteří pracují s projektem, používat stejné verze závislostí.

Pro instalaci závislostí při sestavení produkčního balíčku aplikace se hodí příkaz `composer install --optimize-autoloader --no-dev --no-interaction`. V čem se liší proti obyčejnému `composer install`?
- `--optimize-autoloader` - vytvoří optimalizovaný autoloader vhodný na produkci
- `--no-dev` - neinstalovat závislosti potřebné pro vývoj - na produkci nejsou potřeba
- `--no-interaction` - neinteragovat v terminálu - toto se hodí hlavně pokud je build proces projektu automatizovaný


### Aktualizace závislostí projektu

### Odebírání závislostí

### Autoloading

