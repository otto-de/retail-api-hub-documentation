
# Media assets

You can send one or multiple multi media assets using the API. For each multi media asset you need to specify the URL of the media asset together with its type in the mediaAssets container.

Depending on the media asset type, different limitations will apply for the media assets. The following table gives you an overview of the different types together with their limitations for the media asset:

| type | description | minimum length of the shorter side [pixel] | minimum length of the longer side [pixel] | maximal image size [Byte] | allowed file types | color space
| ---- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| ASSEMBLY_INSTRUCTIONS | |-|- | 26214400 | PDF | - |
| COLOR VARIANT | | 34 | 34 | 10485760 | GIF, JPG/JPEG, PNG | RGB |
| DIMENSIONAL_DRAWING | | 480 | 960 | 26214400 | GIF, JPG/JPEG, PNG, TIFF | RGB |
| ENERGY_EFFICIENCY_LABEL | | 425 | 850 | 26214400 | GIF, JPG/JPEG, PNG, TIFF | RGB |
| IMAGE | | 480 | 960 | 26214400 | GIF, JPG/JPEG, PNG, TIFF | RGB |
| MANUFACTURER_WARRANTY | | - | - | 26214400 | PDF| - |
| MATERIAL_SAMPLE | | 480 | 480 | 26214400 | GIF, JPG/JPEG, PNG | RGB |
| PRODUCT_DATASHEET | |-|- | 26214400 | PDF | - |
| SAFETY_DATASHEET | |-|- | 26214400 | PDF | - |
| USER_MANUAL | |-|- | 26214400 | PDF | - |
| WARNING_LABEL | |-|- | 26214400 | PDF | - |
