# Colossal.OdinSerializer.Utilities.PropertyInfoExtensions

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class PropertyInfoExtensions
{
    public static System.Reflection.PropertyInfo DeAliasProperty(System.Reflection.PropertyInfo propertyInfo, System.Boolean throwOnNotAliased);
    public static System.Boolean IsAliasProperty(System.Reflection.PropertyInfo propertyInfo);
    public static System.Boolean IsAutoProperty(System.Reflection.PropertyInfo propInfo, System.Boolean allowVirtual);
}
```


## Methods

- `public static DeAliasProperty(System.Reflection.PropertyInfo propertyInfo, System.Boolean throwOnNotAliased = False) : System.Reflection.PropertyInfo`  

```csharp
public static System.Reflection.PropertyInfo DeAliasProperty(System.Reflection.PropertyInfo propertyInfo, System.Boolean throwOnNotAliased);
```

- `public static IsAliasProperty(System.Reflection.PropertyInfo propertyInfo) : System.Boolean`  

```csharp
public static System.Boolean IsAliasProperty(System.Reflection.PropertyInfo propertyInfo);
```

- `public static IsAutoProperty(System.Reflection.PropertyInfo propInfo, System.Boolean allowVirtual = False) : System.Boolean`  

```csharp
public static System.Boolean IsAutoProperty(System.Reflection.PropertyInfo propInfo, System.Boolean allowVirtual);
```


