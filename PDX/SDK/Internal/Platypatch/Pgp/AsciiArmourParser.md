# PDX.SDK.Internal.Platypatch.Pgp.AsciiArmourParser

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Platypatch.Pgp`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AsciiArmourParser
{
    private static PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage ConstructMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets);
    private static System.UInt32 FourOctetLength(System.IO.BinaryReader reader);
    public static PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage GetMessage(System.String armour);
    private static System.UInt32 OneOctetLength(System.Int32 lengthPacket);
    private static PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] ParsePackets(System.Byte[] binaryData);
    private static System.UInt32 TwoOctetLengthNewFormat(System.IO.BinaryReader reader, System.Int32 lengthPacket);
    private static System.UInt32 TwoOctetLengthOldFormat(System.IO.BinaryReader reader, System.Int32 lengthPacket);
}
```


## Methods

- `private static ConstructMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets) : PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage`  

```csharp
private static PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage ConstructMessage(PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] packets);
```

- `private static FourOctetLength(System.IO.BinaryReader reader) : System.UInt32`  

```csharp
private static System.UInt32 FourOctetLength(System.IO.BinaryReader reader);
```

- `public static GetMessage(System.String armour) : PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage`  

```csharp
public static PDX.SDK.Internal.Platypatch.Pgp.Messages.IPgpMessage GetMessage(System.String armour);
```

- `private static OneOctetLength(System.Int32 lengthPacket) : System.UInt32`  

```csharp
private static System.UInt32 OneOctetLength(System.Int32 lengthPacket);
```

- `private static ParsePackets(System.Byte[] binaryData) : PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[]`  

```csharp
private static PDX.SDK.Internal.Platypatch.Pgp.Packets.Packet[] ParsePackets(System.Byte[] binaryData);
```

- `private static TwoOctetLengthNewFormat(System.IO.BinaryReader reader, System.Int32 lengthPacket) : System.UInt32`  

```csharp
private static System.UInt32 TwoOctetLengthNewFormat(System.IO.BinaryReader reader, System.Int32 lengthPacket);
```

- `private static TwoOctetLengthOldFormat(System.IO.BinaryReader reader, System.Int32 lengthPacket) : System.UInt32`  

```csharp
private static System.UInt32 TwoOctetLengthOldFormat(System.IO.BinaryReader reader, System.Int32 lengthPacket);
```


