# PDX.SDK.Internal.Platypatch.Pgp.KeyRing

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public class KeyRing
{
    private readonly PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator _messageValidator;
    private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage> _keys;

    public PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage Item { get; }

    public KeyRing(PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator messageValidator);

    public System.Void Add(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, System.Boolean isRootKey);
    private System.Void ValidateKey(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message);
}
```


## Fields

- `private readonly PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator _messageValidator`  

```csharp
private readonly PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator _messageValidator;
```

- `private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage> _keys`  

```csharp
private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage> _keys;
```


## Properties

- `public PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage Item { get }`  

```csharp
public PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage Item { get; }
```


## Constructors

- `public KeyRing(PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator messageValidator)`  

```csharp
public KeyRing(PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator messageValidator);
```


## Methods

- `public Add(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, System.Boolean isRootKey) : System.Void`  

```csharp
public System.Void Add(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, System.Boolean isRootKey);
```

- `private ValidateKey(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message) : System.Void`  

```csharp
private System.Void ValidateKey(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message);
```


