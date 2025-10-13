# Colossal.Mono.Cecil.WriterParameters

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class WriterParameters
{
    private System.Nullable<System.UInt32> timestamp;
    private System.IO.Stream symbol_stream;
    private Colossal.Mono.Cecil.Cil.ISymbolWriterProvider symbol_writer_provider;
    private System.Boolean write_symbols;
    private System.Byte[] key_blob;
    private System.String key_container;
    private System.Reflection.StrongNameKeyPair key_pair;
    private System.Boolean <DeterministicMvid>k__BackingField;

    public System.Nullable<System.UInt32> Timestamp { get; set; }
    public System.IO.Stream SymbolStream { get; set; }
    public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider SymbolWriterProvider { get; set; }
    public System.Boolean WriteSymbols { get; set; }
    public System.Boolean HasStrongNameKey { get; }
    public System.Byte[] StrongNameKeyBlob { get; set; }
    public System.String StrongNameKeyContainer { get; set; }
    public System.Reflection.StrongNameKeyPair StrongNameKeyPair { get; set; }
    public System.Boolean DeterministicMvid { get; set; }

    public WriterParameters();

}
```


## Fields

- `private System.Nullable<System.UInt32> timestamp`  

```csharp
private System.Nullable<System.UInt32> timestamp;
```

- `private System.IO.Stream symbol_stream`  

```csharp
private System.IO.Stream symbol_stream;
```

- `private Colossal.Mono.Cecil.Cil.ISymbolWriterProvider symbol_writer_provider`  

```csharp
private Colossal.Mono.Cecil.Cil.ISymbolWriterProvider symbol_writer_provider;
```

- `private System.Boolean write_symbols`  

```csharp
private System.Boolean write_symbols;
```

- `private System.Byte[] key_blob`  

```csharp
private System.Byte[] key_blob;
```

- `private System.String key_container`  

```csharp
private System.String key_container;
```

- `private System.Reflection.StrongNameKeyPair key_pair`  

```csharp
private System.Reflection.StrongNameKeyPair key_pair;
```

- `private System.Boolean <DeterministicMvid>k__BackingField`  

```csharp
private System.Boolean <DeterministicMvid>k__BackingField;
```


## Properties

- `public System.Nullable<System.UInt32> Timestamp { get; set }`  

```csharp
public System.Nullable<System.UInt32> Timestamp { get; set; }
```

- `public System.IO.Stream SymbolStream { get; set }`  

```csharp
public System.IO.Stream SymbolStream { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider SymbolWriterProvider { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider SymbolWriterProvider { get; set; }
```

- `public System.Boolean WriteSymbols { get; set }`  

```csharp
public System.Boolean WriteSymbols { get; set; }
```

- `public System.Boolean HasStrongNameKey { get }`  

```csharp
public System.Boolean HasStrongNameKey { get; }
```

- `public System.Byte[] StrongNameKeyBlob { get; set }`  

```csharp
public System.Byte[] StrongNameKeyBlob { get; set; }
```

- `public System.String StrongNameKeyContainer { get; set }`  

```csharp
public System.String StrongNameKeyContainer { get; set; }
```

- `public System.Reflection.StrongNameKeyPair StrongNameKeyPair { get; set }`  

```csharp
public System.Reflection.StrongNameKeyPair StrongNameKeyPair { get; set; }
```

- `public System.Boolean DeterministicMvid { get; set }`  

```csharp
public System.Boolean DeterministicMvid { get; set; }
```


## Constructors

- `public WriterParameters()`  

```csharp
public WriterParameters();
```


