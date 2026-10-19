klipper-helm

This repo builds the image that runs helm install/upgrade/remove operations for
the [helm controller](https://github.com/k3s-io/helm-controller) built in to
K3s and RKE2. The approach is extremely simple. This is just a single shell
script.

## Building

Run `make` for the default amd64 image.

To cross-build for RISC-V on an amd64 host, install Docker Buildx and QEMU
binfmt (for example, via `docker/setup-qemu-action` in GitHub Actions), then:

```sh
ARCH=riscv64 REPO=ghcr.io/itamarjp make
```

This builds and loads a single-platform image into the local Docker image
store. To publish a multi-platform image, use the GitHub Actions release
workflow, which already targets `linux/riscv64` alongside amd64 and ARM.

## Contact

For bugs, questions, comments, corrections, suggestions, etc., open an issue in
[k3s-io/helm-controller](https://github.com/k3s-io/helm-controller/issues).
