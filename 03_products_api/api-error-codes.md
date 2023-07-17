# API error codes

You can find the list of error codes below.

### Change Log

| *Date* | *Classification* | *Description* |
| ------ | ----------- |----------- |
| 2023-06-22 | Documentation | Minor changes in documentation |
| 2023-06-02 | Documentation | Intial Version of error codes list |

## Severity levels

 - All errors with a severity level of *error* lead to a rejection of the entire product/variant (depending on the level of the error). The product/variant will not be created/updated at all.
 - All errors with a severity level of *warning* lead to a rejection of the individual attribute: The product/variant will still be created/updated in general, however the individual attribute will not be set or - in case of an update - it will be reset.
 - All errors with a severity level of *info* will not affect the data submission and are for information purpose only (e.g. providing information about not yet submitted recommended information)

## List of error codes

| code | severity | level | description |
| ------ | ----------- |----------- |---------|
| ATTRIBUTE_IS_UNKNOWN | warning | product / variant | The transmitted attribute is not known. Please only submit attributes that belong to the category group. |
| ATTRIBUTE_LEVEL_IS_INVALID | warning | product / variant | The level at which the attribute was sent is not correct. Either a product attribute was sent at variation level or a variation attribute was sent at product level. Please check and correct the attribute level and resubmit the product data. |
| ATTRIBUTE_UNIT_IS_INVALID | warning | product / variant | The unit of the attribute is invalid. Please check the unit of the attribute and submit the product data again with correct unit. |
| ATTRIBUTE_VALUE_EXCEEDS_MAX_LENGTH | warning | product / variant | The maximum length of the value has been exceeded. Ensure that the length restriction is met and retransmit the affected product or variant. |
| ATTRIBUTE_VALUE_IS_INVALID | warning | product / variant | The attribute value provided is invalid. Please correct the value to one of the allowed values and upload the affected variations again. |
| ATTRIBUTE_VALUE_IS_NOT_BOOLEAN | warning | product / variant | The attribute value is not boolean. Please correct the value to a boolean value and resubmit the product data. |
| ATTRIBUTE_VALUE_IS_NOT_DATE | warning | product / variant | The attribute value does not correspond to the valid data type. Please submit the value as a date in the format YYYY-MM-DD. |
| ATTRIBUTE_VALUE_IS_NOT_DECIMAL | warning | product / variant | The attribute value does not correspond to the valid data type. Correct the format and resubmit the affected variations. A valid input is e.g.: 5391.22. | 
| ATTRIBUTE_VALUE_IS_NOT_INTEGER | warning | product / variant | The attribute value does not correspond to the valid data type. Correct the format and resubmit the affected variations. A valid input is e.g.: 42. | 
| ATTRIBUTE_VALUE_IS_NOT_POSITIVE | warning | product / variant | The attribute value must not be negative. Please correct the value to one greater than or equal to zero and upload the affected variations again. |
| ATTRIBUTE_VALUE_IS_ZERO | warning | product / variant | The attribute value must not be zero. Please correct the value to a value other than zero and upload the affected variations again. |
| BRAND_ID_IS_UNKNOWN | error | product | The transmitted brand id is not known. Please check the value or contact the support if you want to transmit a new one. |
| CATEGORY_GROUP_ID_IS_UNKNOWN | error | product | The transmitted category group id is not known. A list of valid category group ids can be obtained from the /products/category-groups endpoint. |
| CATEGORY_IS_UNKNOWN | error | product | The transmitted category is not known. Please select a valid category from the list provided for this category group and re-upload the affected product. |
| EAN_IS_INVALID | error | variant | The given EAN is invalid. Please resubmit the data with a valid EAN. |
| EAN_IS_NOT_UNIQUE_WITHIN_PRODUCT | error | product | You have provided one EAN for several variants of the product, however an EAN must be unique for a given variant. Please update the variants. |
| EAN_IS_NOT_UNIQUE_WITHIN_SUPPLIER_CODE | error | product | The given EAN is already in use and may be assigned only once within a supplier. Please update the product which is already assigned with the EAN or contact the support to the delete the existing product. |
| LEGACY_PRODUCT_UPDATE_REQUIRES_ALL_VARIATIONS | error | product | All variations of the product have to be submitted to update this product. Please add the missing variations and re-upload the affected product. |
| LEGACY_SKU_EAN_IS_MISSING | error | product | The ean attribute must be specified for all variations of the product. Please add the EAN attribute, specify a valid EAN and retransmit the affected variations. |
| LEGACY_SKU_IS_ASSOCIATED_TO_DIFFERENT_PRODUCT | error | product | The variation is already associated with another product and cannot be associated with the given product. Please contact support with the code and a list of affected variations. | 
| MEDIA_ASSET_FILE_TYPE_IS_NOT_SUPPORTED | warning | variant | We could not determine the file type of the media asset or the media asset file type ending does not fit the media asset type. Please make sure that the URL refers to an image/document in jpg, jpeg, png or pdf format. | 
| MEDIA_ASSET_IS_NOT_ACCESSIBLE | warning | variant | The provided media asset cannot be accessed. Please make sure that the URL can be accessed from external services (e.g. no password or internal network protection). |
| MEDIA_ASSET_IS_NOT_AVAILABLE | warning | variant | The given media asset cannot be reached. Please provide a valid URL and upload affected variations again. |
| MEDIA_ASSET_IS_NOT_PROCESSABLE | warning | variant | The given media asset cannot be processed. Please provide a valid URL and upload affected variations again. | 
| MEDIA_ASSET_PROTOCOL_IS_UNKNOWN | warning | variant | The provided media asset URI is not supported. Please provide references to media assets as http(s) links only. Other file protocols like (S)FTP are not supported at the moment. |  
| MEDIA_ASSET_SIZE_EXCEEDS_LIMIT | warning | variant | Maximum file size exceeded. For media assets of type IMAGE, DIMENSIONAL_DRAWING, ENERGY_EFFICIENCY_LABEL and MATERIAL_SAMPLE there is a file size limit of 25MB. All other types have a file size limit of 10MB. |
| MEDIA_ASSET_URI_IS_INVALID |  warning | variant | The media asset URL is invalid. Please provide a syntactically correct URL without any special characters. |
| MISSING_VARIATION_TO_UPDATE_PRODUCT_ATTRIBUTE | error | product | To change characteristics on product level, all variations affected by this have to be re-submitted. Please add the missing variations and re-upload the revised data. | 
| PACKING_UNIT_ID_IS_NOT_UNIQUE | error | variant | The packing unit id must be unique within the variation. Assign a unique packing unit id for each packing unit and retransmit affected variations. | 
| PERMISSION_IS_MISSING_FOR_SUPPLIER_CODE | error | product | The permission is missing for the specified supplier code. Please correct the supplier code and retransmit the affected product. In case a correction is not possible please contact the support. |  
| RECOMMENDED_ATTRIBUTE_IS_MISSING | info | product / variant | A recommended attribute was not submitted. Please provide the attribute to enhance the product data quality. |   
| SKU_IS_ASSOCIATED_TO_DIFFERENT_PRODUCT | error | variant | The variation identifier (sku) is already associated to a different product and cannot be associated to the given product. Enter a unique sku and re-upload the affected variations. |
| SKU_IS_NOT_UNIQUE_IN_PRODUCT | error | product | The variation identifier (sku) is already used for this product and must be unique for each variation. Please correct the sku and re-upload the affected variations. |
| SUPPLIER_CODE_IS_NOT_AUTHORIZED | error | product | The supplier code is not authorized to use the API. Use an authorized supplier code or contact the support to authorize the supplier code. |
| SUPPLIER_CODE_IS_UNKNOWN | error | product | The supplier code provided is not known. Please correct the supplier code and retransmit the affected product. In case a correction is not possible please contact the support. |
| UNKNOWN | error | product / variant | An unknown error has occurred. Please try again or contact the support if the error persists. |
