# Colossal.OdinSerializer.Utilities.MemberInfoExtensions

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class MemberInfoExtensions
{
    public static System.Reflection.MemberInfo DeAlias(System.Reflection.MemberInfo memberInfo, System.Boolean throwOnNotAliased);
    public static T GetAttribute<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit);
    public static T GetAttribute<T>(System.Reflection.ICustomAttributeProvider member);
    public static System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Reflection.ICustomAttributeProvider member);
    public static System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit);
    public static System.Attribute[] GetAttributes(System.Reflection.ICustomAttributeProvider member);
    public static System.Attribute[] GetAttributes(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit);
    public static System.String GetNiceName(System.Reflection.MemberInfo member);
    public static System.Boolean IsAlias(System.Reflection.MemberInfo memberInfo);
    public static System.Boolean IsDefined<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit);
    public static System.Boolean IsDefined<T>(System.Reflection.ICustomAttributeProvider member);
    public static System.Boolean IsStatic(System.Reflection.MemberInfo member);
}
```


## Methods

- `public static DeAlias(System.Reflection.MemberInfo memberInfo, System.Boolean throwOnNotAliased = False) : System.Reflection.MemberInfo`  

```csharp
public static System.Reflection.MemberInfo DeAlias(System.Reflection.MemberInfo memberInfo, System.Boolean throwOnNotAliased);
```

- `public static GetAttribute<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit) : T`  

```csharp
public static T GetAttribute<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit);
```

- `public static GetAttribute<T>(System.Reflection.ICustomAttributeProvider member) : T`  

```csharp
public static T GetAttribute<T>(System.Reflection.ICustomAttributeProvider member);
```

- `public static GetAttributes<T>(System.Reflection.ICustomAttributeProvider member) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Reflection.ICustomAttributeProvider member);
```

- `public static GetAttributes<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> GetAttributes<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit);
```

- `public static GetAttributes(System.Reflection.ICustomAttributeProvider member) : System.Attribute[]`  

```csharp
public static System.Attribute[] GetAttributes(System.Reflection.ICustomAttributeProvider member);
```

- `public static GetAttributes(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit) : System.Attribute[]`  

```csharp
public static System.Attribute[] GetAttributes(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit);
```

- `public static GetNiceName(System.Reflection.MemberInfo member) : System.String`  

```csharp
public static System.String GetNiceName(System.Reflection.MemberInfo member);
```

- `public static IsAlias(System.Reflection.MemberInfo memberInfo) : System.Boolean`  

```csharp
public static System.Boolean IsAlias(System.Reflection.MemberInfo memberInfo);
```

- `public static IsDefined<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit) : System.Boolean`  

```csharp
public static System.Boolean IsDefined<T>(System.Reflection.ICustomAttributeProvider member, System.Boolean inherit);
```

- `public static IsDefined<T>(System.Reflection.ICustomAttributeProvider member) : System.Boolean`  

```csharp
public static System.Boolean IsDefined<T>(System.Reflection.ICustomAttributeProvider member);
```

- `public static IsStatic(System.Reflection.MemberInfo member) : System.Boolean`  

```csharp
public static System.Boolean IsStatic(System.Reflection.MemberInfo member);
```


