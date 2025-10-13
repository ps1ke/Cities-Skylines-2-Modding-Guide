# PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp.Messages`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage`  

## Code

```csharp
public class PgpSignatureMessage : PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage
{
    private readonly PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] <Packets>k__BackingField;
    private System.String <SignedBy>k__BackingField;

    public PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] Packets { get; }
    public System.String SignedBy { get; private set; }

    public PgpSignatureMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets);

}
```


## Fields

- `private readonly PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] <Packets>k__BackingField`  

```csharp
private readonly PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] <Packets>k__BackingField;
```

- `private System.String <SignedBy>k__BackingField`  

```csharp
private System.String <SignedBy>k__BackingField;
```


## Properties

- `public PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] Packets { get }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] Packets { get; }
```

- `public System.String SignedBy { get; private set }`  

```csharp
public System.String SignedBy { get; private set; }
```


## Constructors

- `public PgpSignatureMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets)`  

```csharp
public PgpSignatureMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets);
```


