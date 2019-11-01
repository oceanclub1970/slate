--- 

title: Fenergo Data Integration Manager API 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

**Version:** 1 

# /REST/BUSINESSSERVICE/DOCUMENTREQUIREMENT/{DOCREQUIREID}/LEGALENTITY/{LEGALENTITYID}/CASE/{CASEID}/DOCUMENT/{DOCUMENTID}/LINKAGE
## ***POST*** 

**Summary:** Linking of Document to Document Requirement for a Case.

### HTTP Request 
`***POST*** /rest/businessService/documentRequirement/{docRequireId}/legalEntity/{legalEntityId}/case/{caseId}/document/{documentId}/linkage` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| docRequireId | path | Document Require Id (Updates Status of the Document Requirement). | Yes | integer |
| legalEntityId | path | Legal Entity ID. | Yes | integer |
| caseId | path | Case ID | Yes | string |
| documentId | path | Document ID | Yes | string |
| linkStatus | query | Link Status 0 = Not Active 1 = Active | Yes | string |
| rowVersion | query | Row Version [URL Encoded value] | Yes | string |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LINKLOOKUP
## ***POST*** 

**Summary:** Get Link Lookup Table Data

### HTTP Request 
`***POST*** /rest/linkLookup` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| Version | header | Version of Resource Supplied by Client | No | string |
| body | body | LookupLink Request Body | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LOOKUP
## ***POST*** 

**Summary:** Get Lookup Table Data

### HTTP Request 
`***POST*** /rest/lookup` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| includeIsInactive | query | Include inactive lookup values in response | No | boolean |
| Version | header | Version of Resource Supplied by Client | No | string |
| body | body | Lookup Request Body | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/DOCUMENT/{DOCUMENTID}/LEGALENTITY/{LEGALENTITYID}
## ***DELETE*** 

### HTTP Request 
`***DELETE*** /rest/document/{documentId}/legalEntity/{legalEntityId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| documentId | path | Document Id | Yes | integer |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/DOCUMENT/{DOCUMENTID}/LEGALENTITY/{LEGALENTITYID}/CASE/{CASEID}
## ***DELETE*** 

### HTTP Request 
`***DELETE*** /rest/document/{documentId}/legalEntity/{legalEntityId}/case/{caseId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| documentId | path | Document Id | Yes | integer |
| caseId | path | Case Id | Yes | integer |
| taskId | query | Task Id | No | integer |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/CASE/{CASEID}
## ***GET*** 

**Summary:** GET Case Metadata

### HTTP Request 
`***GET*** /rest/case/{caseId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| caseId | path | Case Id | Yes | integer |
| legalEntityId | query | Legal Entity Id | Yes | integer |
| formId | query | Form Id | Yes | string |
| Editable | query | Editable Flag | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***PUT*** 

**Summary:** Update Case

### HTTP Request 
`***PUT*** /rest/case/{caseId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| caseId | path | Case Id | Yes | integer |
| formId | query | Form Id | Yes | string |
| legalEntityId | query | Legal Entity Id | Yes | integer |
| body | body | Request Body | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}
## ***GET*** 

**Summary:** Combined GET Legal Entity Metadata/Only returns data in readonly mode. Cannot update entity without associated process(taskId)

### HTTP Request 
`***GET*** /rest/legalEntity/{legalEntityId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***POST*** 

**Summary:** Update Legal Entity and Complete Task

### HTTP Request 
`***POST*** /rest/legalEntity/{legalEntityId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| formId | query | Form Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| group | query | Group | No | boolean |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***PUT*** 

**Summary:** Update Legal Entity (DO NOT Complete Task)

### HTTP Request 
`***PUT*** /rest/legalEntity/{legalEntityId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | string |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/ADDRESS
## ***POST*** 

**Summary:** Create Address

### HTTP Request 
`***POST*** /rest/legalEntity/{legalEntityId}/address` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/ADDRESS/{ADDRESSID}
## ***GET*** 

**Summary:** GET Address Metadata

### HTTP Request 
`***GET*** /rest/legalEntity/{legalEntityId}/address/{addressId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| addressId | path | Address Id | Yes | integer |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | No | string |
| caseId | query | Case Id | No | integer |
| taskId | query | Task Id | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***PUT*** 

**Summary:** Edit Address Subform

### HTTP Request 
`***PUT*** /rest/legalEntity/{legalEntityId}/address/{addressId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| addressId | path | Address Id | Yes | integer |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***DELETE*** 

**Summary:** Delete Address Subform

### HTTP Request 
`***DELETE*** /rest/legalEntity/{legalEntityId}/address/{addressId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| addressId | path | Address Id | Yes | integer |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/ASSOCIATION
## ***POST*** 

**Summary:** Create Association. Only returns data in readonly mode. Cannot update entity without associated process(taskId).

### HTTP Request 
`***POST*** /rest/legalEntity/{legalEntityId}/association` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| associationId | path | Association Id | Yes | integer |
| formId | query | Form Id | Yes | string |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id. Where not specified form will be returned in readOnly. | Yes | integer |
| tolegalEntityId | query | Legal Entity to Associate to. | Yes | integer |
| body | body | Request Body | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/ASSOCIATION/{ASSOCIATIONID}
## ***GET*** 

**Summary:** Get Association Metadata and data. Only returns data in readonly mode. Cannot update entity without associated process(taskId).

### HTTP Request 
`***GET*** /rest/legalEntity/{legalEntityId}/association/{associationId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| associationId | path | Association Id | Yes | integer |
| formId | query | Form Id | Yes | string |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id. Where not specified form will be returned in readOnly. | Yes | integer |
| tolegalEntityId | query | Legal Entity to Associate to. | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***PUT*** 

**Summary:** Update Association. Only returns data in readonly mode. Cannot update entity without associated process(taskId).

### HTTP Request 
`***PUT*** /rest/legalEntity/{legalEntityId}/association/{associationId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| associationId | path | Association Id | Yes | integer |
| formId | query | Form Id | Yes | string |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id. Where not specified form will be returned in readOnly. | Yes | integer |
| tolegalEntityId | query | Legal Entity to Associate to. | Yes | integer |
| body | body | Request Body | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***DELETE*** 

**Summary:** Remove Association. Only returns data in readonly mode. Cannot update entity without associated process(taskId).

### HTTP Request 
`***DELETE*** /rest/legalEntity/{legalEntityId}/association/{associationId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| associationId | path | Association Id | Yes | integer |
| formId | query | Form Id | Yes | string |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id. Where not specified form will be returned in readOnly. | Yes | integer |
| tolegalEntityId | query | Legal Entity to Associate to. | Yes | integer |
| immutable | query | Immutable delete. | Yes | boolean |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/DOCUMENT
## ***POST*** 

**Summary:** Create Document (This should only be used for fileless documents or where location is supplied)

### HTTP Request 
`***POST*** /rest/legalEntity/{legalEntityId}/document` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| subformId | query | Subform Id | No | string |
| caseId | query | Case Id | No | integer |
| taskId | query | Task Id | No | integer |
| documentRequirementId | query | Document Requirement Id. Used to link a document to a document requirement | No | integer |
| legalEntityId | path |  | Yes | string |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/DOCUMENT/{DOCUMENTID}
## ***GET*** 

**Summary:** GET Document Metadata

### HTTP Request 
`***GET*** /rest/legalEntity/{legalEntityId}/document/{documentId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| documentId | path | Docuemnt  Id | Yes | integer |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | No | string |
| caseId | query | Case Id | No | integer |
| taskId | query | Task Id | No | integer |
| documentRequirementId | query | DocumentRequirementId Id | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/PRODUCT
## ***POST*** 

**Summary:** Create Product

### HTTP Request 
`***POST*** /rest/legalEntity/{legalEntityId}/product` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/PRODUCT/{PRODUCTID}
## ***GET*** 

**Summary:** GET Product Metadata

### HTTP Request 
`***GET*** /rest/legalEntity/{legalEntityId}/product/{productId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| productId | path | Address Id | Yes | integer |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | No | string |
| caseId | query | Case Id | No | integer |
| taskId | query | Task Id | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***PUT*** 

**Summary:** Edit Product Subform

### HTTP Request 
`***PUT*** /rest/legalEntity/{legalEntityId}/product/{productId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| productId | path | Product Id | Yes | integer |
| subformId | query | Subform Id | Yes | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/TAXIDENTIFIER
## ***POST*** 

**Summary:** Create a Tax Id

### HTTP Request 
`***POST*** /rest/legalEntity/{legalEntityId}/taxIdentifier` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | No | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/LEGALENTITY/{LEGALENTITYID}/TAXIDENTIFIER/{TAXIDENTIFIERID}
## ***GET*** 

**Summary:** GET Tax Id Metadata

### HTTP Request 
`***GET*** /rest/legalEntity/{legalEntityId}/taxIdentifier/{taxIdentifierId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| taxIdentifierId | path | Tax IdentifierId Id | Yes | integer |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | No | string |
| caseId | query | Case Id | No | integer |
| taskId | query | Task Id | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***PUT*** 

**Summary:** Update Tax Id

### HTTP Request 
`***PUT*** /rest/legalEntity/{legalEntityId}/taxIdentifier/{taxIdentifierId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| taxIdentifierId  | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | No | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| taxIdentifierId | path |  | Yes | string |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***DELETE*** 

**Summary:** Remove Tax Id from Legal Entity

### HTTP Request 
`***DELETE*** /rest/legalEntity/{legalEntityId}/taxIdentifier/{taxIdentifierId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | query | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| taxIdentifierId  | path | Legal Entity Id | Yes | integer |
| subformId | query | Subform Id | No | string |
| caseId | query | Case Id | Yes | integer |
| taskId | query | Task Id | Yes | integer |
| taxIdentifierId | path |  | Yes | string |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/FORM/{FORMID}
## ***GET*** 

**Summary:** Get Metadata for a Static Form (No Data Returned by Default)

### HTTP Request 
`***GET*** /rest/form/{formId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | path | Form Id | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/FORM/{FORMID}/LEGALENTITY/{LEGALENTITYID}
## ***GET*** 

**Summary:** GET Legal Entity Metadata (Deprecated)

### HTTP Request 
`***GET*** /rest/form/{formId}/legalEntity/{legalEntityId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | path | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/FORM/{FORMID}/LEGALENTITY/{LEGALENTITYID}/CASE/{CASEID}/TASK/{TASKID}
## ***GET*** 

**Summary:** Only returns data in readonly mode. Cannot update entity without associated process(taskId) (Deprecated)

### HTTP Request 
`***GET*** /rest/form/{formId}/legalEntity/{legalEntityId}/case/{caseId}/task/{taskId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | path | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| caseId | path | Case Id | Yes | integer |
| taskId | path | Task Id | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***POST*** 

**Summary:** Post Entity Data Values for formId (Deprecated)

### HTTP Request 
`***POST*** /rest/form/{formId}/legalEntity/{legalEntityId}/case/{caseId}/task/{taskId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | path | formId(context) | Yes | string |
| legalEntityId | path | legalEntityId | Yes | string |
| caseId | path | caseId | Yes | string |
| taskId | path | taskId | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

## ***PUT*** 

**Summary:** Update Legal Entity (DO NOT Complete Task) (Deprecated)

### HTTP Request 
`***PUT*** /rest/form/{formId}/legalEntity/{legalEntityId}/case/{caseId}/task/{taskId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | path | Form Id | Yes | string |
| legalEntityId | path | Legal Entity Id | Yes | integer |
| caseId | path | Case Id | Yes | integer |
| taskId | path | Task Id | Yes | string |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

# /REST/FORM/{FORMID}/REFRESH/{CONTEXTID}
## ***POST*** 

**Summary:** Get refreshed data for a DataGrid (No Metadata)

### HTTP Request 
`***POST*** /rest/form/{formId}/refresh/{ContextId}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| formId | path | formId | Yes | string |
| ContextId | path | Context for data to be returned (IE: datagridContext or formId) | Yes | string |
| body | body | Request Body | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Output type |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
