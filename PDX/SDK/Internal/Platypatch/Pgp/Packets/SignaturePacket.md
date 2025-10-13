# PDX.SDK.Internal.Platypatch.Pgp.Packets.SignaturePacket

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp.Packets`  

**Type:** class public  

**Base:** `PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet`  

## Code

```csharp
public class SignaturePacket : PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet
{
    private System.Int32 <Version>k__BackingField;
    private PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureType <SignatureType>k__BackingField;
    private PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm <PublicKeyAlgorithm>k__BackingField;
    private PDX.SDK.Internal.Platypatch.Pgp.Enums.HashAlgorithm <HashAlgorithm>k__BackingField;
    private PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] <HashedSubpacketDataSet>k__BackingField;
    private PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] <UnhashedSubpacketDataSet>k__BackingField;
    private PDX.SDK.Internal.Platypatch.Pgp.Models.MultiPrecisionInteger[] <Signature>k__BackingField;
    private System.Byte[] <Fingerprint>k__BackingField;
    private System.String <IssuerKey>k__BackingField;
    private System.UInt32 <HashedLength>k__BackingField;

    public System.Int32 Version { get; private set; }
    public PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureType SignatureType { get; private set; }
    public PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm PublicKeyAlgorithm { get; private set; }
    public PDX.SDK.Internal.Platypatch.Pgp.Enums.HashAlgorithm HashAlgorithm { get; private set; }
    public PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] HashedSubpacketDataSet { get; private set; }
    public PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] UnhashedSubpacketDataSet { get; private set; }
    public PDX.SDK.Internal.Platypatch.Pgp.Models.MultiPrecisionInteger[] Signature { get; private set; }
    public System.Byte[] Fingerprint { get; private set; }
    public System.String IssuerKey { get; private set; }
    public System.UInt32 HashedLength { get; set; }

    public SignaturePacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body);

    protected virtual System.Void ParseInternal(System.IO.BinaryReader reader);
    private PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] ProcessSubpackets(System.IO.BinaryReader reader, System.Int32 count);
}
```


## Fields

- `private System.Int32 <Version>k__BackingField`  

```csharp
private System.Int32 <Version>k__BackingField;
```

- `private PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureType <SignatureType>k__BackingField`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureType <SignatureType>k__BackingField;
```

- `private PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm <PublicKeyAlgorithm>k__BackingField`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm <PublicKeyAlgorithm>k__BackingField;
```

- `private PDX.SDK.Internal.Platypatch.Pgp.Enums.HashAlgorithm <HashAlgorithm>k__BackingField`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Enums.HashAlgorithm <HashAlgorithm>k__BackingField;
```

- `private PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] <HashedSubpacketDataSet>k__BackingField`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] <HashedSubpacketDataSet>k__BackingField;
```

- `private PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] <UnhashedSubpacketDataSet>k__BackingField`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] <UnhashedSubpacketDataSet>k__BackingField;
```

- `private PDX.SDK.Internal.Platypatch.Pgp.Models.MultiPrecisionInteger[] <Signature>k__BackingField`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Models.MultiPrecisionInteger[] <Signature>k__BackingField;
```

- `private System.Byte[] <Fingerprint>k__BackingField`  

```csharp
private System.Byte[] <Fingerprint>k__BackingField;
```

- `private System.String <IssuerKey>k__BackingField`  

```csharp
private System.String <IssuerKey>k__BackingField;
```

- `private System.UInt32 <HashedLength>k__BackingField`  

```csharp
private System.UInt32 <HashedLength>k__BackingField;
```


## Properties

- `public System.Int32 Version { get; private set }`  

```csharp
public System.Int32 Version { get; private set; }
```

- `public PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureType SignatureType { get; private set }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureType SignatureType { get; private set; }
```

- `public PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm PublicKeyAlgorithm { get; private set }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Enums.PublicKeyEncryptionAlgorithm PublicKeyAlgorithm { get; private set; }
```

- `public PDX.SDK.Internal.Platypatch.Pgp.Enums.HashAlgorithm HashAlgorithm { get; private set }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Enums.HashAlgorithm HashAlgorithm { get; private set; }
```

- `public PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] HashedSubpacketDataSet { get; private set }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] HashedSubpacketDataSet { get; private set; }
```

- `public PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] UnhashedSubpacketDataSet { get; private set }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] UnhashedSubpacketDataSet { get; private set; }
```

- `public PDX.SDK.Internal.Platypatch.Pgp.Models.MultiPrecisionInteger[] Signature { get; private set }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Models.MultiPrecisionInteger[] Signature { get; private set; }
```

- `public System.Byte[] Fingerprint { get; private set }`  

```csharp
public System.Byte[] Fingerprint { get; private set; }
```

- `public System.String IssuerKey { get; private set }`  

```csharp
public System.String IssuerKey { get; private set; }
```

- `public System.UInt32 HashedLength { get; set }`  

```csharp
public System.UInt32 HashedLength { get; set; }
```


## Constructors

- `public SignaturePacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body)`  

```csharp
public SignaturePacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body);
```


## Methods

- `protected virtual ParseInternal(System.IO.BinaryReader reader) : System.Void`  

```csharp
protected virtual System.Void ParseInternal(System.IO.BinaryReader reader);
```

- `private ProcessSubpackets(System.IO.BinaryReader reader, System.Int32 count) : PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[]`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket[] ProcessSubpackets(System.IO.BinaryReader reader, System.Int32 count);
```


