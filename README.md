# Logos Forum catalog

A Logos module catalog serving **Forum** (`forum_module`), a text-first
forum for Logos Basecamp with privacy-required posting (Logos Delivery, Mix)
and history on Logos Storage. Source and documentation:
[Tranquil-Flow/logos-forum](https://github.com/Tranquil-Flow/logos-forum).

## Install Forum

1. Install **Logos Basecamp 0.3.1**
   ([releases](https://github.com/logos-co/logos-basecamp/releases/tag/0.3.1)).
2. Basecamp → **Package Manager** → add repository

   ```
   https://raw.githubusercontent.com/Tranquil-Flow/logos-forum-catalog/refs/heads/main/logos-repo.json
   ```

3. Install **Forum**. Its dependencies come from the official
   [logos-modules-release](https://github.com/logos-co/logos-modules-release)
   catalog, pinned in `includes.json` to the exact builds Forum is tested
   against: `delivery_module` 0.3.0 and `storage_module` 3.0.0.

Packages are built for darwin-arm64, linux-amd64, linux-arm64 and
windows-x86_64.

## How this catalog is built

Made from [logos-modules-release-base](https://github.com/logos-co/logos-modules-release-base):
`submodules/logos-forum` pins the Forum source, and the **Release
logos-forum** / **Release all modules** workflows build each variant with
the shared `logos-modules-release-action`, publish a `forum_module-v<version>`
release and roll it into the `index` release that Basecamp reads. To publish
a new version, bump the submodule pointer and run the release workflow.
