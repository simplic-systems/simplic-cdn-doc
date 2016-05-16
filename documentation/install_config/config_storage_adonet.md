


## Write own Simplic CDN ADO.Net Provider

It is possible to write a custom ado.net provider. All providers are located in
the directory `ADO.Net Provider` in the main application folder.

All providers are configurated in a `Configuration.xml` in the directory.

> Hint: Try to copy a working provider and edit what is required for your custom provider.

All ADO.Net Provider must have the followint structure. All strings inside of braces are templates
which will be replaced automatically. The `Assembly`-Tag must point the assembly, which implements
the ADO.Net Provider. The assembly has to be placed inside of the provider configuration directory
and will be loaded automatically.

```xml
<ADONetDriverConfiguration>
	<Assembly Name="Sap.Data.SQLAnywhere.v4.5.dll" />
  <Statements>
    <!-- 
    Statement for checking whether a blob exists or not.
    Should just return the IdColumn and only takes the
    Id-Column as a parameter
    -->
    <Exists>
      <![CDATA[
				SELECT {IdColumn} FROM {TableName} WHERE {IdColumn} = ?
			]]>
    </Exists>
    <!--
    Return the amount of data in the data-table.
    -->
    <HasObjects>
      <![CDATA[
				SELECT Count(*) FROM {TableName}
			]]>
    </HasObjects>
    <!--
    Statement for inserting data into the DB-Table. The first parameter
    must be the id/path and the second the blob/data.
    -->
    <Insert>
      <![CDATA[
				INSERT INTO {TableName} ({IdColumn}, {DataColumn}) ON EXISTING UPDATE VALUES (?, ?)
			]]>
    </Insert>
    <!--
    Statement for querying data from the data table
    by passing the Id-Column as a parameter. The first column
    has to return the blob/data.
    -->
    <Select>
      <![CDATA[
				SELECT {DataColumn} FROM {TableName} WHERE {IdColumn} = ?
			]]>
    </Select>
    <!--
    Statement for deleting data from the DB-Table by passing
    the ID-Column as a parameter
    -->
    <Delete>
      <![CDATA[
				DELETE FROM {TableName} WHERE {IdColumn} = ?
			]]>
    </Delete>
    <SelectAllIds>
      <![CDATA[
				SELECT {IdColumn} FROM {TableName}
			]]>
    </SelectAllIds>
    <SelectAll>
      <![CDATA[
				SELECT {IdColumn}, {DataColumn} FROM {TableName}
			]]>
    </SelectAll>
  </Statements>	
</ADONetDriverConfiguration>
```