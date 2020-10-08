## ipCheck
`Helper: us_helpers`

`Parameters: None`

## ipCheckBan
`Helper: us_helpers`

`Parameters: None`

## randomstring
`Helper: us_helpers`

`Parameters: $len`

## get_gravatar
`Helper: us_helpers`

`Parameters: $email, $s = 120, $d = 'mm', $r = 'pg', $img = false, $atts = array(`

## fetchGroupsByMenu
`Helper: us_helpers`

`Parameters: $menu_id`

## updateGroupsMenus
`Helper: us_helpers`

`Parameters: $group_ids, $menu_ids`

## addGroupsMenus
`Helper: us_helpers`

`Parameters: $group_ids, $menu_ids`

## usernameExists
`Helper: us_helpers`

`Parameters: $username`

## getPageFiles
`Helper: us_helpers`

`Parameters: None`

## getUSPageFiles
`Helper: us_helpers`

`Parameters: None`

## sanitizedDest
`Helper: us_helpers`

`Parameters: $varname='dest'`

## resultBlock
`Helper: us_helpers`

`Parameters: $errors,$successes`

## lang
`Helper: us_helpers`

`Parameters: $key,$markers = NULL`

## isValidEmail
`Helper: us_helpers`

`Parameters: $email`

## emailExists
`Helper: us_helpers`

`Parameters: $email`

## updateEmail
`Helper: us_helpers`

`Parameters: $id, $email`

## echoId
`Helper: us_helpers`

`Parameters: $id,$table,$column`

## bin
`Helper: us_helpers`

`Parameters: $number`

## generateForm
`Helper: us_helpers`

`Parameters: $table,$id, $skip=[]`

## generateAddForm
`Helper: us_helpers`

`Parameters: $table, $skip=[]`

## updateFields2
`Helper: us_helpers`

`Parameters: $post, $skip=[]`

## mqtt
`Helper: us_helpers`

`Parameters: $id,$topic,$message`

## clean
`Helper: us_helpers`

`Parameters: $string`

## stripPagePermissions
`Helper: us_helpers`

`Parameters: $id`

## encodeURIComponent
`Helper: us_helpers`

`Parameters: $str`

## logger
`Helper: us_helpers`

`Parameters: $user_id,$logtype,$lognote`

## echodatetime
`Helper: us_helpers`

`Parameters: $ts`

## time2str
`Helper: us_helpers`

`Parameters: $ts`

## ipReason
`Helper: us_helpers`

`Parameters: $reason`

## checkBan
`Helper: us_helpers`

`Parameters: $ip`

## random_password
`Helper: us_helpers`

`Parameters:  $length = 16 `

## returnError
`Helper: us_helpers`

`Parameters: $errorMsg`

## userHasPermission
`Helper: us_helpers`

`Parameters: $userID,$permissionID`

## requestCheck
`Helper: us_helpers`

`Parameters: $expectedAr`

## adminNotifications
`Helper: us_helpers`

`Parameters: $type,$threads,$user_id`

## lognote
`Helper: us_helpers`

`Parameters: $logid`

## isLocalhost
`Helper: us_helpers`

`Parameters: None`

## currentPageStrict
`Helper: us_helpers`

`Parameters: None`

## UserSessionCount
`Helper: us_helpers`

`Parameters: None`

## fetchUserSessions
`Helper: us_helpers`

`Parameters: $all=false`

## fetchAdminSessions
`Helper: us_helpers`

`Parameters: $all=false`

## killSessions
`Helper: us_helpers`

`Parameters: $sessions,$admin=false`

## passwordResetKillSessions
`Helper: us_helpers`

`Parameters: $uid=NULL`

## username_helper
`Helper: us_helpers`

`Parameters: $fname,$lname,$email`

## oxfordList
`Helper: us_helpers`

`Parameters: $data,$opts=[]`

## currentFile
`Helper: us_helpers`

`Parameters: None`

## importSQL
`Helper: us_helpers`

`Parameters: $file`

## pluginActive
`Helper: us_helpers`

`Parameters: $plugin,$checkOnly = false`

## languageSwitcher
`Helper: us_helpers`

`Parameters: None`

## getMyHooks
`Helper: us_helpers`

`Parameters: $opts = []`

## includeHook
`Helper: us_helpers`

`Parameters: $hooks,$position`

## registerHooks
`Helper: us_helpers`

`Parameters: $hooks,$plugin_name`

## deRegisterHooks
`Helper: us_helpers`

`Parameters: $plugin_name`

## shakerIsInstalled
`Helper: us_helpers`

`Parameters: $type,$reserved`

## updateReAuth
`Helper: us_helpers`

`Parameters: $id, $re_auth`

## reAuth
`Helper: us_helpers`

`Parameters: None`

## verifyadmin
`Helper: us_helpers`

`Parameters: $page`

## isJson

<!-- ```php
``` -->

The `isJson` function attempts to decode a string and returns if it was successful or failed.

### Parameters
Parameter | Type | Default Value | Description
--------- | ----------- | ----------- | -----------
string | `string` | | The string you want validation on

### Expected Returned
Result | Type | Sample
--------- | ----------- | -----------
Success | `boolean` | `true`
Error | `boolean` | `false`

`Helper: us_helpers`
`Version: 5.1.7`
