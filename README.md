# The Rules of Dix

1. Start your NixOS configuration with this template command: (todo)
2. Shell history will be the only way to store your NixOS configuration
3. Run the build command on the same shell session every time unless all your shell sessions share the same history.
4. If you lost your configuration, you lose and have to start over.
5. `github:nixos/nixpkgs/master` is the only flake input.
6. Rolling back to a previously built generation is allowed.

The list of rules may change. The goal is to make configuration in NixOS fun.
