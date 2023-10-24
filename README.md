# kuttle-learn

https://kuttl.dev/docs/kuttl-test-harness.html#writing-your-first-test

### Let's run this test suite:
```
kubectl kuttl test --start-kind=true ./tests/e2e/
```

Running this command will:
- Start a kind (Kubernetes-in-Docker) cluster
- (opens new window), if there is not already one running.
- Create a new namespace for the test case.
- Create the resources defined in tests/e2e/example-test/00-install.yaml.
- Wait for the state defined in tests/e2e/example-test/00-assert.yaml to be reached.
- Collect the kind cluster's logs.
- Tear down the kind cluster (or you can run kubectl kuttl test with --skip-cluster-delete to keep the cluster around after the tests run).

### Test Suite Configuration

To add this test suite to your project, create a kuttl-test.yaml file:

Now we can run the tests just by running `kubectl kuttl test` with no arguments.

Any arguments provided on the command line will override the settings in the `kuttl-test.yaml` file, e.g. to skip using kind and run the tests against a live Kubernetes cluster, run:

```
kubectl kuttl test --start-kind=false
```