# PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp.Packets`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class Packet
{
    private readonly PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType <Tag>k__BackingField;
    private readonly System.UInt32 <Length>k__BackingField;
    private readonly System.Byte[] <Body>k__BackingField;

    public PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType Tag { get; }
    public System.UInt32 Length { get; }
    public System.Byte[] Body { get; }

    public Packet(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body);

    protected abstract System.Void ParseInternal(System.IO.BinaryReader reader);
}
```


## Fields

- `private readonly PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType <Tag>k__BackingField`  

```csharp
private readonly PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType <Tag>k__BackingField;
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

- `public PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType Tag { get }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType Tag { get; }
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

- `public Packet(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body)`  

```csharp
public Packet(PDX.SDK.Internal.Platypatch.Pgp.Enums.TagType type, System.UInt32 length, System.Byte[] body);
```


## Methods

- `protected abstract ParseInternal(System.IO.BinaryReader reader) : System.Void`  

```csharp
protected abstract System.Void ParseInternal(System.IO.BinaryReader reader);
```


