# VRC World Shared Assets

Shared Unity assets for VRChat world development.

## Compatibility

- Unity 2022.3.22f1: VRChat authoring, build, and upload baseline
- Unity 6: shared-asset consumption and testing

Keep assets compatible with Unity 2022.3.22f1. Do not commit prefabs,
materials, scenes, or other serialized Unity assets after saving them only in
Unity 6 unless their backward compatibility has been verified in Unity
2022.3.22f1.

VRChat does not use URP or HDRP, so shared materials and shaders should target
the Built-in Render Pipeline unless documented otherwise.

## Install with Unity Package Manager

After a release tag has been created, open Unity's Package Manager and select
**Add package from git URL**, then enter a versioned URL such as:

```text
https://github.com/allial45003939-prog/vrc_world_shared_assets.git#v0.1.0
```

Pin projects to a release tag or full commit hash instead of relying on the
default branch.

## Package layout

```text
.
|-- package.json
|-- Runtime/
|-- Editor/
|-- Samples~/
|-- CHANGELOG.md
|-- LICENSE.md
`-- README.md
```

- `Runtime/`: assets and runtime code shared by consuming projects
- `Editor/`: Unity Editor-only tooling
- `Samples~/`: optional content imported explicitly from Package Manager

Commit every Unity-generated `.meta` file together with its asset so GUID-based
references remain stable across projects.

## Development policy

- Treat Unity 2022.3.22f1 as the compatibility baseline.
- Keep VRChat SDK-dependent code out of the core package where possible.
- Use semantic versions and Git tags for releases.
- Use Git LFS for large binary source assets when needed, and ensure Git LFS is
  installed on every machine consuming the package.
