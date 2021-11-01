# Terraform Notes


## Notes
- https://www.terraform.io/docs/internals/debugging.html log levels are TRACE, DEBUG, INFO, WARN or ERROR to change the verbosity of the logs
- [resource lifecycle rules](https://www.terraform.io/docs/language/meta-arguments/lifecycle.html)

## Useful commands

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
