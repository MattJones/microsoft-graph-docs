﻿# Update eBookVppGroupAssignment

> **Important:** APIs under the /beta version in Microsoft Graph are in preview and are subject to change. Use of these APIs in production applications is not supported.

> **Note:** Using the Microsoft Graph APIs to configure Intune controls and policies still requires that the Intune service is [correctly licensed](https://go.microsoft.com/fwlink/?linkid=839381) by the customer.

Update the properties of a [eBookVppGroupAssignment](../resources/intune_books_ebookvppgroupassignment.md) object.
## Prerequisites
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](../../../concepts/permissions_reference.md).

|Permission type|Permissions (from most to least privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementApps.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /deviceAppManagement/managedEBooks/{managedEBookId}/groupAssignments/{eBookGroupAssignmentId}
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
In the request body, supply a JSON representation for the [eBookVppGroupAssignment](../resources/intune_books_ebookvppgroupassignment.md) object.

The following table shows the properties that are required when you create the [eBookVppGroupAssignment](../resources/intune_books_ebookvppgroupassignment.md).

|Property|Type|Description|
|:---|:---|:---|
|targetGroupId|String|The Id of the AAD group we are targeting the eBook to. Inherited from [eBookGroupAssignment](../resources/intune_books_ebookgroupassignment.md)|
|id|String|Key of the entity. Inherited from [eBookGroupAssignment](../resources/intune_books_ebookgroupassignment.md)|
|installIntent|String|The install intent defined by the admin. Inherited from [eBookGroupAssignment](../resources/intune_books_ebookgroupassignment.md) Possible values are: `available`, `required`, `uninstall`, `availableWithoutEnrollment`.|
|useDeviceLicensing|Boolean|Whether or not to use device licensing.|



## Response
If successful, this method returns a `200 OK` response code and an updated [eBookVppGroupAssignment](../resources/intune_books_ebookvppgroupassignment.md) object in the response body.

## Example
### Request
Here is an example of the request.
``` http
PATCH https://graph.microsoft.com/beta/deviceAppManagement/managedEBooks/{managedEBookId}/groupAssignments/{eBookGroupAssignmentId}
Content-type: application/json
Content-length: 111

{
  "targetGroupId": "Target Group Id value",
  "installIntent": "required",
  "useDeviceLicensing": true
}
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 222

{
  "@odata.type": "#microsoft.graph.eBookVppGroupAssignment",
  "targetGroupId": "Target Group Id value",
  "id": "5f54e6bf-e6bf-5f54-bfe6-545fbfe6545f",
  "installIntent": "required",
  "useDeviceLicensing": true
}
```



