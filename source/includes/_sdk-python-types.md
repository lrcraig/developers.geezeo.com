# DRAFT Python Aggregation SDK Types DRAFT

## UnauthorizedError
## DoesNotExistError
## NetworkError
## Python FinancialInstitution
| Argument | Description |
| -------- | ----------- |
| id  | Identifier for this financial institution |
| name | Name of this financial institution|
| url      | url of this financial institution |
| login_parameters | A list of [AuthParameter](#python-authparameter) objects for authentication |

## Python AuthParameter
| Argument | Description |
| -------- | ----------- |
| key | String that identifies this parameter uniquely among the parameters for the parent prompt.|
| caption |  String challenge for the user, e.g. "What is your favorite color?". |
| type | String description of the information to be provided, e.g. "password". |
| max_length | Maximum length that the answer for the parameter can have (int). |





## Installing the library

> Install from {?}

```shell
```

> Install from {maybe source/git?}

```shell
```

We have packaged our library nicely. It plays well with others.

## Creating an instance

> Factory? Init? SomethingElsE?

```python
import sdk from Geezeo

sdk.makeItGo('https://my.geezeo.url', 'my-api-key', 'users-pcid');

```

Each instance of the SDK is scoped to a single user I think. Our others work this way.


## Get a list of Financial Institutions

> Get a list

```python
import sdk from Geezeo

sdk.makeItGo('https://my.geezeo.url', 'my-api-key', 'users-pcid');

sdk.getMeAListOfFIs()

```

> Return structure
'''json

[
  {
    "name":"a bank",
    "url":"probably",
    "phone":"naw",
    "login_credentials" : [
      "name" : "something"
    ]
  }
]

'''

Here's a list of FI's for your database.

## Header for each operation

> This goes above a code block to explain it breifly

```python
from github import markdown
```

The text for a block always goes beneath the code and > block. It's kind of annoying. 
