	# OVERVIEW

The 6px API is built on HTTP. Our API is [RESTful](http://en.wikipedia.org/wiki/Representational_State_Transfer) and it:

* Has predictable, resource-oriented URLs
* Uses built-in HTTP capabilities for passing parameters
* Responds with standard HTTP response codes to indicate errors
* Sends and receives data as [JSON](http://en.wikipedia.org/wiki/JSON)

To give you an idea of how to use the API, we have annotated our documentation with code samples written in curl.

## BASE URL

All API endpoints referenced in this documentation should start with the following base URL:

```bash
https://api.6px.io/v1/
```

## AUTHENTICATION

When you sign up for an account, you are given an API key and secret. You authenticate with the 6px API by providing your API key and secret in every request. You can manage your API key and secret in the `My Account` section of the [dashboard](http://6px.io/login).

```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?key=YOUR_KEY&secret=YOUR_SECRET
```

> **Authentication using an API secret should only be used in server to server scenarios. If you're making a request via from a browser via AJAX, please omit the secret and ensure that the requesting domain is whitelisted in the account section of your dashboard.**


## DATE FORMAT

6px returns JSON for all API calls. Dates are passed as an [ISO 8601](http://en.wikipedia.org/wiki/ISO_8601) formatted datetime.

```bash
2014-01-23T19:40:42+17:00
```

## ERRORS


| Code    | Error                 | Description                                                                        |
|---------|-----------------------|------------------------------------------------------------------------------------|
| `200`   | OK                    | Everything worked as expected                                                      |
| `400`   | Bad Request           | Often missing a required parameter                                                 |
| `401`   | Unauthorized          | Invalid API key or secret, or the domain is not allowed                            |
| `404`   | Not Found             | The requested resource doesn't exist                                               |
| `429`   | Too Many Requests     | You are sending too many requests too quickly or you have met your plans API quota |
| `500`   | Internal Server Error | Something went wrong on our end                                                    |

## LIMITS

Rate limits are defined by the number of API calls allowed by your subscription. Only `POST` requests to create a job are metered.

## PAGINATION

Requests that return multiple results will be paginated to 10 resources by default. You can specify further resources with the `?page` parameter.

```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?page=2
```

To increase the number of resources returned, simply pass the `?per_page` parameter.

```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?page=2&per_page=100
```

## SORTING

**Sort by value:**

```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?sort_by=created
```

**Sort by value (descending):**

```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?sort_by=created,desc
```

**Sort by value (ascending):**

```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?sort_by=created,asc
```

## HELP US HELP YOU

Please let us how we can make this API better. If you have a specific feature request or found a bug, please [create a GitHub issue](https://github.com/6px-io/6px-api-docs/issues).
