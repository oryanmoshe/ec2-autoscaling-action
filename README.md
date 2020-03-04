# AWS EC2 autoscaling manager

This action allows you to autoscaling an EC2 autoscaling group by either providing an absolute number for the desired capacity, or a relative fraction.

## Inputs

### `scaling-group`

**Required** - _string_\
The EC2 scaling group name.

### `absolute-desired`

_Optional_ - _number_\
The new desired capacity of the autoscaling group.

### `relative-desired`

_Optional_ - _number_\
A number describing the relative growth (or shrinkage) of the desired capacity in the autoscaling group.

### `minimum-desired`

_Optional_ - _number_\
A number describing the minimum possible desired capacity.

### `maximum-desired`

_Optional_ - _number_\
A number describing the maximum possible desired capacity.

### `retries`

_Optional_ - _integer_\
The number of times you want to try the stability check. Default `2`.

### `aws-access-key-id`

_Optional_ - _string_\
Your AWS ACCESS_KEY_ID.\
Must be provided as an input / defined as an environment variable.

### `aws-secret-access-key`

_Optional_ - _string_\
Your AWS SECRET_ACCESS_KEY.\
Must be provided as an input / defined as an environment variable.

### `aws-region`

_Optional_ - _string_\
Your AWS REGION.\
Must be provided as an input / defined as an environment variable.

### `verbose`

_Optional_ - _boolean_\
Whether to print verbose debug messages to the console. Default `false`.

## Outputs

### `retries`

_integer_\
How many retries happened until success.

## Example usage

### Using all available options

```yaml
uses: oryanmoshe/ecs-wait-action@v1.3
with:
  aws-access-key-id: AKIAIOSFODNN7EXAMPLE
  aws-secret-access-key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
  aws-region: us-east-1
  ecs-cluster: my-ecs-cluster
  ecs-services: '["my-ecs-service-1", "my-ecs-service-2"]'
  retries: 5
  verbose: false
```

### Minimal configuration

```yaml
uses: oryanmoshe/ecs-wait-action@v1.3
with:
  ecs-cluster: my-ecs-cluster
  ecs-services: '["my-ecs-service-1", "my-ecs-service-2"]'
```
