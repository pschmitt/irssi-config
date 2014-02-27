# Irssi config

## Installation

```bash
git clone https://github.com/pschmitt/irssi-config.git $XDG_CONFIG_HOME/irssi
```

### Dependencies

The plugins requires following perl packages (ArchLinux):

* perl-tk
* perl-crypt-openssl-bignum
* perl-crypt-dh
* perl-crypt-blowfish
* perl-lwp-protocol-https
* perl-timedate
* perl-text-unidecode

So on ArchLinux you'd issue:

```bash
sudo pacman -S perl-tk perl-crypt-openssl-bignum perl-crypt-blowfish \
     perl-lwp-protocol-https perl-timedate
# perl-crypt-dh and perl-text-unidecode are AUR packages
# perl-cryp-dh depends on perl-math-bigint-gmp
mkdir /tmp/perl-{math-bigint-gmp,crypt-dh,timedate-unidecode}
cd /tmp/perl-math-bigint-gmp
wget https://aur.archlinux.org/packages/pe/perl-math-bigint-gmp/PKGBUILD
makepkg -si
cd /tmp/perl-crypt-dh
wget https://aur.archlinux.org/packages/pe/perl-crypt-dh/PKGBUILD
makepkg -si
cd /tmp/perl-timedate-unidecode
wget https://aur.archlinux.org/packages/pe/perl-text-unidecode/PKGBUILD
makepkg -si
```

After this, you neeed to either

* Create a symlink from `~/.irssi` to `$XDG_CONFIG_HOME/irssi`

```bash
ln -s $XDG_CONFIG_HOME ~/.irssi
```

* Add a new alias to your `.${SHELL}rc`

```bash
alias irssi="irssi --home=$XDG_CONFIG_HOME/irssi"
```

* Just move the irssi folder

```bash
mv $XDG_CONFIG_HOME/irssi ~/.irssi
```
