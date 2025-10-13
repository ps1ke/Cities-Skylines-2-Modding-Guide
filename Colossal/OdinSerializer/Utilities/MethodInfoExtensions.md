# Colossal.OdinSerializer.Utilities.MethodInfoExtensions

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class MethodInfoExtensions
{
    public static System.Reflection.MethodInfo DeAliasMethod(System.Reflection.MethodInfo methodInfo, System.Boolean throwOnNotAliased);
    public static System.String GetFullName(System.Reflection.MethodBase method, System.String extensionMethodPrefix);
    public static System.String GetFullName(System.Reflection.MethodBase method);
    public static System.String GetParamsNames(System.Reflection.MethodBase method);
    public static System.Boolean IsAliasMethod(System.Reflection.MethodInfo methodInfo);
    public static System.Boolean IsExtensionMethod(System.Reflection.MethodBase method);
}
```


## Methods

- `public static DeAliasMethod(System.Reflection.MethodInfo methodInfo, System.Boolean throwOnNotAliased = False) : System.Reflection.MethodInfo`  

```csharp
public static System.Reflection.MethodInfo DeAliasMethod(System.Reflection.MethodInfo methodInfo, System.Boolean throwOnNotAliased);
```

- `public static GetFullName(System.Reflection.MethodBase method, System.String extensionMethodPrefix) : System.String`  

```csharp
public static System.String GetFullName(System.Reflection.MethodBase method, System.String extensionMethodPrefix);
```

- `public static GetFullName(System.Reflection.MethodBase method) : System.String`  

```csharp
public static System.String GetFullName(System.Reflection.MethodBase method);
```

- `public static GetParamsNames(System.Reflection.MethodBase method) : System.String`  

```csharp
public static System.String GetParamsNames(System.Reflection.MethodBase method);
```

- `public static IsAliasMethod(System.Reflection.MethodInfo methodInfo) : System.Boolean`  

```csharp
public static System.Boolean IsAliasMethod(System.Reflection.MethodInfo methodInfo);
```

- `public static IsExtensionMethod(System.Reflection.MethodBase method) : System.Boolean`  

```csharp
public static System.Boolean IsExtensionMethod(System.Reflection.MethodBase method);
```


