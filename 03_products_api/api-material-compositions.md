# Material composition

The material composition is specified in the material composition field "Materialzusammensetzung".

The base for the material composition is the currently valid Textile conventions of the EU. The material composition must be transferred in the following format (please note the structure, blank and separator characters):

![Material composition!](material-composition.gif "Material composition structure")

The list of valid material names can be found [here](material-names.md).

The list of valid material component names can be found [here](material-component-names.md).

Specifically, the following guidelines and syntax rules, among others, apply to the specification of the material composition:

| Rule | Definition  | Examples |-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| **Material proportion** | You must specify for each material the percentage proportion as an integer by specifying the corresponding percentage value directly followed by a percent sign ("%"). | ![OK!](ok.gif "(OK)") 70% Baumwolle, 30% Viskose |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") Baumwolle, Viskose |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 70 Baumwolle, 30  Viskose |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 70 %Baumwolle, 30 % Viskose |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 70,2345% Baumwolle, 30 % Viskose |
| **Material name** | For the (base) material names, one of the valid names from the (base) material name list must be used. The list can be found [here](material-names.md). |![OK!](ok.gif "(OK)") 70% Baumwolle, 30% Viskose                 |
| | Abbreviations, codes and alternative spellings are not permitted. | ![NOT OK!](not-ok.gif "(NOT OK)") 70% Baumwollstoff, 30% Visk. |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 70% CO, 30% VISKOSE | 
| **Brand fibers** | Brand fibers can be appended to the corresponding (base-) material name in parentheses separated by a space. Only the permitted names/brand names combinations of names may be used. (see the list of valid material names [here](material-names.md)). | ![OK!](ok.gif "(OK)") 100% Viskose (LenzingⓇ) |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 100% Viskose Lenzing  Ⓡ |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 100% Viskose aus LenzingⓇ | 
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 100% Viskose-LenzingⓇ | 
| **Comma separated material list** | If more than one material exists, all materials must be specified separately by a comma (","). | ![OK!](ok.gif "(OK)") 70% Baumwolle, 30% Viskose |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 70% Baumwolle 30% Viskose |  
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 70% Baumwolle; 30% Viskose | 
| **Complete material specification**| The sum of all materials for a material component must be 100%. | ![OK!](ok.gif "(OK)") 70% Baumwolle, 30% Viskose | 
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 70% Baumwolle, 20% Viskose | 
| **Other fibers** | If not all materials are specified, a maximum of 15% "sonstige Fasern" (other fibers) may be specified as material. | ![OK!](ok.gif "(OK)") 60% Hanf, 30% Viskose, 10% sonstige Fasern |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 80% Hanf, 20% sonstige Fasern | 
|**Material component names** | If more than one material component is specified, each material component must be given a material component name. | ![OK!](ok.gif "(OK)") Obermaterial: 60% Hanf, 40% Viskose; Futter: 100% Baumwolle |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 60% Hanf, 40% Viskose; 100% Baumwolle |  
| | | ![NOT OK!](not-ok.gif "(NOT OK)") Obermaterial: 60% Hanf, 40% Viskose; 100% Baumwolle |
| | If only one material component is specified, the material component name can be omitted. | ![OK!](ok.gif "(OK)") 60% Hanf, 40% Viskose | 
| | | ![OK!](ok.gif "(OK)") Obermaterial: 60% Hanf, 40% Viskose |
| | The material component name is specified before the respective material list and is terminated by a colon (":") and a space. | ![OK!](ok.gif "(OK)")Obermaterial: 60% Hanf, 40% Viskose |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") Obermaterial 60% Hanf, 40% Viskose |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") Obermaterial - 60% Hanf, 40% Viskose |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") 60% Hanf, 40% Viskose (Obermaterial) |
| | Only names from the list of valid material component names may be used. | ![NOT OK!](not-ok.gif "(NOT OK)") Obermaterialstoff: 60% Hanf, 40% Viskose |
| **Products with more than one material component** | If more than one material component exists, all material components must be specified. <br> <br> The material components must be listed separated by a semicolon (";") and spaces. The final semicolon can be omitted for the last material component.  | ![OK!](ok.gif "(OK)") Obermaterial: 60% Baumwolle, 40% Viskose; Futter: 100% Baumwolle |
| | | ![NOT OK!](not-ok.gif "(NOT OK)") Obermaterial: 60% Baumwolle, 40% Viskose; 100% Baumwolle | 
| | | ![NOT OK!](not-ok.gif "(NOT OK)") Obermaterial: 60% Baumwolle, 40% Viskose; Futter: 100% Baumwolle  |                                                                                                         
| | Each material component must have a unique material component name, duplications are not allowed. | ![NOT OK!](not-ok.gif "(NOT OK)") Obermaterial: 60% Baumwolle, 40% Viskose; Obermaterial: 100% Baumwolle|

If you are missing entries in the tables of valid (base) material names, brand fibers and material component names, please contact us via the ticket system of the Otto Supplier Connect (OSC) portal.