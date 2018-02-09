# PHP DEV stack on macOS

Instalace většiny softwaru bude probíhat přes terminál. Je možné použít aplikaci Terminál, která je součástí macOS, osobně ale doporučuji nainstalovat [iTerm2](https://www.iterm2.com/).

Nejprve je nutné nainstalovat nástroje pro příkazovou řádku, to se provede v terminálu pomocí příkazu:

`xcode-select --install`

Pro instalaci použijeme balíčkovací system [Homebrew](https://brew.sh/).

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

Úspěšnou instalaci je možné ověřit zavoláním `brew --version`. Pokud je vše v pořádku, měla by se vypsat nainstalovaná verze.

## Instalace dnsmasq

```bash
brew install dnsmasq
sudo cp -v $(brew --prefix dnsmasq)/homebrew.mxcl.dnsmasq.plist /Library/LaunchDaemons
[ -d /etc/resolver ] || sudo mkdir -v /etc/resolver
sudo bash -c 'echo "nameserver 127.0.0.1" > /etc/resolver/test'
mkdir -p $(brew --prefix)/etc/
echo 'address=/.test/127.0.0.1' > $(brew --prefix)/etc/dnsmasq.conf
sudo launchctl load -w /Library/LaunchDaemons/homebrew.mxcl.dnsmasq.plist
```
