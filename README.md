Docker image that includes golang, gcc and Terraform in order to be able to run Terratest.

Image tags refer to the version of Terraform used.

---

Usage:

- Create aliases like

```
alias terratest='docker run -it \
        -v $(pwd):/mnt \
        -v ~/.ssh:/root/.ssh \
        -w /mnt/test \
        -e GOOGLE_APPLICATION_CREDENTIALS \
        kodrclub/terratest:$TERRAFORM_VERSION'
```

or

```
alias terratest='docker run -it \
        -v $(pwd):/mnt \
        -v ~/.ssh:/root/.ssh \
        -w /mnt/test \
        -e AWS_ACCESS_KEY_ID \
        -e AWS_SECRET_ACCESS_KEY \
        -e AWS_DEFAULT_REGION \
        kodrclub/terratest:$TERRAFORM_VERSION'
```

Expects a `test` directory to be present, but must be run from _outside_ the test directory. For example, to test `my_module` the file structure should be in the form

<pre>
my_module/
  my_module.tf
  test/
    my_module_test.go
</pre>

In this case, terratest should be run from the `my_module` directory.

To build, tag and push your own version of the images to your registry, replace the username in the provided `Makefile`s and just run `make` inside the directory for the appropriate Dockerfile.

---

**TODO:** include required go dependencies in the image, so that go doesn't have to install them every time a container is instantiated.
