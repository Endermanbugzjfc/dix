# The Rules of Dix

1. Start with this template Bash command:
  ```
  NIX_CONFIG="experimental-features=flakes" nixos-rebuild switch --flake $(nix-build --no-out-link --expr 'let nixpkgs = fetchTarball "https://github.com/nixos/nixpkgs/tarball/master"; pkgs = nixpkgs.legacyPackages.x86_64-linux; in pkgs.writeText "flake.nix" "{ inputs.nixpkgs.url = "github:nixos/nixpkgs/nixos-unstable"; outputs = { self, nixpkgs }: { nixosConfigurations.nixos = nixpkgs.lib.nixosSystem { system = "x86_64-linux"; modules = [ ({ ... }: { }) ] } } }"')
  ```
  TODO: this command is written in 10 minutes and not tested, will test in some time

2. Configure your NixOS by editing and running that command in any shell.
3. Shell history will be the only way to store your NixOS configuration.
4. Run the build command on the same shell session every time unless all your shell sessions share the same history.
5. If your configuration becomes missing from the shell history, you lose and have to start over.
6. `github:nixos/nixpkgs/nixos-unstable` is the only flake input.
7. Fetchers are allowed.
8. Rolling back to a previously built generation is allowed.

The list of rules may change. The goal is to make configuration in NixOS fun.

