## size

<!-- ```php
``` -->

The `size` function uses PHP native `filesize` function to determine the size of a file and return it in a readable format. It will return units in the size of `B`, `KB`, `MB`, and `GB`.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
path | `string` | | Path to the file based on PHP's `filesize` requirements

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` |
Error | `int` | `0`

`Helper: helpers`

## sanitize

<!-- ```php
``` -->

The `sanitize` function uses PHP's native `htmlentities` function to sanitize a string. It is sanitized with the flag `ENT_QUOTES` and encoded in `UTF-8`. This function will return the sanitized string.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
string | `string` | | The string to be sanitized

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` |

`Helper: helpers`

## currentPage

<!-- ```php
``` -->

The `currentPage` function will return the current file name without the URL.

Example:
If you are visiting `https://example.com/test.php` it would return `test.php`

### Parameters
None

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` |

`Helper: helpers`

## currentFolder

<!-- ```php
``` -->

The `currentFolder` function will return the current folder name without the URL or file.

Example:
If you are visiting `https://example.com/test/index.php` it would return `test`

### Parameters
None

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` |

`Helper: helpers`

## format_date

<!-- ```php
``` -->

<aside class="notice">
    This function is currently outdated and will not work as one may expect with the required parameters. The timezone parameter isn't currently used in the code despite it being required.
</aside>

The `format_date` function takes a plain text timestamp and returns it in this format using `DateTime`: `m/d/y ~ h:iA`

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
date | `string` | | The datetime stamp (expected format: Y-m-d H:i:s) to be converted into a `DateTime` format
tz | `string` | | The timezone to configure with DateTime

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `DateTime` |
Error |  |

`Helper: helpers`

## abrev_date

<!-- ```php
``` -->

<aside class="notice">
    This function is currently outdated and will not work as one may expect with the required parameters. The timezone parameter isn't currently used in the code despite it being required.
</aside>

The `abrev_date` function will take a plain text timestamp and return it using `DateTime` in this format: `M d, Y`

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
date | `string` | | The datetime stamp (expected format: Y-m-d H:i:s) to be converted into a `DateTime` format
tz | `string` | | The timezone to configure with DateTime

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `DateTime` |
Error |  |

`Helper: helpers`

## money

<!-- ```php
``` -->

They `money` function will take a raw string that can be converted into `decimal` or `int` value and convert it into a formatted money string, prefixed with `$` and rounded to 2 decimal places.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
ugly | `string` | | The raw value that can be converted into an `int` or `decimal` value

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` | `$0.00`
Error | |

`Helper: helpers`

## display_errors

<!-- ```php
``` -->

The `display_errors` function is used in conjunction with the validation class to take an array of strings and produce a error block HTML to be used on your page. This will be in an unordered list with two classes, `bg-danger` and `dangerblock`. It will also attach a `has-error` class to the closest `div` in the parent.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
errors | `array` | `[]` | The array of errors

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` | Raw HTML that can be used on your page

`Helper: helpers`

## display_successes

The `display_successes` function is used in conjunction with the validation class to take an array of strings and produce a success block HTML to be used on your page. This will be in an unordered list with no classes.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
errors | `array` | `[]` | The array of errors

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` | Raw HTML that can be used on your page

`Helper: helpers`

## email

<!-- ```php
``` -->

The `email` function uses UserSpice's built in PHP Mailer to send an email using the options you have set in your Email Settings in the Dashboard.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
to | `string` | | The recipients email address
subject | `string` | | The subject of your email
body | `string` | | The body of your email
opts | `array` | `[]` | Any additional options you wish to send to the mailer, currently, the supported keys are `email` (from email) and `name` (from name)
attachment | `file` | | The file you wish to attach

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `Object` | [PHP Mailer Object](#php-mailer-object)
Error | `Object` | [PHP Mailer Object](#php-mailer-object)

`Helper: helpers`

## email_body

<!-- ```php
``` -->

The `email_body` function is used in conjunction with the `email` function to generate a body from the `users` and `usersc` view folders. The template is passed along with options to customize the data in the template.

<aside class="notice">
    Templates in the `usersc` views folder take priority over that of the `users` folder
</aside>

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
template | `string` | | The template name (only - do not include the extension) that you wish to send
options | `array` | `[]` | The options you wish to pass into the template

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `Raw Data` | [ob_get_clean](https://www.php.net/manual/en/function.ob-get-clean.php)
Error | `Raw Data` | [ob_get_clean](https://www.php.net/manual/en/function.ob-get-clean.php)

`Helper: helpers`

## dump

<!-- ```php
``` -->

The `dump` function is a pre-formatted echo of `var_dump` with several custom options allowing you to use it for development and administrative only purposes.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
var | `mixed` | | Any data you wish to `var_dump`
adminOnly | `boolean` | `false` | If you wish to only show the dump to users who pass an [isAdmin](#isadmin) check
localhostOnly | `boolean` | `false` | If you wish to only show the dump when a pass is obtained during an [isLocalhost](#islocalhost) check

`Helper: helpers`

## dnd

<!-- ```php
``` -->

The `dnd` function is pointed at the [dump](#dump) function. After the [dump](#dump) is completed, a `die` is triggered. Parameters are the same as [dump](#dump).

`Helper: helpers`

## bold

<!-- ```php
``` -->

The `bold` function will echo the supplied text in a:

* `text` with `padding=1em` `align=center`
* `h4`
* `span` with `background=white`

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
text | `string` | | The string you wish to output
`Helper: helpers`

## err

<!-- ```php
``` -->

The `err` function will echo the supplied text in a:

* `text` with `padding=1em` `align=center`
* `font` with `color=red`
* `h4`
* `span` with `class=errSpan`

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
text | `string` | | The string you wish to output

`Helper: helpers`

## redirect

<!-- ```php
``` -->

The `redirect` function does a simple `header` redirect to the URL provided. This provides no sanitization or validation and should not be mistaken with the [Redirect::to](#redirect::to) Method

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
location | `string` | | The URL you wish to redirect to

`Helper: helpers`

## write_php_ini
`Helper: helpers`

`Parameters: $array, $file`

## safefilerewrite
`Helper: helpers`

`Parameters: $fileName, $dataToSave`
