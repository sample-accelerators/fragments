#tap-initialize

To create this fragment use:

```
apiVersion: accelerator.apps.tanzu.vmware.com/v1alpha1
kind: Fragment
metadata:
  name: tap-initialize
  namespace: accelerator-system
spec:
  displayName: TAP Initialize
  git:
    ref:
      branch: main
    url: https://github.com/sample-accelerators/fragments.git
    subPath: tap-initialize
```
