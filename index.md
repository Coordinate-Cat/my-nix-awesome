# my-nix-awesome
日本語でnix関連まとめていくだけのレポジトリ

rule:
- en to ja

## Official(公式サイト)
- [NixOS公式](https://nixos.org/)

## Official(公式レポジトリ)
- [LnL7/nix-darwin](https://github.com/LnL7/nix-darwin)


<br>
<br>
<br>
<hr>
<br>
<br>
<br>


## nixpkgs
- home-managerを使うのにいる
```
nix-channel --add https://nixos.org/channels/nixpkgs-unstable nixpkgs
nix-channel --update
```

## home-manager
- nixpkgsを入れた後に以下を実行
```
nix-channel --add https://github.com/nix-community/home-manager/archive/master.tar.gz home-manager
nix-channel --update

nix-shell '<home-manager>' -A install
```

## nix-darwin
- [HomebrewからNix package managerへの移行](https://www.softinio.com/post/moving-from-homebrew-to-nix-package-manager/)
  - [Rahmanian's darwin-configuration.nix](https://github.com/softinio/dotfiles/blob/master/nix/configuration.nix)
  - 筆者のconfigurationのリンクが死んでいます
- [Changing the configuration.nix location](https://github.com/LnL7/nix-darwin/wiki/Changing-the-configuration.nix-location)
  - nix-darwinでconfigurationファイルが読み込めない問題

## その他
まじで動かなくなった時

- [macosからの完全nix削除](https://nixos.org/manual/nix/stable/installation/installing-binary.html#macos)
~~[Uninstall nix on MacOS](https://iohk.zendesk.com/hc/en-us/articles/4415830650265-Uninstall-nix-on-MacOS)~~

```
{ config, pkgs, ... }:

{
  # Use a custom configuration.nix location.
  # $ darwin-rebuild switch -I darwin-config=$HOME/.config/nixpkgs/darwin/configuration.nix
  environment.darwinConfig = "$HOME/.config/nixpkgs/darwin/configuration.nix";

  # ...
}
```
