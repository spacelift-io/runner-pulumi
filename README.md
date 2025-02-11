# Spacelift Runner image for Pulumi

This repository builds Docker images for Spacelift's Pulumi Runners for all language environments officially supported by Pulumi. Resulting images are tagged by their Pulumi version used to build them, and the latest version available is always tagged as `latest`.

## Release process

The release process is triggered by pushing new tags to the repo in the following formats:

- `dev-vx.y.z` - to build a test image pushed to our preproduction registries.
- `latest-vx.y.x` - to build an image with the `latest` tag pushed to our production registries.
- `vx.y.z` - to build an image with a `vx.y.z` tag pushed to our production registries.

**NOTE:** `vx.y.z` in the above examples corresponds to the version of Pulumi that should be installed on the image.

### New Pulumi versions

A tool called the Vendor Releases Watcher automatically pushes new tags to the repo when new releases of Pulumi are published.

### Registries

We publish the runner images to a number of public ECRs depending on the tooling you are using for Pulumi:

| Environment    | Registry                                              |
| -------------- | ----------------------------------------------------- |
| Production     | public.ecr.aws/spacelift/runner-pulumi-dotnet         |
| Production     | public.ecr.aws/spacelift/runner-pulumi-golang         |
| Production     | public.ecr.aws/spacelift/runner-pulumi-javascript     |
| Production     | public.ecr.aws/spacelift/runner-pulumi-python         |
| Pre-Production | public.ecr.aws/spacelift-dev/runner-pulumi-dotnet     |
| Pre-Production | public.ecr.aws/spacelift-dev/runner-pulumi-golang     |
| Pre-Production | public.ecr.aws/spacelift-dev/runner-pulumi-javascript |
| Pre-Production | public.ecr.aws/spacelift-dev/runner-pulumi-python     |

### Re-releasing a version

If you need to make changes to a particular image, just delete the existing tags and push them again. This will trigger a new release that will push the image to the registries.
