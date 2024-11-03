# MinOS

MinOS is a set of custom Vanilla OS images that use Debian Stable as a base, rather than using Debian Sid snapshots. It's still all of the immutable glory of Vanilla OS, but with a more stable (if slightly older) base.

# MinOS Desktop Image

Containerfile for building a MinOS/VanillaOS Desktop image.

This image is based on top of [`minos/core`](https://github.com/SandalChannel/minos-core) and offers the default
MinOS/VanillaOS Desktop experience with GNOME.

## Build

> [!NOTE]
> The fsguard compiled plugin `.so` file should be downloaded from the [latest release](https://github.com/Vanilla-OS/vib-fsguard/releases/latest) and be placed under a `plugins` directory beside the `recipe.yml` file.

```bash
vib build recipe.yml
podman image build -t vanillaos/desktop .
```

## Verify Image Build Provenance Attestation

All the image builds/pushes are attested for build provenance and integrity using the [attest-build-provenance](https://github.com/actions/attest-build-provenance) action. The attestations can be verified [here](https://github.com/Vanilla-OS/desktop-image/attestations) or by having the latest version of [GitHub CLI](https://github.com/cli/cli/releases/latest) installed in your system. Then, execute the following command:

```sh
gh attestation verify oci://ghcr.io/vanilla-os/desktop:main --owner Vanilla-OS
```
