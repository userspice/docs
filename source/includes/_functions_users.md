## userIdExists

```php
$userCheck = userIdExists(1);

if($userCheck) {
  echo "ID 1 exists";
} else {
  echo "ID 1 does NOT exists";
}
```

Check if the provided User ID exists in the users table

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
id | `int` | | The ID of the user to verify

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `boolean` | `true`
Error | `boolean` | `false`

`Helper: users`

## fetchAllUsers

```php
$orderBy = 'lname DESC, fname'; //orders by lname desc, fname
$desc = true; //forces last orderBy param to be desc as well, if no order by is passed, this doesnt do anything
$disabled = false; //removes users who are disabled, DB column permissions
$users = fetchAllUsers($orderBy, $desc, $disabled);

foreach($users as $u) {
  dump($u);
}
```

Fetches an object of users based on the parameters included

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
orderBy | `string` | `null` | Comma seperated params of order by clause to send to the database
desc | `boolean` | `false` | An optional value to order the orderBy in a descending fashion
disabled | `boolean` | `true` | Pass false to remove disabled users from the return

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `Object` | Collection of [User Object](#user-object)
Error | `Object` | Empty

`Helper: users`

## fetchUserDetails

```php
//Good Result:
$id = 1;
$fetchedUser = fetchUserDetails(NULL, NULL, $id); //Returns object

$username = 'admin';
$fetchedUser = fetchUserDetails($username); //Returns object

//Bad Result:
$id = 'admin';
$fetchedUser = fetchUserDetails(NULL, NULL, $id); //Returns null
```

Fetches an object of a user based on the parameters included

### Parameters

<aside class="notice">
    You must supply at least one of the parameters.
</aside>

Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
username | `string` | `null` | Username for lookup
token | `string` | `null` | Deprecated feature
id | `int` | `null` | User ID for lookup

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `Object` | [User Object](#user-object)
Error | `null` |

`Helper: users`

## deleteUsers

```php
//Good Result:
$users = [1,2,3];
$deleteUsers = deleteUsers($users); // returns 3 - number of looped users - may not be the actual number deleted

//Bad Result:
$users = ['username'];
$deleteUsers = deleteUsers($users); // returns 0 as "username" cannot be converted to an int
```

Delete user(s) by ID

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
users | `array` | `[]` | IDs of users in an array

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `int` | Number of users deleted
Error | `int` | Number of users deleted

`Helper: users`

## echouser

```php
//Good Result:
echouser(1); //echos info from User ID 1 based on Setting in ACP
echouser(1, 3); //echos Username (FName) from User ID 1

//Bad Result:
echouser('admin'); //echos "Unknown" as not a valid User ID
```

Echo a user directly in your code as defined in the Setting in your Admin Panel. An optional parameter can be passed to override the type.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
id | `int` | | The ID of the user to return
echoType | `int` | `null` | An in-line setting override as described below

### echoType
ID | Sample
--------- | -----------
0 | FName Lname
1 | Username
2 | Username (FName LName)
3 | Username (FName)
4 | FName First Inital of LName

`Helper: users`

## echousername

```php
//Good Result:
$username = echousername(1); //returns username from User ID 1

//Bad Result:
$username = echousername('admin'); //returns "Unknown" as not a valid User ID
```

Returns the username of a user by ID

<aside class="notice">
    This does not echo as the function name would imply, it only returns the data.
</aside>

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
id | `int` | | The ID of the user to return

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` |
Error | `string` | `Unknown`

`Helper: users`

## updateUser

```php
//Good Result:
$column = 'fname';
$id = 1;
$value = 'Doe';
$updateUser = updateUser($column, $id, $value); //returns DB result object

$column = 'fname';
$id = 1;
$value = 1;
$updateUser = updateUser($column, $id, $value); //returns DB result object

//Bad Result:
$column = 'fname';
$id = 'jdoe';
$value = 'Doe';
$updateUser = updateUser($column, $id, $value); //returns null, failed as id is not int
```

Update an attribute of a specific user by ID

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
column | `string` | | The name of the column to update
id | `int` | | The ID of the user to update
value | `string` | | The value to set the column to for the user ID

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `Object` | [Database Result Object](#database-result-object)
Error | `null` |

`Helper: users`

## fetchUserName

```php
//Good Result:
$id = 1;
$fetchedUser = fetchUserName(NULL, NULL, $id); //Returns string of fname and lname

$username = 'admin';
$fetchedUser = fetchUserName($username); //Returns string of fname and lname

//Bad Result:
$id = 'admin';
$fetchedUser = fetchUserName(NULL, NULL, $id); //Returns null

$username = 'abc123'; //bad username (this user shouldnt exist)
$fetchedUser = fetchUserName($username); //Returns "Unknown"
```

Fetches a concatenation of the FName and LName from the Users Table for the specified user.

### Parameters

<aside class="notice">
    You must supply at least one of the parameters.
</aside>

Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
username | `string` | `null` | Username for lookup
token | `string` | `null` | Deprecated feature
id | `int` | `null` | User ID for lookup

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `String` |
Error | `null` | Invalid query structure, could be a violated parameter type
Error | `string` | A string value of `Unknown` means no user was found

`Helper: users`

## isAdmin

```php
$isAdmin = isAdmin();

if($isAdmin) {
  echo 'Is Admin';
} else {
  echo 'Is NOT Admin';
}
```

Checks if the current user is:

* Logged in and passes [hasPerm](#hasperm); or
* Is cloaked into a user and passes [hasPerm](#hasperm) for their original User ID

[hasPerm](#hasperm) for this function is tested against the default Administrator Permission Level (ID #2)

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `boolean` | `true`
Error | `boolean` | `false`

`Helper: users`

## name_from_id

```php
//Good Result:
$username = name_from_id(1); //returns username from User ID 1

//Bad Result:
$username = name_from_id('admin'); //returns "-" as not a valid User ID
```

Returns the username of a user by ID with the first character capitalized

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
id | `int` | | The ID of the user to return

### Expected Return
Result | Type | Sample
--------- | ----------- | -----------
Success | `string` |
Error | `string` | `-`

`Helper: users`
