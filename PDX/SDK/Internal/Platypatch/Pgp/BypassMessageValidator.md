# PDX.SDK.Internal.Platypatch.Pgp.BypassMessageValidator

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator`  

## Code

```csharp
public class BypassMessageValidator : PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator
{
    public BypassMessageValidator();

    public System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
    public System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
}
```


## Constructors

- `public BypassMessageValidator()`  

```csharp
public BypassMessageValidator();
```


## Methods

- `public IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing) : System.Boolean`  

```csharp
public System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
```

- `public IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing) : System.Boolean`  

```csharp
public System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
```


