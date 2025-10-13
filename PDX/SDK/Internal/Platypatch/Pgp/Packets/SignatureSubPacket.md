# PDX.SDK.Internal.Platypatch.Pgp.Packets.SignatureSubPacket

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp.Packets`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class SignatureSubPacket
{
    private readonly PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType <Type>k__BackingField;
    private readonly System.UInt32 <Length>k__BackingField;
    private readonly System.Byte[] <Body>k__BackingField;

    public PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType Type { get; }
    public System.UInt32 Length { get; }
    public System.Byte[] Body { get; }

    public SignatureSubPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType type, System.UInt32 length, System.Byte[] body);

    protected abstract System.Void ParseInternal(System.IO.BinaryReader reader);
}
```


## Fields

- `private readonly PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType <Type>k__BackingField`  

```csharp
private readonly PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType <Type>k__BackingField;
```

- `private readonly System.UInt32 <Length>k__BackingField`  

```csharp
private readonly System.UInt32 <Length>k__BackingField;
```

- `private readonly System.Byte[] <Body>k__BackingField`  

```csharp
private readonly System.Byte[] <Body>k__BackingField;
```


## Properties

- `public PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType Type { get }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType Type { get; }
```

- `public System.UInt32 Length { get }`  

```csharp
public System.UInt32 Length { get; }
```

- `public System.Byte[] Body { get }`  

```csharp
public System.Byte[] Body { get; }
```


## Constructors

- `public SignatureSubPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType type, System.UInt32 length, System.Byte[] body)`  

```csharp
public SignatureSubPacket(PDX.SDK.Internal.Platypatch.Pgp.Enums.SignatureSubPacketType type, System.UInt32 length, System.Byte[] body);
```


## Methods

- `protected abstract ParseInternal(System.IO.BinaryReader reader) : System.Void`  

```csharp
protected abstract System.Void ParseInternal(System.IO.BinaryReader reader);
```


