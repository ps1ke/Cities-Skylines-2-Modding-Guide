# Colossal.PSI.Common.HashHelper

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class HashHelper
{
    public static Colossal.Hash128 ComputeHash(System.String path, System.String ignoreExtension);
    public static System.String DecryptFile(Colossal.Hash128 key, System.Byte[] encryptedData);
    public static System.Byte[] EncryptFile(System.String filePath, Colossal.Hash128 key);
    public static System.Void Update(Unity.Collections.xxHash3+StreamingState generator, System.String str);
}
```


## Methods

- `public static ComputeHash(System.String path, System.String ignoreExtension) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 ComputeHash(System.String path, System.String ignoreExtension);
```

- `public static DecryptFile(Colossal.Hash128 key, System.Byte[] encryptedData) : System.String`  

```csharp
public static System.String DecryptFile(Colossal.Hash128 key, System.Byte[] encryptedData);
```

- `public static EncryptFile(System.String filePath, Colossal.Hash128 key) : System.Byte[]`  

```csharp
public static System.Byte[] EncryptFile(System.String filePath, Colossal.Hash128 key);
```

- `public static Update(Unity.Collections.xxHash3+StreamingState generator, System.String str) : System.Void`  

```csharp
public static System.Void Update(Unity.Collections.xxHash3+StreamingState generator, System.String str);
```


## Nested types

- `Colossal.PSI.Common.HashHelper+<>c`  

