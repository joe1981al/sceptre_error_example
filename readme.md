## Error Example

###Base Stack Works

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
