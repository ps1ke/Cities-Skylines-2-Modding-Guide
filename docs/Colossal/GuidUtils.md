# Colossal.GuidUtils

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Fields

- `public static readonly System.Guid kDnsNamespace`  
- `public static readonly System.Guid kUrlNamespace`  
- `public static readonly System.Guid kIsoOidNamespace`  
- `public static readonly System.Guid kAssemblyCache`  

## Methods

- `public static Create(System.Guid namespaceId, System.String name) : System.Guid`  
- `public static Create(System.Guid namespaceId, System.String name, System.Int32 version) : System.Guid`  
- `public static Create(System.Guid namespaceId, System.Byte[] nameBytes) : System.Guid`  
- `public static Create(System.Guid namespaceId, System.Byte[] nameBytes, System.Int32 version) : System.Guid`  
- `internal static SwapByteOrder(System.Byte[] guid) : System.Void`  
- `private static SwapBytes(System.Byte[] guid, System.Int32 left, System.Int32 right) : System.Void`  
- `public static ToLowerNoDashString(System.Guid guid) : System.String`  

