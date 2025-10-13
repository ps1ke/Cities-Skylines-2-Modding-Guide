# PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp.Messages`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage`  

## Code

```csharp
public class PgpKeyMessage : PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage
{
    private readonly PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] <Packets>k__BackingField;
    private System.String <KeyId>k__BackingField;
    private System.DateTime <Issued>k__BackingField;

    public PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] Packets { get; }
    public System.String KeyId { get; private set; }
    public System.DateTime Issued { get; set; }

    public PgpKeyMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets);

}
```


## Fields

- `private readonly PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] <Packets>k__BackingField`  

```csharp
private readonly PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] <Packets>k__BackingField;
```

- `private System.String <KeyId>k__BackingField`  

```csharp
private System.String <KeyId>k__BackingField;
```

- `private System.DateTime <Issued>k__BackingField`  

```csharp
private System.DateTime <Issued>k__BackingField;
```


## Properties

- `public PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] Packets { get }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] Packets { get; }
```

- `public System.String KeyId { get; private set }`  

```csharp
public System.String KeyId { get; private set; }
```

- `public System.DateTime Issued { get; set }`  

```csharp
public System.DateTime Issued { get; set; }
```


## Constructors

- `public PgpKeyMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets)`  

```csharp
public PgpKeyMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets);
```


