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

sdk = geezeo.sdk(api_key, user_id, url)
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

sdk.get_featured_institutions()

```

> Returns list of [FinancialInstitution](#python-financialinstitution) objects.

Partners can maintain a list of featured institutions. This method will return that list in the specified order. 

Contact support to change the list of featured institutions for a partner.
 

## get_all_institutions

## search_institutions

## get_institution

## authenticate

## change_authentication