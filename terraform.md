# Terraform Notes


## Notes
- https://www.terraform.io/docs/internals/debugging.html log levels are TRACE, DEBUG, INFO, WARN or ERROR to change the verbosity of the logs

## Useful commands

```bash
terraform workspace list
terraform workspace select <tf workspace name>

#delete all states
terraform state list | xargs -n 1 terraform state rm
```
