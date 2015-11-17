# DRAFT Python Aggregation SDK operations DRAFT

## Installing the library

> Install from {?}

```shell
```

> Install from {maybe source/git?}

```shell
```

We have packaged our library nicely. It plays well with others.

## Using the library

> These items will be provided during implementation

```python
import geezeo

sdk = geezeo.SDK(api_key, user_id, url)
```

Python SDK for the Geezeo API.

The use of this package starts with an SDK instance, which is created with the authentication information required by Geezeo’s web API.

The constructor can raise an [UnauthorizedError](#unauthorizederror) if api_key is incorrect, or a [DoesNotExistError](#doesnotexisterror) if the user_id doesn’t correspond to an actual user.

| Argument | Description |
| -------- | ----------- |
| api_key  | Authentication key for the partner institution using this SDK. If api_key is invalid, the constructor will raise an UnauthorizedError. |
| user     | User on whose behalf the SDK is being used. Note that the SDK object is constructed with the string user_id, and this attribute will be populated with the corresponding User during construction.|
| url      | URL for the partner institution’s web site. |


Once you have an instance the SDK has methods to handle all of the operations of aggregation.


## get_featured_institutions


```python

sdk.get_featured_institutions(page=None)

```

> Returns list-like object of [AuthPrompt](#authprompt) objects. This object also has current_page and last_page attributes, which allow you to manage pagination.

Partners can maintain a list of featured institutions. This method will return that list in the specified order.

Contact support to change the list of featured institutions for a partner.

| Argument | Description |
| -------- | ----------- |
| page | A specific page to retrieve (defaults to the first page). |

## get_all_institutions

```python

sdk.get_all_institutions(get_all_pages=false, page=1)

```

> Returns list-like object of [AuthPrompt](#authprompt) objects. This object also has current_page and last_page attributes, which allow you to manage pagination.

Partners can request a list institutions supported by the Geezeo aggregation platform.

| Argument | Description |
| -------- | ----------- |
| get_all_pages | The SDK will aggregate all pages into one. WARNING this call will take a LONG time. |
| page | A specific page to retrieve.|



## search_institutions

```python

sdk.get_all_institutions(search_string, scope=None, page=None)

```

> Returns list-like object of [AuthPrompt](#authprompt) objects. This object also has current_page and last_page attributes, which allow you to manage pagination.

Partners can search for an Institutions based on name, url, or both.

| Argument | Description |
| -------- | ----------- |
| search_string | The search term to search for. |
| scope | An optional argument to limit the search to the name or url. Accepted values are ['name', 'url']|
| page | Optional page number, since the results are paginated. Defaults to the first page. |


## get_institution

```python

sdk.get_institution(id)

```

> Returns an [AuthPrompt](#authprompt) object.

Partners can load the AuthPrompt for a specific institution.

| Argument | Description |
| -------- | ----------- |
| id | The id of the institution |

## authenticate

```python

sdk.authenticate(submit_key, parameters)

```

> Raises an [MFARequiredError](#mfarequirederror) if MFA is required.
> Returns an [AggregatedInstitution](#aggregatedinstitution) object.


To execute a specific AuthPrompt request, submit it's submit_key with the list of parameters that were provided.

All parameters should now have a populated value field.

| Argument | Description |
| -------- | ----------- |
| submit_key | An [AuthPrompt](#authprompt) has a submit_key that is used to submit authentication requests.|
| parameters | An [AuthPrompt](#authprompt) has an array of parameters that should be displayed to the user. The users input should be included in the .value property. |


## change_authentication