# Update TFC Workspace Variable Value Action

This action is used to update the value of a Terraform Cloud workspace variable.

## Inputs

The action expects the following inputs:

| Variable        | Required | Description                                                                  |
| --------------- | -------- | ---------------------------------------------------------------------------- |
| `tfcToken`      | Yes      | A Terraform Cloud API token with access to manage the workspace.             |
| `orgName`       | Yes      | The name of the Terraform Cloud organization in which the workspace resides. |
| `workspaceName` | Yes      | The name of the Terraform Cloud workspace to manage.                         |
| `variableName`  | Yes      | The name of the variable.                                                    |
| `value`         | No       | The variable's new value. Defaults to an empty string.                       |

## Outputs

The action generates no outputs.

## Example Usage

```yaml
- name: Set some secret key
    uses: cbsinteractive/update-tfc-workspace-variable-value-action@v1
    with:
        tfcToken: ${{ secrets.tfc_org_token }}
        orgName: ${{ secrets.tfc_org }}
        workspaceName: some-tfc-workspace-name
        variableName: some_secret_key
        value: ${{ secrets.some_secret_key }}
```

This example assumes variables stored as GitHub [encrypted secrets][].

[encrypted secrets]: https://docs.github.com/en/actions/reference/encrypted-secrets
