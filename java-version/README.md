# java-version

An accelerator for selecting the Java version to use for a generated project.

## Using the fragment

To use this fragment in your accelerator add the following import under the `accelerator` section in your `accelerator.yaml`:

```
accelerator:

# ...

  imports:
  - name: java-version
```

Then in your `engine` section add a top level `chain` entry with a `merge` that contains your original engine processing transforms. This should then be followed by another `merge` that invokes the fragment processing, taking the files generated in the previous step as input.

```
engine:
  chain:
  - merge:

    # this is where your original transforms go
  
  - merge:
    - include: [ "**" ]
    - type: InvokeFragment
      reference: java-version
```

## Creating the fragment resource

To create this fragment use:

```
apiVersion: accelerator.apps.tanzu.vmware.com/v1alpha1
kind: Fragment
metadata:
  name: java-version
  namespace: accelerator-system
spec:
  displayName: Select Java Version
  git:
    ref:
      branch: main
    url: https://github.com/sample-accelerators/fragments.git
    subPath: java-version
```
