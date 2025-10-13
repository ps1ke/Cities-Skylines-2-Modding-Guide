# PDX.SDK.Internal.Platypatch.Pgp.Packets.PublicKeyPacket

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp.Packets`  

**Type:** class public  

**Base:** `PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet`  

## Code

```csharp
public class PublicKeyPacket : PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet
{
    private System.Int32 <Version>k__BackingField;
    private System.DateTime <TimeCreated>k__BackingField;
    private PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm <EncryptionAlgorithm>k__BackingField;
    private System.Security.Cryptography.RSAParameters <RsaParameters>k__BackingField;
    private readonly System.Boolean <IsSubKey>k__BackingField;
    private System.String <KeyId>k__BackingField;
    private System.String <Fingerprint>k__BackingField;

    public System.Int32 Version { get; private set; }
    public System.DateTime TimeCreated { get; private set; }
    public PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm EncryptionAlgorithm { get; private set; }
    public System.Security.Cryptography.RSAParameters RsaParameters { get; private set; }
    public System.Boolean IsSubKey { get; }
    public System.String KeyId { get; private set; }
    public System.String Fingerprint { get; private set; }

    public PublicKeyPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body, System.Boolean isSubkey);

    protected virtual System.Void ParseInternal(System.IO.BinaryReader reader);
}
```


## Fields

- `private System.Int32 <Version>k__BackingField`  

```csharp
private System.Int32 <Version>k__BackingField;
```

- `private System.DateTime <TimeCreated>k__BackingField`  

```csharp
private System.DateTime <TimeCreated>k__BackingField;
```

- `private PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm <EncryptionAlgorithm>k__BackingField`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm <EncryptionAlgorithm>k__BackingField;
```

- `private System.Security.Cryptography.RSAParameters <RsaParameters>k__BackingField`  

```csharp
private System.Security.Cryptography.RSAParameters <RsaParameters>k__BackingField;
```

- `private readonly System.Boolean <IsSubKey>k__BackingField`  

```csharp
private readonly System.Boolean <IsSubKey>k__BackingField;
```

- `private System.String <KeyId>k__BackingField`  

```csharp
private System.String <KeyId>k__BackingField;
```

- `private System.String <Fingerprint>k__BackingField`  

```csharp
private System.String <Fingerprint>k__BackingField;
```


## Properties

- `public System.Int32 Version { get; private set }`  

```csharp
public System.Int32 Version { get; private set; }
```

- `public System.DateTime TimeCreated { get; private set }`  

```csharp
public System.DateTime TimeCreated { get; private set; }
```

- `public PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm EncryptionAlgorithm { get; private set }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm EncryptionAlgorithm { get; private set; }
```

- `public System.Security.Cryptography.RSAParameters RsaParameters { get; private set }`  

```csharp
public System.Security.Cryptography.RSAParameters RsaParameters { get; private set; }
```

- `public System.Boolean IsSubKey { get }`  

```csharp
public System.Boolean IsSubKey { get; }
```

- `public System.String KeyId { get; private set }`  

```csharp
public System.String KeyId { get; private set; }
```

- `public System.String Fingerprint { get; private set }`  

```csharp
public System.String Fingerprint { get; private set; }
```


## Constructors

- `public PublicKeyPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body, System.Boolean isSubkey)`  

```csharp
public PublicKeyPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body, System.Boolean isSubkey);
```


## Methods

- `protected virtual ParseInternal(System.IO.BinaryReader reader) : System.Void`  

```csharp
protected virtual System.Void ParseInternal(System.IO.BinaryReader reader);
```


