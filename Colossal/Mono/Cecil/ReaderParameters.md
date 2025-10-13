# Colossal.Mono.Cecil.ReaderParameters

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class ReaderParameters
{
    private Colossal.Mono.Cecil.ReadingMode reading_mode;
    internal Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver;
    internal Colossal.Mono.Cecil.IMetadataResolver metadata_resolver;
    internal Colossal.Mono.Cecil.IMetadataImporterProvider metadata_importer_provider;
    internal Colossal.Mono.Cecil.IReflectionImporterProvider reflection_importer_provider;
    private System.IO.Stream symbol_stream;
    private Colossal.Mono.Cecil.Cil.ISymbolReaderProvider symbol_reader_provider;
    private System.Boolean read_symbols;
    private System.Boolean throw_symbols_mismatch;
    private System.Boolean projections;
    private System.Boolean in_memory;
    private System.Boolean read_write;

    public Colossal.Mono.Cecil.ReadingMode ReadingMode { get; set; }
    public System.Boolean InMemory { get; set; }
    public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; set; }
    public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get; set; }
    public Colossal.Mono.Cecil.IMetadataImporterProvider MetadataImporterProvider { get; set; }
    public Colossal.Mono.Cecil.IReflectionImporterProvider ReflectionImporterProvider { get; set; }
    public System.IO.Stream SymbolStream { get; set; }
    public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider SymbolReaderProvider { get; set; }
    public System.Boolean ReadSymbols { get; set; }
    public System.Boolean ThrowIfSymbolsAreNotMatching { get; set; }
    public System.Boolean ReadWrite { get; set; }
    public System.Boolean ApplyWindowsRuntimeProjections { get; set; }

    public ReaderParameters();
    public ReaderParameters(Colossal.Mono.Cecil.ReadingMode readingMode);

}
```


## Fields

- `private Colossal.Mono.Cecil.ReadingMode reading_mode`  

```csharp
private Colossal.Mono.Cecil.ReadingMode reading_mode;
```

- `internal Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver`  

```csharp
internal Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver;
```

- `internal Colossal.Mono.Cecil.IMetadataResolver metadata_resolver`  

```csharp
internal Colossal.Mono.Cecil.IMetadataResolver metadata_resolver;
```

- `internal Colossal.Mono.Cecil.IMetadataImporterProvider metadata_importer_provider`  

```csharp
internal Colossal.Mono.Cecil.IMetadataImporterProvider metadata_importer_provider;
```

- `internal Colossal.Mono.Cecil.IReflectionImporterProvider reflection_importer_provider`  

```csharp
internal Colossal.Mono.Cecil.IReflectionImporterProvider reflection_importer_provider;
```

- `private System.IO.Stream symbol_stream`  

```csharp
private System.IO.Stream symbol_stream;
```

- `private Colossal.Mono.Cecil.Cil.ISymbolReaderProvider symbol_reader_provider`  

```csharp
private Colossal.Mono.Cecil.Cil.ISymbolReaderProvider symbol_reader_provider;
```

- `private System.Boolean read_symbols`  

```csharp
private System.Boolean read_symbols;
```

- `private System.Boolean throw_symbols_mismatch`  

```csharp
private System.Boolean throw_symbols_mismatch;
```

- `private System.Boolean projections`  

```csharp
private System.Boolean projections;
```

- `private System.Boolean in_memory`  

```csharp
private System.Boolean in_memory;
```

- `private System.Boolean read_write`  

```csharp
private System.Boolean read_write;
```


## Properties

- `public Colossal.Mono.Cecil.ReadingMode ReadingMode { get; set }`  

```csharp
public Colossal.Mono.Cecil.ReadingMode ReadingMode { get; set; }
```

- `public System.Boolean InMemory { get; set }`  

```csharp
public System.Boolean InMemory { get; set; }
```

- `public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; set }`  

```csharp
public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; set; }
```

- `public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get; set }`  

```csharp
public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get; set; }
```

- `public Colossal.Mono.Cecil.IMetadataImporterProvider MetadataImporterProvider { get; set }`  

```csharp
public Colossal.Mono.Cecil.IMetadataImporterProvider MetadataImporterProvider { get; set; }
```

- `public Colossal.Mono.Cecil.IReflectionImporterProvider ReflectionImporterProvider { get; set }`  

```csharp
public Colossal.Mono.Cecil.IReflectionImporterProvider ReflectionImporterProvider { get; set; }
```

- `public System.IO.Stream SymbolStream { get; set }`  

```csharp
public System.IO.Stream SymbolStream { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider SymbolReaderProvider { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider SymbolReaderProvider { get; set; }
```

- `public System.Boolean ReadSymbols { get; set }`  

```csharp
public System.Boolean ReadSymbols { get; set; }
```

- `public System.Boolean ThrowIfSymbolsAreNotMatching { get; set }`  

```csharp
public System.Boolean ThrowIfSymbolsAreNotMatching { get; set; }
```

- `public System.Boolean ReadWrite { get; set }`  

```csharp
public System.Boolean ReadWrite { get; set; }
```

- `public System.Boolean ApplyWindowsRuntimeProjections { get; set }`  

```csharp
public System.Boolean ApplyWindowsRuntimeProjections { get; set; }
```


## Constructors

- `public ReaderParameters()`  

```csharp
public ReaderParameters();
```

- `public ReaderParameters(Colossal.Mono.Cecil.ReadingMode readingMode)`  

```csharp
public ReaderParameters(Colossal.Mono.Cecil.ReadingMode readingMode);
```


