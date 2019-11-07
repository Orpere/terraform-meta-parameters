# terraform-meta-parameters -> repo that I can use to see how meta parameters work

This repo has as target to define and show what I have learned about terraform meta parameters

how can I use this repository?
You can use this repo as reference or you can clone the repository to your computer using the follow commands

```git
git clone git@github.com:Orpere/terraform-meta-parameters.git
```

you can also fork this repo using the fork button on top right on github and use it as yours as the follow example:

![fork](fork.png)

like this you can clone and edit the repository and commit your own changes.

you can clone your own repo as:

```git
git clone git@github.com:<YourGitUser>/terraform-meta-parameters.git
```

and use the commands add, commit and push to your own changes

for more instructions to use git you can check the [link](https://rogerdudler.github.io/git-guide/) it will have a much better explanation about all git steps

## Terraform Meta-parameters or Meta-arguments

The inspiration for this repository come from the Hashicorp [documentation](https://www.terraform.io/docs/configuration/resources.html#meta-arguments)

![terraform](terraform.png)

Allow Terraform an high level of control flow and his life cycle
It don't map direct to the cloud or API but helps Terraform to add some logical to his actions, like this arguments can decide if the terraform execution order will be sequential or parallel, as example if you use depends_on, Terraform will be sequential as one resource will depend of other.

1) [depends_on, for specifying hidden dependencies](https://www.terraform.io/docs/configuration/resources.html#depends_on-explicit-resource-dependencies)
2) [count, for creating multiple resource instances according to a count](https://www.terraform.io/docs/configuration/resources.html#count-multiple-resource-instances-by-count)
3) [for_each, to create multiple instances according to a map, or set of strings](https://www.terraform.io/docs/configuration/resources.html#for_each-multiple-resource-instances-defined-by-a-map-or-set-of-strings)
4) [provider, for selecting a non-default provider configuration](https://www.terraform.io/docs/configuration/resources.html#provider-selecting-a-non-default-provider-configuration)
5) [lifecycle, for lifecycle customizations](https://www.terraform.io/docs/configuration/resources.html#lifecycle-lifecycle-customizations)
6) [provisioner and connection, for taking extra actions after resource creation](https://www.terraform.io/docs/configuration/resources.html#provisioner-and-connection-resource-provisioners)

example: on module module_web > main.tf the meta parameter count is initiated by the variable instance_count

```terraform
resource "aws_instance" "web" {
  count = "${var.instance_count}"
  # count initiate the default variable count as value 2
}
```
