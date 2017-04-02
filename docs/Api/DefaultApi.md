# Wrike\Client\DefaultApi

All URIs are relative to *https://www.wrike.com/api/v3*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getContacts**](DefaultApi.md#getContacts) | **GET** /contacts | 
[**getContactsById**](DefaultApi.md#getContactsById) | **GET** /contacts/{contactId} | 
[**getFolders**](DefaultApi.md#getFolders) | **GET** /folders | 
[**getFoldersFromFolderId**](DefaultApi.md#getFoldersFromFolderId) | **GET** /folders/{folderId}/folders | 
[**getTasks**](DefaultApi.md#getTasks) | **GET** /tasks | 
[**getTasksById**](DefaultApi.md#getTasksById) | **GET** /tasks/{taskId} | 
[**getTimelogs**](DefaultApi.md#getTimelogs) | **GET** /timelogs | 
[**getTimelogsForAccount**](DefaultApi.md#getTimelogsForAccount) | **GET** /accounts/{accountId}/timelogs | 
[**getTimelogsForContact**](DefaultApi.md#getTimelogsForContact) | **GET** /contacts/{contactId}/timelogs | 
[**getTimelogsForFolder**](DefaultApi.md#getTimelogsForFolder) | **GET** /folders/{folderId}/timelogs | 
[**getTimelogsForTask**](DefaultApi.md#getTimelogsForTask) | **GET** /tasks/{taskId}/timelogs | 
[**updateMyContact**](DefaultApi.md#updateMyContact) | **PUT** /contacts/{contactId} | 


# **getContacts**
> \Wrike\Client\Model\InlineResponse200 getContacts($me, $metadata, $fields)



List contacts of all users and user groups in all accessible

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$me = true; // bool | If present - only contact info of requesting user is returned
$metadata = "metadata_example"; // string | Metadata filter, exact match for metadata key or key-value pair
$fields = "fields_example"; // string | Json string array of optional fields to be included in the response model

try {
    $result = $api_instance->getContacts($me, $metadata, $fields);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getContacts: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **me** | **bool**| If present - only contact info of requesting user is returned | [optional]
 **metadata** | **string**| Metadata filter, exact match for metadata key or key-value pair | [optional]
 **fields** | **string**| Json string array of optional fields to be included in the response model | [optional]

### Return type

[**\Wrike\Client\Model\InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getContactsById**
> \Wrike\Client\Model\InlineResponse200 getContactsById($contact_id, $metadata, $fields)



List contacts of specified users and user groups

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$contact_id = array("contact_id_example"); // string[] | If present - only contact info of requesting user is returned
$metadata = "metadata_example"; // string | Metadata filter, exact match for metadata key or key-value pair
$fields = "fields_example"; // string | Json string array of optional fields to be included in the response model

try {
    $result = $api_instance->getContactsById($contact_id, $metadata, $fields);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getContactsById: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **contact_id** | [**string[]**](../Model/string.md)| If present - only contact info of requesting user is returned |
 **metadata** | **string**| Metadata filter, exact match for metadata key or key-value pair | [optional]
 **fields** | **string**| Json string array of optional fields to be included in the response model | [optional]

### Return type

[**\Wrike\Client\Model\InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getFolders**
> \Wrike\Client\Model\InlineResponse2001 getFolders($permalink, $descendants, $metadata, $custom_field, $updated_date, $project, $deleted)



Returns list of entries required to build a folder tree for all accounts. This list contains the virtual root and recycle bin folders for each account, which can be used as root nodes for trees. The IDs of the virtual folder could be obtained from the '/accounts' method response. Note: when any of query filter parameters are present (e.g. descendants=false, metadata) response is switched to Folder model.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$permalink = "permalink_example"; // string | Folder permalink, exact match
$descendants = true; // bool | Adds all descendant folders to search scope
$metadata = "metadata_example"; // string | Metadata filter, exact match for metadata key or key-value pair
$custom_field = "custom_field_example"; // string | Custom field filter (id/value). JSON object with 'id' and 'value' properties.
$updated_date = "updated_date_example"; // string | Updated date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$project = true; // bool | Get only projects (true) / only folders (false)
$deleted = true; // bool | Get folders from Root (false) / Recycle Bin (true)

try {
    $result = $api_instance->getFolders($permalink, $descendants, $metadata, $custom_field, $updated_date, $project, $deleted);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getFolders: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **permalink** | **string**| Folder permalink, exact match | [optional]
 **descendants** | **bool**| Adds all descendant folders to search scope | [optional]
 **metadata** | **string**| Metadata filter, exact match for metadata key or key-value pair | [optional]
 **custom_field** | **string**| Custom field filter (id/value). JSON object with &#39;id&#39; and &#39;value&#39; properties. | [optional]
 **updated_date** | **string**| Updated date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **project** | **bool**| Get only projects (true) / only folders (false) | [optional]
 **deleted** | **bool**| Get folders from Root (false) / Recycle Bin (true) | [optional]

### Return type

[**\Wrike\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getFoldersFromFolderId**
> \Wrike\Client\Model\InlineResponse2001 getFoldersFromFolderId($folder_id, $permalink, $descendants, $metadata, $custom_field, $updated_date, $project)



Returns a list of tree entries for subtree of this folder. For root and recycle bin folders, returns folder subtrees of root and recycle bin respectively.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$folder_id = "folder_id_example"; // string | The folder ID
$permalink = "permalink_example"; // string | Folder permalink, exact match
$descendants = true; // bool | Adds all descendant folders to search scope
$metadata = "metadata_example"; // string | Metadata filter, exact match for metadata key or key-value pair
$custom_field = "custom_field_example"; // string | Custom field filter (id/value)
$updated_date = "updated_date_example"; // string | Updated date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$project = true; // bool | Get only projects (true) / only folders (false)

try {
    $result = $api_instance->getFoldersFromFolderId($folder_id, $permalink, $descendants, $metadata, $custom_field, $updated_date, $project);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getFoldersFromFolderId: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **folder_id** | **string**| The folder ID |
 **permalink** | **string**| Folder permalink, exact match | [optional]
 **descendants** | **bool**| Adds all descendant folders to search scope | [optional]
 **metadata** | **string**| Metadata filter, exact match for metadata key or key-value pair | [optional]
 **custom_field** | **string**| Custom field filter (id/value) | [optional]
 **updated_date** | **string**| Updated date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **project** | **bool**| Get only projects (true) / only folders (false) | [optional]

### Return type

[**\Wrike\Client\Model\InlineResponse2001**](../Model/InlineResponse2001.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTasks**
> \Wrike\Client\Model\InlineResponse2002 getTasks($authors, $responsibles, $shareds, $descendants, $title, $status, $importance, $start_date, $due_date, $scheduled_date, $created_date, $updated_date, $completed_date, $permalink, $type, $limit, $sort_field, $sort_order, $sub_tasks, $page_size, $next_page_token, $metadata, $custom_field, $custom_statuses, $fields)



Search among all tasks in all accounts.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$authors = array("authors_example"); // string[] | Authors filter, match of any
$responsibles = array("responsibles_example"); // string[] | Responsibles filter, match of any
$shareds = array("shareds_example"); // string[] | Shared users filter, match of any
$descendants = true; // bool | Adds all descendant folders to search scope
$title = "title_example"; // string | Title filter, exact match
$status = "status_example"; // string | Status filter, match with any of specified constants
$importance = "importance_example"; // string | Importance filter, exact match.
$start_date = "start_date_example"; // string | Start date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$due_date = "due_date_example"; // string | Due date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$scheduled_date = "scheduled_date_example"; // string | Scheduled date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$created_date = "created_date_example"; // string | Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$updated_date = "updated_date_example"; // string | Updated date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$completed_date = "completed_date_example"; // string | Completed date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$permalink = "permalink_example"; // string | Task permalink, exact match
$type = "type_example"; // string | Task type.
$limit = 56; // int | Limit on number of returned tasks
$sort_field = "sort_field_example"; // string | Sort field.
$sort_order = "Asc"; // string | Sort order.
$sub_tasks = true; // bool | Adds subtasks to search scope
$page_size = 3.4; // float | Page size
$next_page_token = "next_page_token_example"; // string | Next page token, overrides any other parameters in request.
$metadata = "metadata_example"; // string | Metadata filter, exact match for metadata key or key-value pair
$custom_field = "custom_field_example"; // string | Custom field filter (id/value). JSON object with 'id' and 'value' properties.
$custom_statuses = "custom_statuses_example"; // string | Custom statuses filter. JSON array with a list of Custom status IDs.
$fields = "fields_example"; // string | \"Json string array of optional fields to be included in the response model.\" \"Available fields: \\n\" \"- authorIds: Author IDs\" \"- hasAttachments: Has attachments\" \"- attachmentCount: Attachment count\" \"- parentIds: List of task parent folder\" \"- superParentIds: List of task super parent folder\" \"- sharedIds: List of user IDs, who have task share\" \"- responsibleIds: List of responsible user IDs\" \"- description: Description\" \"- briefDescription: Brief description\" \"- recurrent: Is a task recurrent\" \"- superTaskIds: List of supertask IDs\" \"- subTaskIds: List of subtask IDs\" \"- dependencyIds: Dependency IDs\" \"- metadata: Task metadata entries\" \"- customFields: Custom fields\"

try {
    $result = $api_instance->getTasks($authors, $responsibles, $shareds, $descendants, $title, $status, $importance, $start_date, $due_date, $scheduled_date, $created_date, $updated_date, $completed_date, $permalink, $type, $limit, $sort_field, $sort_order, $sub_tasks, $page_size, $next_page_token, $metadata, $custom_field, $custom_statuses, $fields);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getTasks: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authors** | [**string[]**](../Model/string.md)| Authors filter, match of any |
 **responsibles** | [**string[]**](../Model/string.md)| Responsibles filter, match of any |
 **shareds** | [**string[]**](../Model/string.md)| Shared users filter, match of any |
 **descendants** | **bool**| Adds all descendant folders to search scope | [optional]
 **title** | **string**| Title filter, exact match | [optional]
 **status** | **string**| Status filter, match with any of specified constants | [optional]
 **importance** | **string**| Importance filter, exact match. | [optional]
 **start_date** | **string**| Start date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **due_date** | **string**| Due date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **scheduled_date** | **string**| Scheduled date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **created_date** | **string**| Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **updated_date** | **string**| Updated date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **completed_date** | **string**| Completed date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **permalink** | **string**| Task permalink, exact match | [optional]
 **type** | **string**| Task type. | [optional]
 **limit** | **int**| Limit on number of returned tasks | [optional]
 **sort_field** | **string**| Sort field. | [optional]
 **sort_order** | **string**| Sort order. | [optional] [default to Asc]
 **sub_tasks** | **bool**| Adds subtasks to search scope | [optional]
 **page_size** | **float**| Page size | [optional]
 **next_page_token** | **string**| Next page token, overrides any other parameters in request. | [optional]
 **metadata** | **string**| Metadata filter, exact match for metadata key or key-value pair | [optional]
 **custom_field** | **string**| Custom field filter (id/value). JSON object with &#39;id&#39; and &#39;value&#39; properties. | [optional]
 **custom_statuses** | **string**| Custom statuses filter. JSON array with a list of Custom status IDs. | [optional]
 **fields** | **string**| \&quot;Json string array of optional fields to be included in the response model.\&quot; \&quot;Available fields: \\n\&quot; \&quot;- authorIds: Author IDs\&quot; \&quot;- hasAttachments: Has attachments\&quot; \&quot;- attachmentCount: Attachment count\&quot; \&quot;- parentIds: List of task parent folder\&quot; \&quot;- superParentIds: List of task super parent folder\&quot; \&quot;- sharedIds: List of user IDs, who have task share\&quot; \&quot;- responsibleIds: List of responsible user IDs\&quot; \&quot;- description: Description\&quot; \&quot;- briefDescription: Brief description\&quot; \&quot;- recurrent: Is a task recurrent\&quot; \&quot;- superTaskIds: List of supertask IDs\&quot; \&quot;- subTaskIds: List of subtask IDs\&quot; \&quot;- dependencyIds: Dependency IDs\&quot; \&quot;- metadata: Task metadata entries\&quot; \&quot;- customFields: Custom fields\&quot; | [optional]

### Return type

[**\Wrike\Client\Model\InlineResponse2002**](../Model/InlineResponse2002.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTasksById**
> \Wrike\Client\Model\InlineResponse2002 getTasksById($task_id, $fields)



Returns complete information about single or multiple tasks.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$task_id = array("task_id_example"); // string[] | A list of task IDS - up to 100 IDs
$fields = "fields_example"; // string | \"Json string array of optional fields to be included in the response model.\" \"Available fields: \\n\" \"- recurrent: Add field to indicate if task is recurrent\" \"- attachmentCount: Attachment count\"

try {
    $result = $api_instance->getTasksById($task_id, $fields);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getTasksById: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **task_id** | [**string[]**](../Model/string.md)| A list of task IDS - up to 100 IDs |
 **fields** | **string**| \&quot;Json string array of optional fields to be included in the response model.\&quot; \&quot;Available fields: \\n\&quot; \&quot;- recurrent: Add field to indicate if task is recurrent\&quot; \&quot;- attachmentCount: Attachment count\&quot; | [optional]

### Return type

[**\Wrike\Client\Model\InlineResponse2002**](../Model/InlineResponse2002.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTimelogs**
> \Wrike\Client\Model\InlineResponse2003 getTimelogs($created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text)



Get all timelog records in all accounts.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$created_date = "created_date_example"; // string | Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$tracked_date = "tracked_date_example"; // string | Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$me = true; // bool | If present - only contact info of requesting user is returned
$descendants = true; // bool | Adds all descendant tasks to search scope
$sub_tasks = true; // bool | Adds subtasks to search scope
$plain_text = false; // bool | Get comment text as plain text, HTML otherwise

try {
    $result = $api_instance->getTimelogs($created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getTimelogs: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **created_date** | **string**| Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **tracked_date** | **string**| Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **me** | **bool**| If present - only contact info of requesting user is returned | [optional]
 **descendants** | **bool**| Adds all descendant tasks to search scope | [optional] [default to true]
 **sub_tasks** | **bool**| Adds subtasks to search scope | [optional] [default to true]
 **plain_text** | **bool**| Get comment text as plain text, HTML otherwise | [optional] [default to false]

### Return type

[**\Wrike\Client\Model\InlineResponse2003**](../Model/InlineResponse2003.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTimelogsForAccount**
> \Wrike\Client\Model\InlineResponse2003 getTimelogsForAccount($account_id, $created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text)



Get all timelog records in the account.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$account_id = "account_id_example"; // string | The contact ID
$created_date = "created_date_example"; // string | Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$tracked_date = "tracked_date_example"; // string | Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$me = true; // bool | If present - only contact info of requesting user is returned
$descendants = true; // bool | Adds all descendant tasks to search scope
$sub_tasks = true; // bool | Adds subtasks to search scope
$plain_text = false; // bool | Get comment text as plain text, HTML otherwise

try {
    $result = $api_instance->getTimelogsForAccount($account_id, $created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getTimelogsForAccount: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **account_id** | **string**| The contact ID |
 **created_date** | **string**| Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **tracked_date** | **string**| Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **me** | **bool**| If present - only contact info of requesting user is returned | [optional]
 **descendants** | **bool**| Adds all descendant tasks to search scope | [optional] [default to true]
 **sub_tasks** | **bool**| Adds subtasks to search scope | [optional] [default to true]
 **plain_text** | **bool**| Get comment text as plain text, HTML otherwise | [optional] [default to false]

### Return type

[**\Wrike\Client\Model\InlineResponse2003**](../Model/InlineResponse2003.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTimelogsForContact**
> \Wrike\Client\Model\InlineResponse2003 getTimelogsForContact($contact_id, $created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text)



Get all timelog records that were created by the user.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$contact_id = "contact_id_example"; // string | The contact ID
$created_date = "created_date_example"; // string | Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$tracked_date = "tracked_date_example"; // string | Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$me = true; // bool | If present - only contact info of requesting user is returned
$descendants = true; // bool | Adds all descendant tasks to search scope
$sub_tasks = true; // bool | Adds subtasks to search scope
$plain_text = false; // bool | Get comment text as plain text, HTML otherwise

try {
    $result = $api_instance->getTimelogsForContact($contact_id, $created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getTimelogsForContact: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **contact_id** | **string**| The contact ID |
 **created_date** | **string**| Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **tracked_date** | **string**| Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **me** | **bool**| If present - only contact info of requesting user is returned | [optional]
 **descendants** | **bool**| Adds all descendant tasks to search scope | [optional] [default to true]
 **sub_tasks** | **bool**| Adds subtasks to search scope | [optional] [default to true]
 **plain_text** | **bool**| Get comment text as plain text, HTML otherwise | [optional] [default to false]

### Return type

[**\Wrike\Client\Model\InlineResponse2003**](../Model/InlineResponse2003.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTimelogsForFolder**
> \Wrike\Client\Model\InlineResponse2003 getTimelogsForFolder($folder_id, $created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text)



Get all timelog records for a folder.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$folder_id = "folder_id_example"; // string | The contact ID
$created_date = "created_date_example"; // string | Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$tracked_date = "tracked_date_example"; // string | Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$me = true; // bool | If present - only contact info of requesting user is returned
$descendants = true; // bool | Adds all descendant tasks to search scope
$sub_tasks = true; // bool | Adds subtasks to search scope
$plain_text = false; // bool | Get comment text as plain text, HTML otherwise

try {
    $result = $api_instance->getTimelogsForFolder($folder_id, $created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getTimelogsForFolder: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **folder_id** | **string**| The contact ID |
 **created_date** | **string**| Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **tracked_date** | **string**| Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **me** | **bool**| If present - only contact info of requesting user is returned | [optional]
 **descendants** | **bool**| Adds all descendant tasks to search scope | [optional] [default to true]
 **sub_tasks** | **bool**| Adds subtasks to search scope | [optional] [default to true]
 **plain_text** | **bool**| Get comment text as plain text, HTML otherwise | [optional] [default to false]

### Return type

[**\Wrike\Client\Model\InlineResponse2003**](../Model/InlineResponse2003.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTimelogsForTask**
> \Wrike\Client\Model\InlineResponse2003 getTimelogsForTask($task_id, $created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text)



Get all timelog records for a task.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$task_id = "task_id_example"; // string | The contact ID
$created_date = "created_date_example"; // string | Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$tracked_date = "tracked_date_example"; // string | Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \"Format: yyyy-MM-dd'T'HH:mm:ss'Z' ('T'HH:mm:ss is optional)\"
$me = true; // bool | If present - only contact info of requesting user is returned
$descendants = true; // bool | Adds all descendant tasks to search scope
$sub_tasks = true; // bool | Adds subtasks to search scope
$plain_text = false; // bool | Get comment text as plain text, HTML otherwise

try {
    $result = $api_instance->getTimelogsForTask($task_id, $created_date, $tracked_date, $me, $descendants, $sub_tasks, $plain_text);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->getTimelogsForTask: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **task_id** | **string**| The contact ID |
 **created_date** | **string**| Created date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **tracked_date** | **string**| Tracked date filter, date match or range (Timestamp semi-open interval) \\n - start (Optional): Range start \\n - equal (Optional): Date exact match value \\n - end (Optional): Range end \\n \&quot;Format: yyyy-MM-dd&#39;T&#39;HH:mm:ss&#39;Z&#39; (&#39;T&#39;HH:mm:ss is optional)\&quot; | [optional]
 **me** | **bool**| If present - only contact info of requesting user is returned | [optional]
 **descendants** | **bool**| Adds all descendant tasks to search scope | [optional] [default to true]
 **sub_tasks** | **bool**| Adds subtasks to search scope | [optional] [default to true]
 **plain_text** | **bool**| Get comment text as plain text, HTML otherwise | [optional] [default to false]

### Return type

[**\Wrike\Client\Model\InlineResponse2003**](../Model/InlineResponse2003.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateMyContact**
> \Wrike\Client\Model\InlineResponse200 updateMyContact($contact_id, $metadata)



Update contact by Id. Please note that only the contact whose the API key belongs to may be updated. For updating users and groups data, you need to use the User and Group related methods.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure OAuth2 access token for authorization: oauth
Wrike\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');
// Configure API key authorization: token
Wrike\Client\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// Wrike\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');

$api_instance = new Wrike\Client\Api\DefaultApi();
$contact_id = "contact_id_example"; // string | The contact ID
$metadata = "metadata_example"; // string | Metadata filter, exact match for metadata key or key-value pair

try {
    $result = $api_instance->updateMyContact($contact_id, $metadata);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DefaultApi->updateMyContact: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **contact_id** | **string**| The contact ID |
 **metadata** | **string**| Metadata filter, exact match for metadata key or key-value pair | [optional]

### Return type

[**\Wrike\Client\Model\InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

[oauth](../../README.md#oauth), [token](../../README.md#token)

### HTTP request headers

 - **Content-Type**: application/x-www-form-urlencoded
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

