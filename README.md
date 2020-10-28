# Magento2 Module Select2 Ui Component
 
Select2 UI Component for Magento 2

## Documentation

https://select2.github.io
  
## Usage

You can control the select2 options with the xml in the select2 tags

Example Options
 ```xml
<item name="select2" xsi:type="array">
     <item name="maximumSelectionLength" xsi:type="string">3</item>
     <item name="tags" xsi:type="string">true</item>
     <item name="allowClear" xsi:type="string"">true</item>
</item>
 ```

Multiselect 
 
 ```xml
 <?xml version="1.0" encoding="UTF-8"?>
 <form xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:module:Magento_Ui:etc/ui_configuration.xsd">
     <fieldset name="FIELDSET_NAME">
         <field name="CUSTOM_FIELD">
             <argument name="data" xsi:type="array">
                <item name="options" xsi:type="object">Magento\Customer\Model\Customer\Attribute\Source\Group</item>
                <item name="config" xsi:type="array">
                    <item name="dataType" xsi:type="string">text</item>
                    <item name="label" translate="true" xsi:type="string">Customer Group</item>
                    <item name="formElement" xsi:type="string">multiselect</item>
                    <item name="source" xsi:type="string">Group</item>
                    <item name="sortOrder" xsi:type="number">40</item>
                    <item name="dataScope" xsi:type="string">group_id</item>
                    <item name="validation" xsi:type="array">
                        <item name="required-entry" xsi:type="boolean">true</item>
                    </item>
                    <item name="elementTmpl" xsi:type="string">Experius_FormSelect2/form/element/multiselect2</item>
                    <item name="component" xsi:type="string">Experius_FormSelect2/js/form/element/multiselect2</item>
                    <item name="select2" xsi:type="array">
                        <item name="tags" xsi:type="string">true</item>
                    </item>
                </item>
            </argument>
         </field>
     </fieldset>
 </form>
 ```
 
Select 
  
  ```xml
  <?xml version="1.0" encoding="UTF-8"?>
  <form xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:module:Magento_Ui:etc/ui_configuration.xsd">
      <fieldset name="FIELDSET_NAME">
          <field name="CUSTOM_FIELD">
              <argument name="data" xsi:type="array">
                 <item name="options" xsi:type="object">Magento\Customer\Model\Customer\Attribute\Source\Group</item>
                 <item name="config" xsi:type="array">
                     <item name="dataType" xsi:type="string">text</item>
                     <item name="label" translate="true" xsi:type="string">Customer Group</item>
                     <item name="formElement" xsi:type="string">select</item>
                     <item name="source" xsi:type="string">Group</item>
                     <item name="sortOrder" xsi:type="number">40</item>
                     <item name="dataScope" xsi:type="string">group_id</item>
                     <item name="validation" xsi:type="array">
                         <item name="required-entry" xsi:type="boolean">true</item>
                     </item>
                     <item name="elementTmpl" xsi:type="string">Experius_FormSelect2/form/element/select2</item>
                     <item name="component" xsi:type="string">Experius_FormSelect2/js/form/element/select2</item>
                     <item name="select2" xsi:type="array">
                         <item name="maximumSelectionLength" xsi:type="string">1</item>
                         <item name="tags" xsi:type="string">true</item>
                     </item>
                 </item>
             </argument>
          </field>
      </fieldset>
  </form>
  ```

Ajax Search Select 

```xml
<item name="select2" xsi:type="array">
    <item name="maximumSelectionLength" xsi:type="string">1</item>
    <item name="tags" xsi:type="string">true</item>
    <item name="ajax" xsi:type="array">
        <item name="url" xsi:type="string">/admin/formselect2/ajax/search</item>
        <item name="search" xsi:type="string">ProductSearch</item> <!-- Uses virtual model productsearch -->
    </item>
</item>
```
  
Ajax Virtual Search Model Example (di.xml)

```xml
  <virtualType name="Experius\FormSelect2\Model\Virtual\ProductSearch" type="Experius\FormSelect2\Model\Search">
         <arguments>
             <argument name="searchData" xsi:type="array">
                 <item name="modelCollectionClass" xsi:type="string">Magento\Catalog\Model\ResourceModel\Product\Collection</item>
                 <item name="modelClass" xsi:type="string">Magento\Catalog\Model\Product</item>
                 <item name="searchFields" xsi:type="array">
                     <item name="sku" xsi:type="string">sku</item>
                     <item name="name" xsi:type="string">name</item>
                 </item>
                 <item name="modelType" xsi:type="string">eav</item>
                 <item name="modelKey" xsi:type="string">entity_id</item>
                 <item name="sortByAttribute" xsi:type="string">name</item>
             </argument>
         </arguments>
     </virtualType>
```
  
  
## Credits
Inspired by https://github.com/weprovide/magento2-module-select2-uicomponent  
Jquery select2 lib by https://select2.github.io/