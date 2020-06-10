# xyz

# Packer


Packer is a tool for building identical machine images for multiple platforms
from a single source configuration.

Packer is lightweight, runs on every major operating system, and is highly
performant, creating machine images for multiple platforms in parallel. Packer
comes out of the box with support for many platforms, the full list of which can
be found at https://www.packer.io/docs/builders/index.html.

Support for other platforms can be added via plugins.



## Instruction to download packer

First, [download a pre-built Packer
binary](https://www.packer.io/downloads.html) for your operating system or
[compile Packer
yourself](https://github.com/hashicorp/packer/blob/master/.github/CONTRIBUTING.md#setting-up-go-to-work-on-packer).

After Packer is installed, create your first template, which tells Packer
what platforms to build images for and how you want to build them. In our
case, we'll create a simple AMI that has Redis pre-installed. Save this
file as `ami.json`. Export your AWS credentials as the
`AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment variables.

Now validate packer:

```
$ ./packer validate ami.json
```

Next, tell Packer to build the image:

```
$ packer build ami.json
...
```

Packer will build an AMI according to the template. The AMI
will be available in your AWS account. 


