# JavaFxPropertyHelper NetBeans Plugin

This NetBeans plugin will help to generate get/set methods for JavaFx properties 
that are contained within a POJO.

The standard get/set code generator creates the following get/set methods for a 
JavaFx property which is not ideal:

```java
private StringProperty name;

public StringProperty getName() { 
    return name;
}
public void setName( StringProperty name ) {
    this.name = name;
}
```

This plugin would create the following methods:

```java
public final String getName() {
    return name.get();
}

public final void setName( String value ) {
    name.set(value);
}

public final StringProperty nameProperty() {
    return name;
}
```

It's also possible to use variables with the suffix `Property` in their names 
which will create the following methods: 

```java
private StringProperty nameProperty;
public final String getName() {
    return nameProperty.get();
}

public final void setName( String value ) {
    nameProperty.set(value);
}

public final StringProperty nameProperty() {
    return nameProperty;
}
```



# Usage

Press Alt-Insert to get the "Generate" popup menu, and select "Java FX Getter and Setter..."
![alt tag](https://rterp.files.wordpress.com/2015/11/nb-plugin-11.png)


Methods for supported property types will automatically be generated.
![alt tag](https://rterp.files.wordpress.com/2015/11/nb-plugin-2.png)



### Supported Property Types
* StringProperty
* BooleanProperty
* DoubleProperty
* FloatProperty
* IntegerProperty
* LongProperty



### Unsupported Property Types
* ListProperty
* MapProperty
* ObjectProperty
* SetProperty

