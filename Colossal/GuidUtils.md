# Colossal.GuidUtils

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class GuidUtils
{
    public static readonly System.Guid kDnsNamespace;
    public static readonly System.Guid kUrlNamespace;
    public static readonly System.Guid kIsoOidNamespace;
    public static readonly System.Guid kAssemblyCache;

    public static System.Guid Create(System.Guid namespaceId, System.String name);
    public static System.Guid Create(System.Guid namespaceId, System.String name, System.Int32 version);
    public static System.Guid Create(System.Guid namespaceId, System.Byte[] nameBytes);
    public static System.Guid Create(System.Guid namespaceId, System.Byte[] nameBytes, System.Int32 version);
    internal static System.Void SwapByteOrder(System.Byte[] guid);
    private static System.Void SwapBytes(System.Byte[] guid, System.Int32 left, System.Int32 right);
    public static System.String ToLowerNoDashString(System.Guid guid);
}
```


## Fields

- `public static readonly System.Guid kDnsNamespace`  

```csharp
public static readonly System.Guid kDnsNamespace;
```

- `public static readonly System.Guid kUrlNamespace`  

```csharp
public static readonly System.Guid kUrlNamespace;
```

- `public static readonly System.Guid kIsoOidNamespace`  

```csharp
public static readonly System.Guid kIsoOidNamespace;
```

- `public static readonly System.Guid kAssemblyCache`  

```csharp
public static readonly System.Guid kAssemblyCache;
```


## Methods

- `public static Create(System.Guid namespaceId, System.String name) : System.Guid`  

```csharp
public static System.Guid Create(System.Guid namespaceId, System.String name);
```

- `public static Create(System.Guid namespaceId, System.String name, System.Int32 version) : System.Guid`  

```csharp
public static System.Guid Create(System.Guid namespaceId, System.String name, System.Int32 version);
```

- `public static Create(System.Guid namespaceId, System.Byte[] nameBytes) : System.Guid`  

```csharp
public static System.Guid Create(System.Guid namespaceId, System.Byte[] nameBytes);
```

- `public static Create(System.Guid namespaceId, System.Byte[] nameBytes, System.Int32 version) : System.Guid`  

```csharp
public static System.Guid Create(System.Guid namespaceId, System.Byte[] nameBytes, System.Int32 version);
```

- `internal static SwapByteOrder(System.Byte[] guid) : System.Void`  

```csharp
internal static System.Void SwapByteOrder(System.Byte[] guid);
```

- `private static SwapBytes(System.Byte[] guid, System.Int32 left, System.Int32 right) : System.Void`  

```csharp
private static System.Void SwapBytes(System.Byte[] guid, System.Int32 left, System.Int32 right);
```

- `public static ToLowerNoDashString(System.Guid guid) : System.String`  

```csharp
public static System.String ToLowerNoDashString(System.Guid guid);
```


