# my-yocto-devcontainer

This repository provides devcontainer environment for yocto build.

## Reference

- [Yocto Project Quick Build [Kirkstone (4.0.21)]](https://docs.yoctoproject.org/4.0.21/brief-yoctoprojectqs/index.html)

## Usage

### Directory structure

```shell
my-yocto-devcontainer/
├── .devcontainer
│   ├── Dockerfile
│   └── devcontainer.json
├── poky (after you create devcontainer, git clone poky)
├── build (after you initialize with using oe-init-build-env, build directory will be created)
├── meta-XXX (if you use custom meta-layer, you create them out of poky)
├── :
├── :
│
├── README.md
└── UNLICENSE
```

### Setup devcontainer

- Clone this repository and run VS Code in the root directory.

```shell
git clone https://github.com/tomoten-umino/my-yocto-devcontainer.git
cd my-yocto-devcontainer
code .
```

- Use "Reopen in Container" and start devcontainer with a new window.
- Git clone poky repository.
  - This devcontainer is confirmed to run with kirkstone.
- If you have custom meta-layer, you add meta-layer to your build tree.
