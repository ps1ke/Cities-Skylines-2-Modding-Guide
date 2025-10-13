# PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp`  

**Type:** interface abstract public  


**Attributes:** `Preserve`  

## Code

```csharp
public abstract interface IMessageValidator
{
    public abstract System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
    public abstract System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
}
```


## Methods

- `public abstract IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing) : System.Boolean`  

```csharp
public abstract System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
```

- `public abstract IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing) : System.Boolean`  

```csharp
public abstract System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
```


