# my-nix-awesome
日本語でnix関連まとめていくだけのレポジトリ

rule:
- en to ja

## Official(公式サイト)
- [NixOS公式](https://nixos.org/)

## Official(公式レポジトリ)
- [LnL7/nix-darwin](https://github.com/LnL7/nix-darwin)

## nix-darwin
- [HomebrewからNix package managerへの移行](https://www.softinio.com/post/moving-from-homebrew-to-nix-package-manager/)
  - [Rahmanian's darwin-configuration.nix](https://github.com/softinio/dotfiles/blob/master/nix/configuration.nix)
  - 筆者のconfigurationのリンクが死んでいます
- [Changing the configuration.nix location](https://github.com/LnL7/nix-darwin/wiki/Changing-the-configuration.nix-location)
  - nix-darwinでconfigurationファイルが読み込めない問題

## その他
まじで動かなくなった時
- [Uninstall nix on MacOS](https://iohk.zendesk.com/hc/en-us/articles/4415830650265-Uninstall-nix-on-MacOS)
```
sudo vim bash.bashrc
```
```
rm -rf $HOME/{.nix-channels,.nix-defexpr,.nix-profile}
```



```
{ config, pkgs, ... }:

{
  # Use a custom configuration.nix location.
  # $ darwin-rebuild switch -I darwin-config=$HOME/.config/nixpkgs/darwin/configuration.nix
  environment.darwinConfig = "$HOME/.config/nixpkgs/darwin/configuration.nix";

  # ...
}
```
