### Syntax
```
variable "variable_name" {
  type = variable_type
  default = default_value
  description = variable_description
}
```
* [Optional] `type`: primitive or list or map. Example: `type = "string"`, `type = "list"`.
* [Optional] `default`: default value for `variable_name`. Use when `variable_name` is not set from outside.
* [Optional] `description`: Human readable description for `variable_name`.
* Access variable value: `${var.variable_name}`. Example: `${var.string_var}`, `${var.map_var[0]}`, `${var.list_var[0]}`

### Override
* Create `override.tf` file or ending with `_override.tf` file.
```
# Example: Override variable type and default value:
#
# anyfile.tf
variable "this_var_would_be_overrided" {
  type = "string"
  default = "default string"
}

# override.tf or anyfile_override.tf
variable "this_var_would_be_overrided" {
  type = "boolean"
  default = false
}
```