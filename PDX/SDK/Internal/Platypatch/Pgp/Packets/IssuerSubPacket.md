# PDX.SDK.Internal.Platypatch.Pgp.Packets.IssuerSubPacket

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp.Packets`  

**Type:** class public  

**Base:** `PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket`  

## Code

```csharp
public class IssuerSubPacket : PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket
{
    private System.UInt64 <SignerKeyId>k__BackingField;
    private System.String <SignerkeyIdString>k__BackingField;

    public System.UInt64 SignerKeyId { get; set; }
    public System.String SignerkeyIdString { get; set; }

    public IssuerSubPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType type, System.UInt32 length, System.Byte[] body);

    protected virtual System.Void ParseInternal(System.IO.BinaryReader reader);
}
```


## Fields

- `private System.UInt64 <SignerKeyId>k__BackingField`  

```csharp
private System.UInt64 <SignerKeyId>k__BackingField;
```

- `private System.String <SignerkeyIdString>k__BackingField`  

```csharp
private System.String <SignerkeyIdString>k__BackingField;
```


## Properties

- `public System.UInt64 SignerKeyId { get; set }`  

```csharp
public System.UInt64 SignerKeyId { get; set; }
```

- `public System.String SignerkeyIdString { get; set }`  

```csharp
public System.String SignerkeyIdString { get; set; }
```


## Constructors

- `public IssuerSubPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType type, System.UInt32 length, System.Byte[] body)`  

```csharp
public IssuerSubPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType type, System.UInt32 length, System.Byte[] body);
```


## Methods

- `protected virtual ParseInternal(System.IO.BinaryReader reader) : System.Void`  

```csharp
protected virtual System.Void ParseInternal(System.IO.BinaryReader reader);
```


