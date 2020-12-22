# Useful tools for OpenShift SREs

## Dependencies

* [direnv](https://direnv.net/)

## Install

```bash
git clone https://github.com/NautiluX/osd-tools
echo "export PATH=`pwd`/osd-tools/bin:\$PATH"
```

## Usage

### ocenv

`ocenv` can be used to log in to several OpenShift clusters at the same time. Each cluster is referred to by a user-defined alias.
`ocenv` creates a directory in `~/ocenv/` for each cluster named by the alias. It contains an `.envrc` to set `$KUBECONFIG` when the user enters the directory.

You can run `ocenv my-cluster` to create a new environment or switch between environments. Each environment will use a separate `$KUBECONFIG` so you can easily switch between them.

Optionally, you can run `ocenv my-cluster my-cluster-id` to set the `$CLUSTERID` variable in the environment. This is useful to log in to the cluster. When using `ocm` you can use the shorthands `ocl` to log in to the cluster and `oct` to create a tunnel when inside the environment.

You can leave an environment by pressing `ctrl+D`, but you can also just switch to a different one with `ocenv my-other-cluster`.
