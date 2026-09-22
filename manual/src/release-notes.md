# Release Notes

## [Release 0.5.0](https://github.com/nix-community/colmena/releases/tag/v0.5.0) (unreleased)

This is a long overdue release more than 3 years after 0.4.0!

Colmena has moved from `zhaofengli/colmena` to `nix-community/colmena`
after [a discussion with the original author](https://github.com/orgs/nix-community/discussions/2276).
The current maintainers are
[@stepbrobd](https://github.com/stepbrobd),
[@NickCao](https://github.com/NickCao), and
[@zhaofengli](https://github.com/zhaofengli).

This will be the last release with `x86_64-darwin` support, 0.6.0 will be tagged shortly after 0.5.0.

- ssh: fix substitution when using experimental `nix copy` ([#156](https://github.com/nix-community/colmena/pull/156))
- fix: allow nodeSpecialArgs to override name and nodes ([#155](https://github.com/nix-community/colmena/pull/155))
- chore: dead link ([#172](https://github.com/nix-community/colmena/pull/172))
- Switch to clap derive ([#169](https://github.com/nix-community/colmena/pull/169))
- Set exit code > 0 when colmena exec fails ([#191](https://github.com/nix-community/colmena/pull/191))
- Support adding extra ssh options on node configurations ([#197](https://github.com/nix-community/colmena/pull/197))
- make eval.nix more convnient to use for non-flake user ([#199](https://github.com/nix-community/colmena/pull/199))
- lib.mdDoc has been deprecated since 24.05 ([#222](https://github.com/nix-community/colmena/pull/222))
- Fix describe_node_list remaining nodes special case ([#224](https://github.com/nix-community/colmena/pull/224))
- Add direct flake evaluation support ([#228](https://github.com/nix-community/colmena/pull/228))
- Exclude more paths from colmena.src to reduce rebuilds ([#238](https://github.com/nix-community/colmena/pull/238))
- .github/build: Update macOS runner, add aarch64-darwin ([#242](https://github.com/nix-community/colmena/pull/242))
- README.md: Fix badge branch ([#247](https://github.com/nix-community/colmena/pull/247))
- resolve TempDir paths before passing them to the flake bin ([#233](https://github.com/nix-community/colmena/pull/233))
- progress: Detect tty with std::io::IsTerminal, remove atty ([#248](https://github.com/nix-community/colmena/pull/248))
- flake: fix patch for nix-eval-jobs ([#256](https://github.com/nix-community/colmena/pull/256))
- Add meta.mainProgram ([#267](https://github.com/nix-community/colmena/pull/267))
- Enable direct flake evaluation by default ([#279](https://github.com/nix-community/colmena/pull/279))
- README.md: Update flake example for direct flake evaluation ([#280](https://github.com/nix-community/colmena/pull/280))
- Improve help message readability ([#261](https://github.com/nix-community/colmena/pull/261))
- Make nix_flags_with_builders call nix_flags ([#265](https://github.com/nix-community/colmena/pull/265))
- fix(nix-eval-jobs): silence warning when overriding version without src ([#289](https://github.com/nix-community/colmena/pull/289))
- fix: Chown correct path for pre-activation keys ([#291](https://github.com/nix-community/colmena/pull/291))
- chore: Format most Nix files with nixfmt-rfc-style ([#283](https://github.com/nix-community/colmena/pull/283))
- refactor: Migrate to tracing ([#284](https://github.com/nix-community/colmena/pull/284))
- Emit logs to stderr ([#300](https://github.com/nix-community/colmena/pull/300))
- Don't use patched version of nix-eval-jobs if version >= 2.30.0 ([#306](https://github.com/nix-community/colmena/pull/306))
- .github: Harmonize common setup, pin dependencies with commit hash ([#308](https://github.com/nix-community/colmena/pull/308))
- deployment: Fix typo that broke --eval-node-limit=0 ([#311](https://github.com/nix-community/colmena/pull/311))
- fix: replace deprecated pkgs.system with pkgs.stdenv.hostPlatform.system ([#316](https://github.com/nix-community/colmena/pull/316))
- ci: fix "no space left on device" ([#342](https://github.com/nix-community/colmena/pull/342))
- {cargo,flake}: bump deps ([#341](https://github.com/nix-community/colmena/pull/341))
- ci: init dependabot ([#347](https://github.com/nix-community/colmena/pull/347))
- treewide: address clippy and deadcode warns ([#345](https://github.com/nix-community/colmena/pull/345))
- ci: use dependabot groups to prevent prs spams ([#357](https://github.com/nix-community/colmena/pull/357))
- .git-blame-ignore-revs: init ([#358](https://github.com/nix-community/colmena/pull/358))
- ssh: Put extra_ssh_options before internal options ([#364](https://github.com/nix-community/colmena/pull/364))
- treewide: run nix fmt ([#362](https://github.com/nix-community/colmena/pull/362))
- formatter: fix ci and find repo root with git ([#375](https://github.com/nix-community/colmena/pull/375))
- hive: fix `--evaluator streaming` noop ([#340](https://github.com/nix-community/colmena/pull/340))
- cargo: drop atty ([#377](https://github.com/nix-community/colmena/pull/377))
- hive/tests: pin nixpkgs system in tests ([#378](https://github.com/nix-community/colmena/pull/378))
- Loosen deployment.keys username/group validation regex ([#380](https://github.com/nix-community/colmena/pull/380))
- treewide: cleanup ([#381](https://github.com/nix-community/colmena/pull/381))
- treewide: drop legacy code paths and refactor how CLI flags are passed ([#379](https://github.com/nix-community/colmena/pull/379))

## [Release 0.4.0](https://github.com/nix-community/colmena/releases/tag/v0.4.0) (2023/05/14)

- Flake evaluation is now actually pure by default. To enable impure expressions, pass `--impure`.
- `--reboot` is added to trigger a reboot and wait for the node to come back up.
- The target user is no longer explicitly set when `deployment.targetUser` is null ([#91](https://github.com/nix-community/colmena/pull/91)).
- In `apply-local`, we now only escalate privileges during activation ([#85](https://github.com/nix-community/colmena/issues/85)).
- Impure overlays are no longer imported by default if a path is specified in `meta.nixpkgs` ([#39](https://github.com/nix-community/colmena/issues/39))
- GC roots are now created right after the builds are complete, as opposed to after activation.
- The [`meta.allowApplyAll`](./reference/meta.md#allowapplyall) option has been added. If set to false, deployments without a node filter (`--on`) are disallowed ([#95](https://github.com/nix-community/colmena/issues/95)).
- The `--no-substitutes` option under the `apply` subcommand has been renamed to `--no-substitute` ([#59](https://github.com/nix-community/colmena/issues/59)).
- The [`meta.nodeSpecialArgs`](./reference/meta.md#nodespecialargs) option has been added. It allows specifying node-specific `specialArgs` passed to NixOS modules ([#100](https://github.com/nix-community/colmena/pull/100)).
- The [`repl`](./reference/cli.html#colmena-repl) subcommand has been added. It allows you to start an [interactive REPL](./features/eval.md#interactive-repl) with access to the complete node configurations.
- The default goal for `colmena apply` is now `boot` if `--reboot` is specified, and `switch` otherwise ([#113](https://github.com/nix-community/colmena/issues/113)).
- Post-activation keys are now uploaded after the reboot if `--reboot` is specified ([#113](https://github.com/nix-community/colmena/issues/113)).
- Flake-enabled deployments now use the new SSH store protocol (`ssh-ng://`).

## [Release 0.3.2](https://github.com/nix-community/colmena/releases/tag/v0.3.1) (2022/09/29)

- Fixed: [Key services](https://colmena.cli.rs/0.3/features/keys.html#key-services) were using the deprecated `inotifyTools` alias removed from `nixos-unstable` ([NixOS/nixpkgs#192681](https://github.com/NixOS/nixpkgs/pull/192681)).

## [Release 0.3.1](https://github.com/nix-community/colmena/releases/tag/v0.3.1) (2022/08/18)

- Fixed: Streaming evaluation fails for node names containing periods ([#92](https://github.com/nix-community/colmena/issues/92))
- Fixed: Streaming evaluation fails in non-flake deployments with relative paths ([#107](https://github.com/nix-community/colmena/issues/107))
- Fixed: `colmena apply-local` returning non-zero exit code when successful ([#111](https://github.com/nix-community/colmena/issues/111))

## [Release 0.3.0](https://github.com/nix-community/colmena/releases/tag/v0.3.0) (2022/04/27)

- [Remote builds](https://colmena.cli.rs/0.3/features/remote-builds.html) are now supported ([#33](https://github.com/nix-community/colmena/issues/33)).
- [Streaming evaluation](https://colmena.cli.rs/0.3/features/parallelism.html#parallel-evaluation-experimental) powered by [nix-eval-jobs](https://github.com/nix-community/nix-eval-jobs) is now available as an experimental feature (`--evaluator streaming`).
- Colmena can now run on macOS to deploy to NixOS hosts using [remote building](https://colmena.cli.rs/0.3/features/remote-builds.html).
- It's now possible to configure output colorization via the CLI and environment variables. Colmena follows the [clicolors](https://bixense.com/clicolors) standard.
- [A systemd unit](https://colmena.cli.rs/0.3/features/keys.html#key-services) (`${name}-key.service`) is now created for each secret file deployed using `deployment.keys` ([#48](https://github.com/nix-community/colmena/issues/48)).
- Node enumeration is now faster if you do not filter against tags with `--on @tag-name`.
- The main deployment logic has been rewritten to be cleaner and easier to follow.
- There are now [end-to-end tests](https://github.com/nix-community/colmena/tree/main/integration-tests) to ensure that the development branch is actually functional as a whole at all times.

## [Release 0.2.2](https://github.com/nix-community/colmena/releases/tag/v0.2.2) (2022/03/08)

This bugfix release fixes NixOS detection so `apply-local` works with the latest changes in `nixos-unstable` ([#63](https://github.com/nix-community/colmena/pull/63)). Additionally, `--no-keys` was fixed in `apply-local`.

## [Release 0.2.1](https://github.com/nix-community/colmena/releases/tag/v0.2.1) (2022/01/26)

This bugfix release fixes the issue ([#50](https://github.com/nix-community/colmena/issues/50)) where [sandboxed documentation builds](https://github.com/NixOS/nixpkgs/pull/149532) fail when using the unstable Nixpkgs channel.

## [Release 0.2.0](https://github.com/nix-community/colmena/releases/tag/v0.2.0) (2021/11/18)

This is release 0.2.0, the first stable release of Colmena!

Colmena is a simple, stateless NixOS deployment tool modeled after NixOps and morph, built from the ground up to support parallel deployments.

This release contains the following features:

- Node Tagging
- Local Deployment
- Secrets
- Ad Hoc Evaluation
- Nix Flakes Support
- Parallelism

We now have a User Manual at https://colmena.cli.rs/0.2 containing tutorials, sample configurations as well as a complete listing of supported deployment options.
