# PDX.SDK.Internal.Platypatch.Pgp.MessageValidator

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator`  

**Attributes:** `Preserve`  

## Code

```csharp
public class MessageValidator : PDX.SDK.Internal.Platypatch.Pgp.IMessageValidator
{
    public MessageValidator();

    private System.Void AddV4Trailer(PDX.SDK.Internal.Platypatch.Pgp.Packets.SignaturePacket signature, System.Collections.Generic.List<System.Byte> hashedData);
    private PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage FindInKeyring(System.String keyId, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
    private static System.Byte[] GetRSASignatureWithPkcs1Padding(System.Byte[] rsaSignature, System.Int32 rsaKeyLength);
    public System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
    public System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
}
```


## Constructors

- `public MessageValidator()`  

```csharp
public MessageValidator();
```


## Methods

- `private AddV4Trailer(PDX.SDK.Internal.Platypatch.Pgp.Packets.SignaturePacket signature, System.Collections.Generic.List<System.Byte> hashedData) : System.Void`  

```csharp
private System.Void AddV4Trailer(PDX.SDK.Internal.Platypatch.Pgp.Packets.SignaturePacket signature, System.Collections.Generic.List<System.Byte> hashedData);
```

- `private FindInKeyring(System.String keyId, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing) : PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage`  

```csharp
private PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage FindInKeyring(System.String keyId, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
```

- `private static GetRSASignatureWithPkcs1Padding(System.Byte[] rsaSignature, System.Int32 rsaKeyLength) : System.Byte[]`  

```csharp
private static System.Byte[] GetRSASignatureWithPkcs1Padding(System.Byte[] rsaSignature, System.Int32 rsaKeyLength);
```

- `public IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing) : System.Boolean`  

```csharp
public System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpSignatureMessage message, System.Byte[] data, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
```

- `public IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing) : System.Boolean`  

```csharp
public System.Boolean IsValid(PDX.SDK.Internal.Platypatch.Pgp.Messages.PgpKeyMessage message, PDX.SDK.Internal.Platypatch.Pgp.KeyRing keyRing);
```


## Nested types

- `PDX.SDK.Internal.Platypatch.Pgp.MessageValidator+<>c__DisplayClass0_0`  
- `PDX.SDK.Internal.Platypatch.Pgp.MessageValidator+<>c__DisplayClass2_0`  

