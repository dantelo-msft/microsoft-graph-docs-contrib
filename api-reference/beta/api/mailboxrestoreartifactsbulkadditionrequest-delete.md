---
title: "Delete mailboxRestoreArtifactsBulkAdditionRequest"
description: "Delete a mailboxRestoreArtifactsBulkAdditionRequest object associated with an exchangeRestoreSession."
author: "vidula-verma"
ms.localizationpriority: medium
ms.subservice: "m365-backup-storage"
doc_type: apiPageType
ms.date: 12/11/2024
---

# Delete mailboxRestoreArtifactsBulkAdditionRequest

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete a [mailboxRestoreArtifactsBulkAdditionRequest](../resources/mailboxrestoreartifactsbulkadditionrequest.md) object associated with an [exchangeRestoreSession](../resources/exchangerestoresession.md).

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "mailboxrestoreartifactsbulkadditionrequest-delete"
}
-->
[!INCLUDE [permissions-table](../includes/permissions/mailboxrestoreartifactsbulkadditionrequest-delete-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /solutions/backupRestore/exchangeRestoreSessions/{exchangeRestoreSessionId}/mailboxRestoreArtifactsBulkAdditionRequests/{mailboxRestoreArtifactsBulkAdditionRequestId}
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "delete_mailboxrestoreartifactsbulkadditionrequest"
}
-->
``` http
DELETE https://graph.microsoft.com/beta/solutions/backupRestore/exchangeRestoreSessions/d8078599-3b3c-568d-b6ff-adf161a42760/mailboxRestoreArtifactsBulkAdditionRequests/4437afcf-e520-463c-90a7-ca96401d8039
```


### Response

The following example shows the response.
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

