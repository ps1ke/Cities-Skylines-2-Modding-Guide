# PDX.SDK.Internal.Util.CryptUtils

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Util`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CryptUtils
{
    private static System.Collections.Generic.Dictionary<PDX.SDK.Internal.Enums.HashingAlgorithm, System.Func<System.Security.Cryptography.HashAlgorithm>> algoritmToHasherFunction;

    private static System.Void EncodeString(System.String toEncode, PDX.SDK.Internal.Enums.StringEncoding encoding, System.Byte[]& data);
    public static System.String HashString(System.String toHash, PDX.SDK.Internal.Enums.HashingAlgorithm algorithm, PDX.SDK.Internal.Enums.StringEncoding encoding);
    private static System.String HashToReadableHexString(System.Byte[] hash);
}
```


## Fields

- `private static System.Collections.Generic.Dictionary<PDX.SDK.Internal.Enums.HashingAlgorithm, System.Func<System.Security.Cryptography.HashAlgorithm>> algoritmToHasherFunction`  

```csharp
private static System.Collections.Generic.Dictionary<PDX.SDK.Internal.Enums.HashingAlgorithm, System.Func<System.Security.Cryptography.HashAlgorithm>> algoritmToHasherFunction;
```


## Methods

- `private static EncodeString(System.String toEncode, PDX.SDK.Internal.Enums.StringEncoding encoding, System.Byte[]& data) : System.Void`  

```csharp
private static System.Void EncodeString(System.String toEncode, PDX.SDK.Internal.Enums.StringEncoding encoding, System.Byte[]& data);
```

- `public static HashString(System.String toHash, PDX.SDK.Internal.Enums.HashingAlgorithm algorithm = SHA256, PDX.SDK.Internal.Enums.StringEncoding encoding = UTF8) : System.String`  

```csharp
public static System.String HashString(System.String toHash, PDX.SDK.Internal.Enums.HashingAlgorithm algorithm, PDX.SDK.Internal.Enums.StringEncoding encoding);
```

- `private static HashToReadableHexString(System.Byte[] hash) : System.String`  

```csharp
private static System.String HashToReadableHexString(System.Byte[] hash);
```


## Nested types

- `PDX.SDK.Internal.Util.CryptUtils+<>c`  

