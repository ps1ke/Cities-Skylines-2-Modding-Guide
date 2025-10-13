# Colossal.Mono.Cecil.ModuleParameters

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class ModuleParameters
{
    private Colossal.Mono.Cecil.ModuleKind kind;
    private Colossal.Mono.Cecil.TargetRuntime runtime;
    private System.Nullable<System.UInt32> timestamp;
    private Colossal.Mono.Cecil.TargetArchitecture architecture;
    private Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver;
    private Colossal.Mono.Cecil.IMetadataResolver metadata_resolver;
    private Colossal.Mono.Cecil.IMetadataImporterProvider metadata_importer_provider;
    private Colossal.Mono.Cecil.IReflectionImporterProvider reflection_importer_provider;

    public Colossal.Mono.Cecil.ModuleKind Kind { get; set; }
    public Colossal.Mono.Cecil.TargetRuntime Runtime { get; set; }
    public System.Nullable<System.UInt32> Timestamp { get; set; }
    public Colossal.Mono.Cecil.TargetArchitecture Architecture { get; set; }
    public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; set; }
    public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get; set; }
    public Colossal.Mono.Cecil.IMetadataImporterProvider MetadataImporterProvider { get; set; }
    public Colossal.Mono.Cecil.IReflectionImporterProvider ReflectionImporterProvider { get; set; }

    public ModuleParameters();

    private static Colossal.Mono.Cecil.TargetRuntime GetCurrentRuntime();
}
```


## Fields

- `private Colossal.Mono.Cecil.ModuleKind kind`  

```csharp
private Colossal.Mono.Cecil.ModuleKind kind;
```

- `private Colossal.Mono.Cecil.TargetRuntime runtime`  

```csharp
private Colossal.Mono.Cecil.TargetRuntime runtime;
```

- `private System.Nullable<System.UInt32> timestamp`  

```csharp
private System.Nullable<System.UInt32> timestamp;
```

- `private Colossal.Mono.Cecil.TargetArchitecture architecture`  

```csharp
private Colossal.Mono.Cecil.TargetArchitecture architecture;
```

- `private Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver`  

```csharp
private Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver;
```

- `private Colossal.Mono.Cecil.IMetadataResolver metadata_resolver`  

```csharp
private Colossal.Mono.Cecil.IMetadataResolver metadata_resolver;
```

- `private Colossal.Mono.Cecil.IMetadataImporterProvider metadata_importer_provider`  

```csharp
private Colossal.Mono.Cecil.IMetadataImporterProvider metadata_importer_provider;
```

- `private Colossal.Mono.Cecil.IReflectionImporterProvider reflection_importer_provider`  

```csharp
private Colossal.Mono.Cecil.IReflectionImporterProvider reflection_importer_provider;
```


## Properties

- `public Colossal.Mono.Cecil.ModuleKind Kind { get; set }`  

```csharp
public Colossal.Mono.Cecil.ModuleKind Kind { get; set; }
```

- `public Colossal.Mono.Cecil.TargetRuntime Runtime { get; set }`  

```csharp
public Colossal.Mono.Cecil.TargetRuntime Runtime { get; set; }
```

- `public System.Nullable<System.UInt32> Timestamp { get; set }`  

```csharp
public System.Nullable<System.UInt32> Timestamp { get; set; }
```

- `public Colossal.Mono.Cecil.TargetArchitecture Architecture { get; set }`  

```csharp
public Colossal.Mono.Cecil.TargetArchitecture Architecture { get; set; }
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


## Constructors

- `public ModuleParameters()`  

```csharp
public ModuleParameters();
```


## Methods

- `private static GetCurrentRuntime() : Colossal.Mono.Cecil.TargetRuntime`  

```csharp
private static Colossal.Mono.Cecil.TargetRuntime GetCurrentRuntime();
```


