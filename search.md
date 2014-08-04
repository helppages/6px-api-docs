# SEARCH `experimental`

The search functionality is optimized to help you find jobs using query parameters.

**For example:**
* Image(s) within a specific area
* Image(s) with specific methods

## NUMBER

* `?number={all}123,456` Both 123 and 456 must be present
* `?number={nin}123,456` Neither 123 nor 456
* `?number={in}123,456` Either 123 or 456
* `?number={gt}123` > 123
* `?number={gte}123` >= 123
* `?number={lt}123` < 123
* `?number={lte}123` <= 123
* `?number={ne}123` Not 123
* `?number={mod}10,2` Where (number / 10) has remainder 2

**Example:**
```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?processed.bytes={gt}1048576
```

## STRING

* `?string={all}foo,bar` Both foo and bar must be present
* `?string={nin}foo,bar` Neither foo nor bar
* `?string={in}foo,bar` Either foo or bar
* `?string={not}foo` Not foo
* `?string={exact}fOoBaR` Case-sensitive exact match of fOoBaR

**Example:**
```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?status=processing
```

## LOCATION

* `?latlon={near}40.0176,-105.2797,5` Near 40.0176,-105.2797 (with a 5 mile radius)
* `?latlon={near}40.0176,-105.2797` Near 40.0176,-105.2797 (no radius limit, automatically sorts by distance)

**Example:**
```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?processed.images.latlon={near}40.0176,-105.2797,10
```

## DATES

- `date={gt}1999-12-12T13:33:00.000Z` > 1999-12-12T13:33:00.000Z
- `date={gte}1999-12-12T13:33:00.000Z` >= 1999-12-12T13:33:00.000Z
- `date={lt}1999-12-12T13:33:00.000Z` < 1999-12-12T13:33:00.000Z
- `date={lte}1999-12-12T13:33:00.000Z` <= 1999-12-12T13:33:00.000Z
- `date={gt}1999-12-12T13:33:00.000Z{lt}2014-01-01T01:01:01.000Z` between 1999-12-12T13:33:00.000Z and 2014-01-01T01:01:01.000Z

**Example:**
```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?created={gte}1999-12-12T13:33:00.000Z
```
