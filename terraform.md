# Terraform Notes


## Notes
- [Debugging log levels are TRACE, DEBUG, INFO, WARN or ERROR to change the verbosity of the logs](https://www.terraform.io/docs/internals/debugging.html)
- [Data sources - get info of resources outside terraform](https://www.terraform.io/docs/language/data-sources/index.html)
- [resource lifecycle rules](https://www.terraform.io/docs/language/meta-arguments/lifecycle.html)
  -  create_before_destroy, prevent_destroy, ignore_changes
-  Count uses index of list. [Ref](https://www.terraform.io/docs/language/meta-arguments/count.html)
-  for_each uses a map [Ref](https://www.terraform.io/docs/language/meta-arguments/for_each.html)

## Useful commands

[TF commands reference](https://www.terraform.io/docs/cli/index.html)

```bash

terraform -help

#idempotent
terraform init

# validate configs
terraform validate

# format
terraform fmt

terraform show

terraform workspace list
terraform workspace select <tf workspace name>

#delete all states
terraform state list | xargs -n 1 terraform state rm
```
