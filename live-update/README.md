# live-update

To create this fragment use:

```
apiVersion: accelerator.apps.tanzu.vmware.com/v1alpha1
kind: Fragment
metadata:
  name: live-update
  namespace: accelerator-system
spec:
  displayName: Select Java Version
  git:
    ref:
      branch: main
    url: https://github.com/sample-accelerators/fragments.git
    subPath: live-update
```
