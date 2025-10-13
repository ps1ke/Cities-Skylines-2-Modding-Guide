# Colossal.OdinSerializer.Utilities.MemberAliasMethodInfo

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.Reflection.MethodInfo`  
**Implements:** `System.Reflection.ICustomAttributeProvider`  

## Code

```csharp
public sealed class MemberAliasMethodInfo : System.Reflection.MethodInfo, System.Reflection.ICustomAttributeProvider
{
    private System.Reflection.MethodInfo aliasedMethod;
    private System.String mangledName;
    private static const System.String FAKE_NAME_SEPARATOR_STRING;

    public System.Reflection.MethodInfo AliasedMethod { get; }
    public System.Reflection.ICustomAttributeProvider ReturnTypeCustomAttributes { get; }
    public System.RuntimeMethodHandle MethodHandle { get; }
    public System.Reflection.MethodAttributes Attributes { get; }
    public System.Type ReturnType { get; }
    public System.Type DeclaringType { get; }
    public System.String Name { get; }
    public System.Type ReflectedType { get; }

    public MemberAliasMethodInfo(System.Reflection.MethodInfo method, System.String namePrefix);
    public MemberAliasMethodInfo(System.Reflection.MethodInfo method, System.String namePrefix, System.String separatorString);

    public virtual System.Reflection.MethodInfo GetBaseDefinition();
    public virtual System.Object[] GetCustomAttributes(System.Boolean inherit);
    public virtual System.Object[] GetCustomAttributes(System.Type attributeType, System.Boolean inherit);
    public virtual System.Reflection.MethodImplAttributes GetMethodImplementationFlags();
    public virtual System.Reflection.ParameterInfo[] GetParameters();
    public virtual System.Object Invoke(System.Object obj, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] parameters, System.Globalization.CultureInfo culture);
    public virtual System.Boolean IsDefined(System.Type attributeType, System.Boolean inherit);
}
```


## Fields

- `private System.Reflection.MethodInfo aliasedMethod`  

```csharp
private System.Reflection.MethodInfo aliasedMethod;
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

- `public System.Reflection.MethodInfo AliasedMethod { get }`  

```csharp
public System.Reflection.MethodInfo AliasedMethod { get; }
```

- `public System.Reflection.ICustomAttributeProvider ReturnTypeCustomAttributes { get }`  

```csharp
public System.Reflection.ICustomAttributeProvider ReturnTypeCustomAttributes { get; }
```

- `public System.RuntimeMethodHandle MethodHandle { get }`  

```csharp
public System.RuntimeMethodHandle MethodHandle { get; }
```

- `public System.Reflection.MethodAttributes Attributes { get }`  

```csharp
public System.Reflection.MethodAttributes Attributes { get; }
```

- `public System.Type ReturnType { get }`  

```csharp
public System.Type ReturnType { get; }
```

- `public System.Type DeclaringType { get }`  

```csharp
public System.Type DeclaringType { get; }
```

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public System.Type ReflectedType { get }`  

```csharp
public System.Type ReflectedType { get; }
```


## Constructors

- `public MemberAliasMethodInfo(System.Reflection.MethodInfo method, System.String namePrefix)`  

```csharp
public MemberAliasMethodInfo(System.Reflection.MethodInfo method, System.String namePrefix);
```

- `public MemberAliasMethodInfo(System.Reflection.MethodInfo method, System.String namePrefix, System.String separatorString)`  

```csharp
public MemberAliasMethodInfo(System.Reflection.MethodInfo method, System.String namePrefix, System.String separatorString);
```


## Methods

- `public virtual GetBaseDefinition() : System.Reflection.MethodInfo`  

```csharp
public virtual System.Reflection.MethodInfo GetBaseDefinition();
```

- `public virtual GetCustomAttributes(System.Boolean inherit) : System.Object[]`  

```csharp
public virtual System.Object[] GetCustomAttributes(System.Boolean inherit);
```

- `public virtual GetCustomAttributes(System.Type attributeType, System.Boolean inherit) : System.Object[]`  

```csharp
public virtual System.Object[] GetCustomAttributes(System.Type attributeType, System.Boolean inherit);
```

- `public virtual GetMethodImplementationFlags() : System.Reflection.MethodImplAttributes`  

```csharp
public virtual System.Reflection.MethodImplAttributes GetMethodImplementationFlags();
```

- `public virtual GetParameters() : System.Reflection.ParameterInfo[]`  

```csharp
public virtual System.Reflection.ParameterInfo[] GetParameters();
```

- `public virtual Invoke(System.Object obj, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] parameters, System.Globalization.CultureInfo culture) : System.Object`  

```csharp
public virtual System.Object Invoke(System.Object obj, System.Reflection.BindingFlags invokeAttr, System.Reflection.Binder binder, System.Object[] parameters, System.Globalization.CultureInfo culture);
```

- `public virtual IsDefined(System.Type attributeType, System.Boolean inherit) : System.Boolean`  

```csharp
public virtual System.Boolean IsDefined(System.Type attributeType, System.Boolean inherit);
```


