# Custom complex data types

Creation of custom data types.

::: info
**Note:** For Bonita Enterprise, Performance, Efficiency, and Teamwork editions only.
:::

If the standard data types are not suitable for a variable in your process, you can create a new custom complex data type. It could be useful for example to reference data from an external database.

::: warning
**Deprecated:** 
Because they are serialized in the database, because they do not allow the use of Bonita API, because they may not work if the Bonita platform Java version is updated, complex data types are now deprecated.
When the feature is removed from Bonita (in a few versions), data types will still work, but their creation will not be possible in Bonita Studio anymore.
Instead of data types, you can create a [Business Object](define-and-deploy-the-bdm.md). Its data will be stored in a structured way.
You can also add a POJO (using a custom Groovy script or importing a .jar). This POJO must implement _java.io.Serializable_.
:::

A complex data type is a collection of attributes, each attribute having a data type. Complex data types are defined in a JAR or XSD file. Each file can contain more than one definition. To add a new complex data type, create a new JAR or XSD file.

If you are using the Enterprise, Performance, Efficiency, or Teamwork edition, you can also use Bonita Studio to add a new data type:

1. From the **Development** menu, choose **Data types**, then choose **New data type...**. In the dialog box that opens, you can define a set of data types.
2. At the top of the dialog box, specify a name for the set of data types.
3. For each type, specify a name, and the set of attributes. Each attribute has a name, a type, and can be either single or multiple.
4. When you have defined all the data types required, click **_OK_**.
5. Click **_Create as JAR_** or **_Create as XSD_**, then click **_Finish_**.

When the new data type has been defined, as a JAR or XSD definition, it can be used to [define a variable](specify-data-in-a-process-definition.md).

Warning: Java data types (defined in a JAR file) use the STAX API. Stax libraries cannot be loaded in more than one classloader but must instead be placed in a single location where they can be called by all the items that use them. When you configure a process that uses Java data types, you must [manage the jar files](manage-jar-files.md).
