# DRAFT Python Aggregation SDK Types DRAFT

## UnauthorizedError
## DoesNotExistError
## NetworkError
## MFARequiredError
| Property | Description |
| -------- | ----------- |
| AuthPrompt | An additional [AuthPrompt](#authprompt) for the user to complete. There may be multiple is succession. |


## AuthPrompt
| Property | Description |
| -------- | ----------- |
| id  | Identifier for this financial institution. |
| name | Name of this financial institution.|
| url      | url of this financial institution. |
| login_parameters | A list of [AuthParameter](#python-authparameter) objects for authentication. |
| submit_key | The key for this auth prompt. This key should be used when submitting this AuthPrompt for authentication. |

| Operation | Description |
| -------- | ----------- |
| to_json | Create a json representation. |

## AggregatedInstitution
| Property | Description |
| -------- | ----------- |
| id  | Identifier for this financial institution. |
| name | Name of this financial institution.|
| url      | url of this financial institution. |
| accounts | An array of accounts for this institution. |

| Operation | Description |
| -------- | ----------- |
| to_json | Create a json representation. |


## AuthParameter
| Property | Description |
| -------- | ----------- |
| key | String that identifies this parameter uniquely among the parameters for the parent prompt.|
| caption |  String challenge for the user, e.g. "What is your favorite color?". |
| type | String description of the information to be provided, e.g. "password". |
| max_length | Maximum length that the answer for the parameter can have (int). |
| value | The value parameter should be provided by the end user. It will default to *None*. |

| Operation | Description |
| -------- | ----------- |
| to_json | Create a json representation. |
