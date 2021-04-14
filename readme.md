## Error Example

Code sample to go with github [issue #1000](https://github.com/Sceptre/sceptre/issues/1000)

Error found is when using a `!stack output` in the `scepter_user_data` section of a config it does not add dependencies or resolve unless stack already exists.  The expected behavior would be to have it add dependencies and resolve the same way as when adding in `parameters` section.

This code example has three stacks that all use the same template.
* stack1.yaml: is a base to test against reading output from.
* stack2.yaml: is using a stack_output from stack1 in parameters and no error when validating.
* stack3.yaml: is using a stack_output from stack1 in scepter_user_data and fails validation for missing stack.

### Base Stack Works

`sceptre validate stack1.yaml`
```
Template stack1 is valid. Template details:

{'Parameters': [{'ParameterKey': 'Test', 'DefaultValue': 'default', 'NoEcho': False}], 'Description': 'Stack for Testing'}
```

### Using Stack Output in Parameters Works

`sceptre validate stack2.yaml`
```
Template stack2 is valid. Template details:

{'Parameters': [{'ParameterKey': 'Test', 'DefaultValue': 'default', 'NoEcho': False}], 'Description': 'Stack for Testing'}
```

### Using Stack Output in scepter_user_data Fails

`sceptre validate stack3.yaml`
```
"Stack with id testing-stack1 does not exist"
```

[d]: https://github.com/Sceptre/sceptre/issues/1000
