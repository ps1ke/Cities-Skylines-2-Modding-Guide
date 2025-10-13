# Colossal.OdinSerializer.Utilities.MemberAliasFieldInfo

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.Reflection.FieldInfo`  
**Implements:** `System.Reflection.ICustomAttributeProvider`  

## Code

```csharp
public sealed class MemberAliasFieldInfo : System.Reflection.FieldInfo, System.Reflection.ICustomAttributeProvider
{
    private System.Reflection.FieldInfo aliasedField;
    private System.String mangledName;
    private static const System.String FAKE_NAME_SEPARATOR_STRING;

    public System.Reflection.FieldInfo AliasedField { get; }
    public System.Reflection.Module Module { get; }
    public System.Int32 MetadataToken { get; }
    public System.String Name { get; }
    public System.Type DeclaringType { get; }
    public System.Type ReflectedType { get; }
    public System.Type FieldType { get; }
    public System.RuntimeFieldHandle FieldHandle { get; }
    public System.Reflection.FieldAttributes Attributes { get; }

    public MemberAliasFieldInfo(System.Reflection.FieldInfo field, System.String namePrefix);
    public MemberAliasFieldInfo(System.Reflection.FieldInfo field, System.String namePrefix, System.String separatorString);

    public virtual System.Object[] GetCustomAttributes(System.Boolean inherit);
    public virtual System.Object[] GetCustomAttributes(System.Type attributeType, System.Boolean inherit);
    public virtual System.Object GetValue(System.Object obj);
    public virtual System.Boolean IsDefined(System.Type attributeType, System.Boolean inherit);
    public virtual System.Void SetValue(System.Object obj, System.Object value, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Globalization.CultureInfo culture);
}
```


## Fields

- `private System.Reflection.FieldInfo aliasedField`  

```csharp
private System.Reflection.FieldInfo aliasedField;
```

- `private System.String mangledName`  

```csharp
private System.String mangledName;
```

- `private static const System.String FAKE_NAME_SEPARATOR_STRING`  

```csharp
private static const System.String FAKE_NAME_SEPARATOR_STRING;
```


## Properties

- `public System.Reflection.FieldInfo AliasedField { get }`  

```csharp
public System.Reflection.FieldInfo AliasedField { get; }
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

- `public System.Type FieldType { get }`  

```csharp
public System.Type FieldType { get; }
```

- `public System.RuntimeFieldHandle FieldHandle { get }`  

```csharp
public System.RuntimeFieldHandle FieldHandle { get; }
```

- `public System.Reflection.FieldAttributes Attributes { get }`  

```csharp
public System.Reflection.FieldAttributes Attributes { get; }
```


## Constructors

- `public MemberAliasFieldInfo(System.Reflection.FieldInfo field, System.String namePrefix)`  

```csharp
public MemberAliasFieldInfo(System.Reflection.FieldInfo field, System.String namePrefix);
```

- `public MemberAliasFieldInfo(System.Reflection.FieldInfo field, System.String namePrefix, System.String separatorString)`  

```csharp
public MemberAliasFieldInfo(System.Reflection.FieldInfo field, System.String namePrefix, System.String separatorString);
```


## Methods

- `public virtual GetCustomAttributes(System.Boolean inherit) : System.Object[]`  

```csharp
public virtual System.Object[] GetCustomAttributes(System.Boolean inherit);
```

- `public virtual GetCustomAttributes(System.Type attributeType, System.Boolean inherit) : System.Object[]`  

```csharp
public virtual System.Object[] GetCustomAttributes(System.Type attributeType, System.Boolean inherit);
```

- `public virtual GetValue(System.Object obj) : System.Object`  

```csharp
public virtual System.Object GetValue(System.Object obj);
```

- `public virtual IsDefined(System.Type attributeType, System.Boolean inherit) : System.Boolean`  

```csharp
public virtual System.Boolean IsDefined(System.Type attributeType, System.Boolean inherit);
```

- `public virtual SetValue(System.Object obj, System.Object value, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Globalization.CultureInfo culture) : System.Void`  

```csharp
public virtual System.Void SetValue(System.Object obj, System.Object value, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Globalization.CultureInfo culture);
```


