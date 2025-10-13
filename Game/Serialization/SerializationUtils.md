# Game.Serialization.SerializationUtils

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class SerializationUtils
{
    public static Colossal.AssetPipeline.Native.CompressionFormat BufferToCompressionFormat(Colossal.Serialization.Entities.BufferFormat format);
    public static System.Boolean IsCompressed(Colossal.Serialization.Entities.BufferFormat format);
}
```


## Methods

- `public static BufferToCompressionFormat(Colossal.Serialization.Entities.BufferFormat format) : Colossal.AssetPipeline.Native.CompressionFormat`  

```csharp
public static CompressionFormat BufferToCompressionFormat(BufferFormat format)
	{
		return format switch
		{
			BufferFormat.CompressedLZ4 => CompressionFormat.LZ4, 
			BufferFormat.CompressedZStd => CompressionFormat.ZSTD, 
			_ => throw new FormatException($"Invalid format {format}"), 
		};
	}
```

- `public static IsCompressed(Colossal.Serialization.Entities.BufferFormat format) : System.Boolean`  

```csharp
public static bool IsCompressed(this BufferFormat format)
	{
		if (format != BufferFormat.CompressedLZ4)
		{
			return format == BufferFormat.CompressedZStd;
		}
		return true;
	}
```


