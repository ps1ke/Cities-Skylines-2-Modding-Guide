# Colossal.OdinSerializer.Utilities.MemberAliasPropertyInfo

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.Reflection.PropertyInfo`  
**Implements:** `System.Reflection.ICustomAttributeProvider`  

## Code

```csharp
public sealed class MemberAliasPropertyInfo : System.Reflection.PropertyInfo, System.Reflection.ICustomAttributeProvider
{
    private System.Reflection.PropertyInfo aliasedProperty;
    private System.String mangledName;
    private static const System.String FakeNameSeparatorString;

    public System.Reflection.PropertyInfo AliasedProperty { get; }
    public System.Reflection.Module Module { get; }
    public System.Int32 MetadataToken { get; }
    public System.String Name { get; }
    public System.Type DeclaringType { get; }
    public System.Type ReflectedType { get; }
    public System.Type PropertyType { get; }
    public System.Reflection.PropertyAttributes Attributes { get; }
    public System.Boolean CanRead { get; }
    public System.Boolean CanWrite { get; }

    public MemberAliasPropertyInfo(System.Reflection.PropertyInfo prop, System.String namePrefix);
    public MemberAliasPropertyInfo(System.Reflection.PropertyInfo prop, System.String namePrefix, System.String separatorString);

    public virtual System.Reflection.MethodInfo[] GetAccessors(System.Boolean nonPublic);
    public virtual System.Object[] GetCustomAttributes(System.Boolean inherit);
    public virtual System.Object[] GetCustomAttributes(System.Type attributeType, System.Boolean inherit);
    public virtual System.Reflection.MethodInfo GetGetMethod(System.Boolean nonPublic);
    public virtual System.Reflection.ParameterInfo[] GetIndexParameters();
    public virtual System.Reflection.MethodInfo GetSetMethod(System.Boolean nonPublic);
    public virtual System.Object GetValue(System.Object obj, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] index, System.Globalization.CultureInfo culture);
    public virtual System.Boolean IsDefined(System.Type attributeType, System.Boolean inherit);
    public virtual System.Void SetValue(System.Object obj, System.Object value, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] index, System.Globalization.CultureInfo culture);
}
```


## Fields

- `private System.Reflection.PropertyInfo aliasedProperty`  

```csharp
private System.Reflection.PropertyInfo aliasedProperty;
```

- `private System.String mangledName`  

```csharp
private System.String mangledName;
```

- `private static const System.String FakeNameSeparatorString`  

```csharp
private static const System.String FakeNameSeparatorString;
```


## Properties

- `public System.Reflection.PropertyInfo AliasedProperty { get }`  

```csharp
public System.Reflection.PropertyInfo AliasedProperty { get; }
```

- `public System.Reflection.Module Module { get }`  

```csharp
public System.Reflection.Module Module { get; }
```

- `public System.Int32 MetadataToken { get }`  

```csharp
public System.Int32 MetadataToken { get; }
```

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public System.Type DeclaringType { get }`  

```csharp
public System.Type DeclaringType { get; }
```

- `public System.Type ReflectedType { get }`  

```csharp
public System.Type ReflectedType { get; }
```

- `public System.Type PropertyType { get }`  

```csharp
public System.Type PropertyType { get; }
```

- `public System.Reflection.PropertyAttributes Attributes { get }`  

```csharp
public System.Reflection.PropertyAttributes Attributes { get; }
```

- `public System.Boolean CanRead { get }`  

```csharp
public System.Boolean CanRead { get; }
```

- `public System.Boolean CanWrite { get }`  

```csharp
public System.Boolean CanWrite { get; }
```


## Constructors

- `public MemberAliasPropertyInfo(System.Reflection.PropertyInfo prop, System.String namePrefix)`  

```csharp
public MemberAliasPropertyInfo(System.Reflection.PropertyInfo prop, System.String namePrefix);
```

- `public MemberAliasPropertyInfo(System.Reflection.PropertyInfo prop, System.String namePrefix, System.String separatorString)`  

```csharp
public MemberAliasPropertyInfo(System.Reflection.PropertyInfo prop, System.String namePrefix, System.String separatorString);
```


## Methods

- `public virtual GetAccessors(System.Boolean nonPublic) : System.Reflection.MethodInfo[]`  

```csharp
public virtual System.Reflection.MethodInfo[] GetAccessors(System.Boolean nonPublic);
```

- `public virtual GetCustomAttributes(System.Boolean inherit) : System.Object[]`  

```csharp
public virtual System.Object[] GetCustomAttributes(System.Boolean inherit);
```

- `public virtual GetCustomAttributes(System.Type attributeType, System.Boolean inherit) : System.Object[]`  

```csharp
public virtual System.Object[] GetCustomAttributes(System.Type attributeType, System.Boolean inherit);
```

- `public virtual GetGetMethod(System.Boolean nonPublic) : System.Reflection.MethodInfo`  

```csharp
public virtual System.Reflection.MethodInfo GetGetMethod(System.Boolean nonPublic);
```

- `public virtual GetIndexParameters() : System.Reflection.ParameterInfo[]`  

```csharp
public virtual System.Reflection.ParameterInfo[] GetIndexParameters();
```

- `public virtual GetSetMethod(System.Boolean nonPublic) : System.Reflection.MethodInfo`  

```csharp
public virtual System.Reflection.MethodInfo GetSetMethod(System.Boolean nonPublic);
```

- `public virtual GetValue(System.Object obj, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] index, System.Globalization.CultureInfo culture) : System.Object`  

```csharp
public virtual System.Object GetValue(System.Object obj, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] index, System.Globalization.CultureInfo culture);
```

- `public virtual IsDefined(System.Type attributeType, System.Boolean inherit) : System.Boolean`  

```csharp
public virtual System.Boolean IsDefined(System.Type attributeType, System.Boolean inherit);
```

- `public virtual SetValue(System.Object obj, System.Object value, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] index, System.Globalization.CultureInfo culture) : System.Void`  

```csharp
public virtual System.Void SetValue(System.Object obj, System.Object value, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] index, System.Globalization.CultureInfo culture);
```


