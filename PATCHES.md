# PocketAR engine patches

This branch is Godot master at the commit below plus the patches PocketAR and ExitAR build on. Each patch is one upstream PR, issue or proposal; drop it from the stack when it merges upstream. Rebase onto newer master deliberately, then rerun PocketAR's harness on desktop and both phones and ExitAR's smoke and budget runs before moving the games to it.

Base: `232e6b14ab` (master, 2026-10-09).

| Patch | Commits | Upstream | Notes |
| --- | --- | --- | --- |
| Vulkan: acceleration structure descriptor writes after skipped bindings | 1 | #124370 (open) | |
| Vulkan: dangling ASTC decode mode pointer in shared views | 1 | #124371 (open), issue #124392 | Crashes on Mali with `VK_EXT_astc_decode_mode` |
| RD: 2D default texture for unassigned `samplerExternalOES` | 1 | #124374 (open) | |
| `ExternalTexture` hardware buffer submission on RD (immutable samplers, Android hardware buffer import, submission) | 13 | #124376 (closed: features need trust first) | Resubmit through a godot-proposals entry; resplit the series first |
| Mobile: render targets without storage usage | 1 | none yet (FIXME in `texture_storage.cpp`) | Prototype. Breaks MetalFX spatial upscaling and user code binding viewport textures as storage; upstream shape is per render target and opt-in |
