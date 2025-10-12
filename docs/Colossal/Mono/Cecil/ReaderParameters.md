# Colossal.Mono.Cecil.ReaderParameters

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Fields

- `private Colossal.Mono.Cecil.ReadingMode reading_mode`  
- `internal Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver`  
- `internal Colossal.Mono.Cecil.IMetadataResolver metadata_resolver`  
- `internal Colossal.Mono.Cecil.IMetadataImporterProvider metadata_importer_provider`  
- `internal Colossal.Mono.Cecil.IReflectionImporterProvider reflection_importer_provider`  
- `private System.IO.Stream symbol_stream`  
- `private Colossal.Mono.Cecil.Cil.ISymbolReaderProvider symbol_reader_provider`  
- `private System.Boolean read_symbols`  
- `private System.Boolean throw_symbols_mismatch`  
- `private System.Boolean projections`  
- `private System.Boolean in_memory`  
- `private System.Boolean read_write`  

## Properties

- `public Colossal.Mono.Cecil.ReadingMode ReadingMode { get; set }`  
- `public System.Boolean InMemory { get; set }`  
- `public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; set }`  
- `public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get; set }`  
- `public Colossal.Mono.Cecil.IMetadataImporterProvider MetadataImporterProvider { get; set }`  
- `public Colossal.Mono.Cecil.IReflectionImporterProvider ReflectionImporterProvider { get; set }`  
- `public System.IO.Stream SymbolStream { get; set }`  
- `public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider SymbolReaderProvider { get; set }`  
- `public System.Boolean ReadSymbols { get; set }`  
- `public System.Boolean ThrowIfSymbolsAreNotMatching { get; set }`  
- `public System.Boolean ReadWrite { get; set }`  
- `public System.Boolean ApplyWindowsRuntimeProjections { get; set }`  

## Constructors

- `public ReaderParameters()`  
- `public ReaderParameters(Colossal.Mono.Cecil.ReadingMode readingMode)`  

