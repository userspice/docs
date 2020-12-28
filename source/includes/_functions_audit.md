## getIP

```php
$ip = getIP();
```

Attempts to retrieve the users IP address. In the event a user is behind a proxy server, this will return the IP based on the following header values. These are retrieved using the `get_env` function and may not be returned if PHP is running as an ISAPI module.

* `HTTP_CLIENT_IP`
* `HTTP_X_FORWARDED_FOR`
* `HTTP_X_FORWARDED`
* `HTTP_FORWARDED_FOR`
* `HTTP_FORWARDED`
* `REMOTE_ADDR`

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
IP | `String` |

`Helper: audit`

## fetchUserjsonPIE

```php
$pie = fetchUserjsonPIE();
```

Returns data for a Pie Chart for Page Permission Counts.

<aside class="warning">
    It is likely this function will be removed from core code in the future. You should implement your own version of this function in custom_functions.php or in your own plugin functions if required.
</aside>

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Data | `Unknown` |

`Helper: audit`

## fetchUserjsonLG2

```php
$loginsBar = fetchUserjsonLG2();
```

Returns data for a Bar Chart for Login Counts.

<aside class="warning">
    It is likely this function will be removed from core code in the future. You should implement your own version of this function in custom_functions.php or in your own plugin functions if required.
</aside>

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Data | `Unknown` |

`Helper: audit`

## fetchUserjsonLG

```php
$signupCounts = fetchUserjsonLG();
```

Returns data for a Bar Chart for Signup Counts.

<aside class="warning">
    It is likely this function will be removed from core code in the future. You should implement your own version of this function in custom_functions.php or in your own plugin functions if required.
</aside>

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Data | `Unknown` |

`Helper: audit`

## fetchAllLatest

```php
$auditData = fetchAllLatest($userid, $start, $end, $eventcode);
```

Retrieves data for Audit Functions

<aside class="warning">
    It is likely this function will be removed from core code in the future. You should implement your own version of this function in custom_functions.php or in your own plugin functions if required.
</aside>

### Parameters

Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
id | `int` | | User ID for lookup
start | `datetime` | |
end | `datetime` | |
eventcode | `string` | | `audit.audit_eventcode`

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Data | `Unknown` |

`Helper: audit`

## countStuff

```php
$count = countStuff($query);
```

This function will count the number of rows for the query.

<aside class="warning">
    It is likely this function will be removed from core code in the future. You should implement your own version of this function in custom_functions.php or in your own plugin functions if required.
</aside>

### Parameters

Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
what | `string` | | Expected to send raw SQL parameters after `FROM`

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Data | `Unknown` |

`Helper: audit`

## countLoginsSince

This function will use the `audit` table to count the number of events since a date based on an eventcode supplied. The audit system isn't heavily maintained, please do not consider this system reliable.

<aside class="warning">
    It is likely this function will be removed from core code in the future. You should implement your own version of this function in custom_functions.php or in your own plugin functions if required.
</aside>

### Parameters

Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
eventcode | `string` | |
since | `datetime` | |

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Count | `int` |

`Helper: audit`

## ago

Return a string to how long ago the supplied timestamp occured. A better function to use is [time2str](#time2str).

<aside class="warning">
    You should use the time2str function instead, this function is likely to be removed from core code in the future.
</aside>

### Parameters

Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
time | `datetime` | |

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Timestamp | `string` |

`Helper: audit`

## fetchAllAudit
`Helper: audit`

`Parameters: None`

## fetchUserAudit
`Helper: audit`

`Parameters: $userid`

## writeAudit
`Helper: audit`

`Parameters: $userid,$userip,$othus,$event,$action,$itemid=0`
