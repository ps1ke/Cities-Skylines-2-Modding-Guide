# Colossal.Mono.Cecil.ModuleDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.ModuleReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataScope`, `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `System.IDisposable`  

## Code

```csharp
public sealed class ModuleDefinition : Colossal.Mono.Cecil.ModuleReference, Colossal.Mono.Cecil.IMetadataScope, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.ICustomAttributeProvider, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, System.IDisposable
{
    internal Colossal.Mono.Cecil.PE.Image Image;
    internal Colossal.Mono.Cecil.MetadataSystem MetadataSystem;
    internal Colossal.Mono.Cecil.ReadingMode ReadingMode;
    internal Colossal.Mono.Cecil.Cil.ISymbolReaderProvider SymbolReaderProvider;
    internal Colossal.Mono.Cecil.Cil.ISymbolReader symbol_reader;
    internal Colossal.Mono.Disposable<Colossal.Mono.Cecil.IAssemblyResolver> assembly_resolver;
    internal Colossal.Mono.Cecil.IMetadataResolver metadata_resolver;
    internal Colossal.Mono.Cecil.TypeSystem type_system;
    internal readonly Colossal.Mono.Cecil.MetadataReader reader;
    private readonly System.String file_name;
    internal System.String runtime_version;
    internal Colossal.Mono.Cecil.ModuleKind kind;
    private Colossal.Mono.Cecil.WindowsRuntimeProjections projections;
    private Colossal.Mono.Cecil.MetadataKind metadata_kind;
    private Colossal.Mono.Cecil.TargetRuntime runtime;
    private Colossal.Mono.Cecil.TargetArchitecture architecture;
    private Colossal.Mono.Cecil.ModuleAttributes attributes;
    private Colossal.Mono.Cecil.ModuleCharacteristics characteristics;
    private System.Guid mvid;
    internal System.UInt16 linker_version;
    internal System.UInt16 subsystem_major;
    internal System.UInt16 subsystem_minor;
    internal System.UInt32 timestamp;
    internal Colossal.Mono.Cecil.AssemblyDefinition assembly;
    private Colossal.Mono.Cecil.MethodDefinition entry_point;
    private System.Boolean entry_point_set;
    internal Colossal.Mono.Cecil.IReflectionImporter reflection_importer;
    internal Colossal.Mono.Cecil.IMetadataImporter metadata_importer;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.AssemblyNameReference> references;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleReference> modules;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Resource> resources;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ExportedType> exported_types;
    private Colossal.Mono.Cecil.TypeDefinitionCollection types;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> custom_infos;
    internal Colossal.Mono.Cecil.MetadataBuilder metadata_builder;
    private readonly System.Object module_lock;

    public System.Boolean IsMain { get; }
    public Colossal.Mono.Cecil.ModuleKind Kind { get; set; }
    public Colossal.Mono.Cecil.MetadataKind MetadataKind { get; set; }
    internal Colossal.Mono.Cecil.WindowsRuntimeProjections Projections { internal get; }
    public Colossal.Mono.Cecil.TargetRuntime Runtime { get; set; }
    public System.String RuntimeVersion { get; set; }
    public Colossal.Mono.Cecil.TargetArchitecture Architecture { get; set; }
    public Colossal.Mono.Cecil.ModuleAttributes Attributes { get; set; }
    public Colossal.Mono.Cecil.ModuleCharacteristics Characteristics { get; set; }
    public System.String FullyQualifiedName { get; }
    public System.String FileName { get; }
    public System.Guid Mvid { get; set; }
    internal System.Boolean HasImage { internal get; }
    public System.Boolean HasSymbols { get; }
    public Colossal.Mono.Cecil.Cil.ISymbolReader SymbolReader { get; }
    public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get; }
    public Colossal.Mono.Cecil.AssemblyDefinition Assembly { get; }
    internal Colossal.Mono.Cecil.IReflectionImporter ReflectionImporter { internal get; }
    internal Colossal.Mono.Cecil.IMetadataImporter MetadataImporter { internal get; }
    public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; }
    public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get; }
    public Colossal.Mono.Cecil.TypeSystem TypeSystem { get; }
    public System.Boolean HasAssemblyReferences { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.AssemblyNameReference> AssemblyReferences { get; }
    public System.Boolean HasModuleReferences { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleReference> ModuleReferences { get; }
    public System.Boolean HasResources { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Resource> Resources { get; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public System.Boolean HasTypes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> Types { get; }
    public System.Boolean HasExportedTypes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ExportedType> ExportedTypes { get; }
    public Colossal.Mono.Cecil.MethodDefinition EntryPoint { get; set; }
    public System.Boolean HasCustomDebugInformations { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> CustomDebugInformations { get; }
    internal System.Object SyncRoot { internal get; }
    public System.Boolean HasDebugHeader { get; }

    internal ModuleDefinition();
    internal ModuleDefinition(Colossal.Mono.Cecil.PE.Image image);

    private static System.Void CheckContext(Colossal.Mono.Cecil.IGenericParameterProvider context, Colossal.Mono.Cecil.ModuleDefinition module);
    private static Colossal.Mono.Cecil.AssemblyNameDefinition CreateAssemblyName(System.String name);
    public static Colossal.Mono.Cecil.ModuleDefinition CreateModule(System.String name, Colossal.Mono.Cecil.ModuleKind kind);
    public static Colossal.Mono.Cecil.ModuleDefinition CreateModule(System.String name, Colossal.Mono.Cecil.ModuleParameters parameters);
    public System.Void Dispose();
    public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.CustomAttribute> GetCustomAttributes();
    public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
    private static System.IO.Stream GetFileStream(System.String fileName, System.IO.FileMode mode, System.IO.FileAccess access, System.IO.FileShare share);
    public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.MemberReference> GetMemberReferences();
    private Colossal.Mono.Cecil.TypeDefinition GetNestedType(System.String fullname);
    public Colossal.Mono.Cecil.TypeReference GetType(System.String fullName, System.Boolean runtimeName);
    public Colossal.Mono.Cecil.TypeDefinition GetType(System.String fullName);
    public Colossal.Mono.Cecil.TypeDefinition GetType(System.String namespace, System.String name);
    private Colossal.Mono.Cecil.TypeReference GetTypeReference(System.String scope, System.String fullname);
    public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeReference> GetTypeReferences();
    public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeDefinition> GetTypes();
    private static System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeDefinition> GetTypes(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> types);
    public System.Boolean HasTypeReference(System.String fullName);
    public System.Boolean HasTypeReference(System.String scope, System.String fullName);
    public System.Void ImmediateRead();
    public Colossal.Mono.Cecil.TypeReference Import(System.Type type);
    public Colossal.Mono.Cecil.TypeReference Import(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.FieldReference Import(System.Reflection.FieldInfo field);
    public Colossal.Mono.Cecil.FieldReference Import(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.MethodReference Import(System.Reflection.MethodBase method);
    public Colossal.Mono.Cecil.MethodReference Import(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.TypeReference Import(Colossal.Mono.Cecil.TypeReference type);
    public Colossal.Mono.Cecil.TypeReference Import(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.FieldReference Import(Colossal.Mono.Cecil.FieldReference field);
    public Colossal.Mono.Cecil.FieldReference Import(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.MethodReference Import(Colossal.Mono.Cecil.MethodReference method);
    public Colossal.Mono.Cecil.MethodReference Import(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.TypeReference ImportReference(System.Type type);
    public Colossal.Mono.Cecil.TypeReference ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.FieldReference ImportReference(System.Reflection.FieldInfo field);
    public Colossal.Mono.Cecil.FieldReference ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.MethodReference ImportReference(System.Reflection.MethodBase method);
    public Colossal.Mono.Cecil.MethodReference ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.TypeReference ImportReference(Colossal.Mono.Cecil.TypeReference type);
    public Colossal.Mono.Cecil.TypeReference ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.FieldReference ImportReference(Colossal.Mono.Cecil.FieldReference field);
    public Colossal.Mono.Cecil.FieldReference ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.MethodReference ImportReference(Colossal.Mono.Cecil.MethodReference method);
    public Colossal.Mono.Cecil.MethodReference ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public Colossal.Mono.Cecil.IMetadataTokenProvider LookupToken(System.Int32 token);
    public Colossal.Mono.Cecil.IMetadataTokenProvider LookupToken(Colossal.Mono.Cecil.MetadataToken token);
    internal System.Void Read<TItem>(TItem item, System.Action<TItem, Colossal.Mono.Cecil.MetadataReader> read);
    internal TRet Read<TItem, TRet>(TItem item, System.Func<TItem, Colossal.Mono.Cecil.MetadataReader, TRet> read);
    internal TRet Read<TItem, TRet>(TRet& variable, TItem item, System.Func<TItem, Colossal.Mono.Cecil.MetadataReader, TRet> read);
    public static Colossal.Mono.Cecil.ModuleDefinition ReadModule(System.String fileName);
    public static Colossal.Mono.Cecil.ModuleDefinition ReadModule(System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters);
    public static Colossal.Mono.Cecil.ModuleDefinition ReadModule(System.IO.Stream stream);
    public static Colossal.Mono.Cecil.ModuleDefinition ReadModule(System.IO.Stream stream, Colossal.Mono.Cecil.ReaderParameters parameters);
    private static Colossal.Mono.Cecil.ModuleDefinition ReadModule(Colossal.Mono.Disposable<System.IO.Stream> stream, System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters);
    public System.Void ReadSymbols();
    public System.Void ReadSymbols(Colossal.Mono.Cecil.Cil.ISymbolReader reader);
    public System.Void ReadSymbols(Colossal.Mono.Cecil.Cil.ISymbolReader reader, System.Boolean throwIfSymbolsAreNotMaching);
    internal Colossal.Mono.Cecil.FieldDefinition Resolve(Colossal.Mono.Cecil.FieldReference field);
    internal Colossal.Mono.Cecil.MethodDefinition Resolve(Colossal.Mono.Cecil.MethodReference method);
    internal Colossal.Mono.Cecil.TypeDefinition Resolve(Colossal.Mono.Cecil.TypeReference type);
    public System.Boolean TryGetTypeReference(System.String fullName, Colossal.Mono.Cecil.TypeReference& type);
    public System.Boolean TryGetTypeReference(System.String scope, System.String fullName, Colossal.Mono.Cecil.TypeReference& type);
    public System.Void Write(System.String fileName);
    public System.Void Write(System.String fileName, Colossal.Mono.Cecil.WriterParameters parameters);
    public System.Void Write();
    public System.Void Write(Colossal.Mono.Cecil.WriterParameters parameters);
    public System.Void Write(System.IO.Stream stream);
    public System.Void Write(System.IO.Stream stream, Colossal.Mono.Cecil.WriterParameters parameters);
}
```


## Fields

- `internal Colossal.Mono.Cecil.PE.Image Image`  

```csharp
internal Colossal.Mono.Cecil.PE.Image Image;
```

- `internal Colossal.Mono.Cecil.MetadataSystem MetadataSystem`  

```csharp
internal Colossal.Mono.Cecil.MetadataSystem MetadataSystem;
```

- `internal Colossal.Mono.Cecil.ReadingMode ReadingMode`  

```csharp
internal Colossal.Mono.Cecil.ReadingMode ReadingMode;
```

- `internal Colossal.Mono.Cecil.Cil.ISymbolReaderProvider SymbolReaderProvider`  

```csharp
internal Colossal.Mono.Cecil.Cil.ISymbolReaderProvider SymbolReaderProvider;
```

- `internal Colossal.Mono.Cecil.Cil.ISymbolReader symbol_reader`  

```csharp
internal Colossal.Mono.Cecil.Cil.ISymbolReader symbol_reader;
```

- `internal Colossal.Mono.Disposable<Colossal.Mono.Cecil.IAssemblyResolver> assembly_resolver`  

```csharp
internal Colossal.Mono.Disposable<Colossal.Mono.Cecil.IAssemblyResolver> assembly_resolver;
```

- `internal Colossal.Mono.Cecil.IMetadataResolver metadata_resolver`  

```csharp
internal Colossal.Mono.Cecil.IMetadataResolver metadata_resolver;
```

- `internal Colossal.Mono.Cecil.TypeSystem type_system`  

```csharp
internal Colossal.Mono.Cecil.TypeSystem type_system;
```

- `internal readonly Colossal.Mono.Cecil.MetadataReader reader`  

```csharp
internal readonly Colossal.Mono.Cecil.MetadataReader reader;
```

- `private readonly System.String file_name`  

```csharp
private readonly System.String file_name;
```

- `internal System.String runtime_version`  

```csharp
internal System.String runtime_version;
```

- `internal Colossal.Mono.Cecil.ModuleKind kind`  

```csharp
internal Colossal.Mono.Cecil.ModuleKind kind;
```

- `private Colossal.Mono.Cecil.WindowsRuntimeProjections projections`  

```csharp
private Colossal.Mono.Cecil.WindowsRuntimeProjections projections;
```

- `private Colossal.Mono.Cecil.MetadataKind metadata_kind`  

```csharp
private Colossal.Mono.Cecil.MetadataKind metadata_kind;
```

- `private Colossal.Mono.Cecil.TargetRuntime runtime`  

```csharp
private Colossal.Mono.Cecil.TargetRuntime runtime;
```

- `private Colossal.Mono.Cecil.TargetArchitecture architecture`  

```csharp
private Colossal.Mono.Cecil.TargetArchitecture architecture;
```

- `private Colossal.Mono.Cecil.ModuleAttributes attributes`  

```csharp
private Colossal.Mono.Cecil.ModuleAttributes attributes;
```

- `private Colossal.Mono.Cecil.ModuleCharacteristics characteristics`  

```csharp
private Colossal.Mono.Cecil.ModuleCharacteristics characteristics;
```

- `private System.Guid mvid`  

```csharp
private System.Guid mvid;
```

- `internal System.UInt16 linker_version`  

```csharp
internal System.UInt16 linker_version;
```

- `internal System.UInt16 subsystem_major`  

```csharp
internal System.UInt16 subsystem_major;
```

- `internal System.UInt16 subsystem_minor`  

```csharp
internal System.UInt16 subsystem_minor;
```

- `internal System.UInt32 timestamp`  

```csharp
internal System.UInt32 timestamp;
```

- `internal Colossal.Mono.Cecil.AssemblyDefinition assembly`  

```csharp
internal Colossal.Mono.Cecil.AssemblyDefinition assembly;
```

- `private Colossal.Mono.Cecil.MethodDefinition entry_point`  

```csharp
private Colossal.Mono.Cecil.MethodDefinition entry_point;
```

- `private System.Boolean entry_point_set`  

```csharp
private System.Boolean entry_point_set;
```

- `internal Colossal.Mono.Cecil.IReflectionImporter reflection_importer`  

```csharp
internal Colossal.Mono.Cecil.IReflectionImporter reflection_importer;
```

- `internal Colossal.Mono.Cecil.IMetadataImporter metadata_importer`  

```csharp
internal Colossal.Mono.Cecil.IMetadataImporter metadata_importer;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.AssemblyNameReference> references`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.AssemblyNameReference> references;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleReference> modules`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleReference> modules;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Resource> resources`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Resource> resources;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ExportedType> exported_types`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ExportedType> exported_types;
```

- `private Colossal.Mono.Cecil.TypeDefinitionCollection types`  

```csharp
private Colossal.Mono.Cecil.TypeDefinitionCollection types;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> custom_infos`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> custom_infos;
```

- `internal Colossal.Mono.Cecil.MetadataBuilder metadata_builder`  

```csharp
internal Colossal.Mono.Cecil.MetadataBuilder metadata_builder;
```

- `private readonly System.Object module_lock`  

```csharp
private readonly System.Object module_lock;
```


## Properties

- `public System.Boolean IsMain { get }`  

```csharp
public System.Boolean IsMain { get; }
```

- `public Colossal.Mono.Cecil.ModuleKind Kind { get; set }`  

```csharp
public Colossal.Mono.Cecil.ModuleKind Kind { get; set; }
```

- `public Colossal.Mono.Cecil.MetadataKind MetadataKind { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataKind MetadataKind { get; set; }
```

- `internal Colossal.Mono.Cecil.WindowsRuntimeProjections Projections { internal get }`  

```csharp
internal Colossal.Mono.Cecil.WindowsRuntimeProjections Projections { internal get; }
```

- `public Colossal.Mono.Cecil.TargetRuntime Runtime { get; set }`  

```csharp
public Colossal.Mono.Cecil.TargetRuntime Runtime { get; set; }
```

- `public System.String RuntimeVersion { get; set }`  

```csharp
public System.String RuntimeVersion { get; set; }
```

- `public Colossal.Mono.Cecil.TargetArchitecture Architecture { get; set }`  

```csharp
public Colossal.Mono.Cecil.TargetArchitecture Architecture { get; set; }
```

- `public Colossal.Mono.Cecil.ModuleAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.ModuleAttributes Attributes { get; set; }
```

- `public Colossal.Mono.Cecil.ModuleCharacteristics Characteristics { get; set }`  

```csharp
public Colossal.Mono.Cecil.ModuleCharacteristics Characteristics { get; set; }
```

- `public System.String FullyQualifiedName { get }`  

```csharp
public System.String FullyQualifiedName { get; }
```

- `public System.String FileName { get }`  

```csharp
public System.String FileName { get; }
```

- `public System.Guid Mvid { get; set }`  

```csharp
public System.Guid Mvid { get; set; }
```

- `internal System.Boolean HasImage { internal get }`  

```csharp
internal System.Boolean HasImage { internal get; }
```

- `public System.Boolean HasSymbols { get }`  

```csharp
public System.Boolean HasSymbols { get; }
```

- `public Colossal.Mono.Cecil.Cil.ISymbolReader SymbolReader { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReader SymbolReader { get; }
```

- `public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get }`  

```csharp
public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get; }
```

- `public Colossal.Mono.Cecil.AssemblyDefinition Assembly { get }`  

```csharp
public Colossal.Mono.Cecil.AssemblyDefinition Assembly { get; }
```

- `internal Colossal.Mono.Cecil.IReflectionImporter ReflectionImporter { internal get }`  

```csharp
internal Colossal.Mono.Cecil.IReflectionImporter ReflectionImporter { internal get; }
```

- `internal Colossal.Mono.Cecil.IMetadataImporter MetadataImporter { internal get }`  

```csharp
internal Colossal.Mono.Cecil.IMetadataImporter MetadataImporter { internal get; }
```

- `public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get }`  

```csharp
public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; }
```

- `public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get }`  

```csharp
public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get; }
```

- `public Colossal.Mono.Cecil.TypeSystem TypeSystem { get }`  

```csharp
public Colossal.Mono.Cecil.TypeSystem TypeSystem { get; }
```

- `public System.Boolean HasAssemblyReferences { get }`  

```csharp
public System.Boolean HasAssemblyReferences { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.AssemblyNameReference> AssemblyReferences { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.AssemblyNameReference> AssemblyReferences { get; }
```

- `public System.Boolean HasModuleReferences { get }`  

```csharp
public System.Boolean HasModuleReferences { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleReference> ModuleReferences { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleReference> ModuleReferences { get; }
```

- `public System.Boolean HasResources { get }`  

```csharp
public System.Boolean HasResources { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Resource> Resources { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Resource> Resources { get; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public System.Boolean HasTypes { get }`  

```csharp
public System.Boolean HasTypes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> Types { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> Types { get; }
```

- `public System.Boolean HasExportedTypes { get }`  

```csharp
public System.Boolean HasExportedTypes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ExportedType> ExportedTypes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ExportedType> ExportedTypes { get; }
```

- `public Colossal.Mono.Cecil.MethodDefinition EntryPoint { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition EntryPoint { get; set; }
```

- `public System.Boolean HasCustomDebugInformations { get }`  

```csharp
public System.Boolean HasCustomDebugInformations { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> CustomDebugInformations { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> CustomDebugInformations { get; }
```

- `internal System.Object SyncRoot { internal get }`  

```csharp
internal System.Object SyncRoot { internal get; }
```

- `public System.Boolean HasDebugHeader { get }`  

```csharp
public System.Boolean HasDebugHeader { get; }
```


## Constructors

- `internal ModuleDefinition()`  

```csharp
internal ModuleDefinition();
```

- `internal ModuleDefinition(Colossal.Mono.Cecil.PE.Image image)`  

```csharp
internal ModuleDefinition(Colossal.Mono.Cecil.PE.Image image);
```


## Methods

- `private static CheckContext(Colossal.Mono.Cecil.IGenericParameterProvider context, Colossal.Mono.Cecil.ModuleDefinition module) : System.Void`  

```csharp
private static System.Void CheckContext(Colossal.Mono.Cecil.IGenericParameterProvider context, Colossal.Mono.Cecil.ModuleDefinition module);
```

- `private static CreateAssemblyName(System.String name) : Colossal.Mono.Cecil.AssemblyNameDefinition`  

```csharp
private static Colossal.Mono.Cecil.AssemblyNameDefinition CreateAssemblyName(System.String name);
```

- `public static CreateModule(System.String name, Colossal.Mono.Cecil.ModuleKind kind) : Colossal.Mono.Cecil.ModuleDefinition`  

```csharp
public static Colossal.Mono.Cecil.ModuleDefinition CreateModule(System.String name, Colossal.Mono.Cecil.ModuleKind kind);
```

- `public static CreateModule(System.String name, Colossal.Mono.Cecil.ModuleParameters parameters) : Colossal.Mono.Cecil.ModuleDefinition`  

```csharp
public static Colossal.Mono.Cecil.ModuleDefinition CreateModule(System.String name, Colossal.Mono.Cecil.ModuleParameters parameters);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetCustomAttributes() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.CustomAttribute>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.CustomAttribute> GetCustomAttributes();
```

- `public GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  

```csharp
public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
```

- `private static GetFileStream(System.String fileName, System.IO.FileMode mode, System.IO.FileAccess access, System.IO.FileShare share) : System.IO.Stream`  

```csharp
private static System.IO.Stream GetFileStream(System.String fileName, System.IO.FileMode mode, System.IO.FileAccess access, System.IO.FileShare share);
```

- `public GetMemberReferences() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.MemberReference>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.MemberReference> GetMemberReferences();
```

- `private GetNestedType(System.String fullname) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
private Colossal.Mono.Cecil.TypeDefinition GetNestedType(System.String fullname);
```

- `public GetType(System.String fullName, System.Boolean runtimeName) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference GetType(System.String fullName, System.Boolean runtimeName);
```

- `public GetType(System.String fullName) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public Colossal.Mono.Cecil.TypeDefinition GetType(System.String fullName);
```

- `public GetType(System.String namespace, System.String name) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public Colossal.Mono.Cecil.TypeDefinition GetType(System.String namespace, System.String name);
```

- `private GetTypeReference(System.String scope, System.String fullname) : Colossal.Mono.Cecil.TypeReference`  

```csharp
private Colossal.Mono.Cecil.TypeReference GetTypeReference(System.String scope, System.String fullname);
```

- `public GetTypeReferences() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeReference>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeReference> GetTypeReferences();
```

- `public GetTypes() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeDefinition>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeDefinition> GetTypes();
```

- `private static GetTypes(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> types) : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeDefinition>`  

```csharp
private static System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeDefinition> GetTypes(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> types);
```

- `public HasTypeReference(System.String fullName) : System.Boolean`  

```csharp
public System.Boolean HasTypeReference(System.String fullName);
```

- `public HasTypeReference(System.String scope, System.String fullName) : System.Boolean`  

```csharp
public System.Boolean HasTypeReference(System.String scope, System.String fullName);
```

- `public ImmediateRead() : System.Void`  

```csharp
public System.Void ImmediateRead();
```

- `public Import(System.Type type) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference Import(System.Type type);
```

- `public Import(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference Import(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public Import(System.Reflection.FieldInfo field) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public Colossal.Mono.Cecil.FieldReference Import(System.Reflection.FieldInfo field);
```

- `public Import(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public Colossal.Mono.Cecil.FieldReference Import(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public Import(System.Reflection.MethodBase method) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public Colossal.Mono.Cecil.MethodReference Import(System.Reflection.MethodBase method);
```

- `public Import(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public Colossal.Mono.Cecil.MethodReference Import(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public Import(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference Import(Colossal.Mono.Cecil.TypeReference type);
```

- `public Import(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference Import(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public Import(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public Colossal.Mono.Cecil.FieldReference Import(Colossal.Mono.Cecil.FieldReference field);
```

- `public Import(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public Colossal.Mono.Cecil.FieldReference Import(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public Import(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public Colossal.Mono.Cecil.MethodReference Import(Colossal.Mono.Cecil.MethodReference method);
```

- `public Import(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public Colossal.Mono.Cecil.MethodReference Import(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public ImportReference(System.Type type) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference ImportReference(System.Type type);
```

- `public ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public ImportReference(System.Reflection.FieldInfo field) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public Colossal.Mono.Cecil.FieldReference ImportReference(System.Reflection.FieldInfo field);
```

- `public ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public Colossal.Mono.Cecil.FieldReference ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public ImportReference(System.Reflection.MethodBase method) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public Colossal.Mono.Cecil.MethodReference ImportReference(System.Reflection.MethodBase method);
```

- `public ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public Colossal.Mono.Cecil.MethodReference ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public ImportReference(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference ImportReference(Colossal.Mono.Cecil.TypeReference type);
```

- `public ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public Colossal.Mono.Cecil.TypeReference ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public ImportReference(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public Colossal.Mono.Cecil.FieldReference ImportReference(Colossal.Mono.Cecil.FieldReference field);
```

- `public ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public Colossal.Mono.Cecil.FieldReference ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public ImportReference(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public Colossal.Mono.Cecil.MethodReference ImportReference(Colossal.Mono.Cecil.MethodReference method);
```

- `public ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public Colossal.Mono.Cecil.MethodReference ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public LookupToken(System.Int32 token) : Colossal.Mono.Cecil.IMetadataTokenProvider`  

```csharp
public Colossal.Mono.Cecil.IMetadataTokenProvider LookupToken(System.Int32 token);
```

- `public LookupToken(Colossal.Mono.Cecil.MetadataToken token) : Colossal.Mono.Cecil.IMetadataTokenProvider`  

```csharp
public Colossal.Mono.Cecil.IMetadataTokenProvider LookupToken(Colossal.Mono.Cecil.MetadataToken token);
```

- `internal Read<TItem>(TItem item, System.Action<TItem, Colossal.Mono.Cecil.MetadataReader> read) : System.Void`  

```csharp
internal System.Void Read<TItem>(TItem item, System.Action<TItem, Colossal.Mono.Cecil.MetadataReader> read);
```

- `internal Read<TItem, TRet>(TItem item, System.Func<TItem, Colossal.Mono.Cecil.MetadataReader, TRet> read) : TRet`  

```csharp
internal TRet Read<TItem, TRet>(TItem item, System.Func<TItem, Colossal.Mono.Cecil.MetadataReader, TRet> read);
```

- `internal Read<TItem, TRet>(TRet& variable, TItem item, System.Func<TItem, Colossal.Mono.Cecil.MetadataReader, TRet> read) : TRet`  

```csharp
internal TRet Read<TItem, TRet>(TRet& variable, TItem item, System.Func<TItem, Colossal.Mono.Cecil.MetadataReader, TRet> read);
```

- `public static ReadModule(System.String fileName) : Colossal.Mono.Cecil.ModuleDefinition`  

```csharp
public static Colossal.Mono.Cecil.ModuleDefinition ReadModule(System.String fileName);
```

- `public static ReadModule(System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.ModuleDefinition`  

```csharp
public static Colossal.Mono.Cecil.ModuleDefinition ReadModule(System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `public static ReadModule(System.IO.Stream stream) : Colossal.Mono.Cecil.ModuleDefinition`  

```csharp
public static Colossal.Mono.Cecil.ModuleDefinition ReadModule(System.IO.Stream stream);
```

- `public static ReadModule(System.IO.Stream stream, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.ModuleDefinition`  

```csharp
public static Colossal.Mono.Cecil.ModuleDefinition ReadModule(System.IO.Stream stream, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `private static ReadModule(Colossal.Mono.Disposable<System.IO.Stream> stream, System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.ModuleDefinition`  

```csharp
private static Colossal.Mono.Cecil.ModuleDefinition ReadModule(Colossal.Mono.Disposable<System.IO.Stream> stream, System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `public ReadSymbols() : System.Void`  

```csharp
public System.Void ReadSymbols();
```

- `public ReadSymbols(Colossal.Mono.Cecil.Cil.ISymbolReader reader) : System.Void`  

```csharp
public System.Void ReadSymbols(Colossal.Mono.Cecil.Cil.ISymbolReader reader);
```

- `public ReadSymbols(Colossal.Mono.Cecil.Cil.ISymbolReader reader, System.Boolean throwIfSymbolsAreNotMaching) : System.Void`  

```csharp
public System.Void ReadSymbols(Colossal.Mono.Cecil.Cil.ISymbolReader reader, System.Boolean throwIfSymbolsAreNotMaching);
```

- `internal Resolve(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldDefinition`  

```csharp
internal Colossal.Mono.Cecil.FieldDefinition Resolve(Colossal.Mono.Cecil.FieldReference field);
```

- `internal Resolve(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
internal Colossal.Mono.Cecil.MethodDefinition Resolve(Colossal.Mono.Cecil.MethodReference method);
```

- `internal Resolve(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
internal Colossal.Mono.Cecil.TypeDefinition Resolve(Colossal.Mono.Cecil.TypeReference type);
```

- `public TryGetTypeReference(System.String fullName, Colossal.Mono.Cecil.TypeReference& type) : System.Boolean`  

```csharp
public System.Boolean TryGetTypeReference(System.String fullName, Colossal.Mono.Cecil.TypeReference& type);
```

- `public TryGetTypeReference(System.String scope, System.String fullName, Colossal.Mono.Cecil.TypeReference& type) : System.Boolean`  

```csharp
public System.Boolean TryGetTypeReference(System.String scope, System.String fullName, Colossal.Mono.Cecil.TypeReference& type);
```

- `public Write(System.String fileName) : System.Void`  

```csharp
public System.Void Write(System.String fileName);
```

- `public Write(System.String fileName, Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  

```csharp
public System.Void Write(System.String fileName, Colossal.Mono.Cecil.WriterParameters parameters);
```

- `public Write() : System.Void`  

```csharp
public System.Void Write();
```

- `public Write(Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  

```csharp
public System.Void Write(Colossal.Mono.Cecil.WriterParameters parameters);
```

- `public Write(System.IO.Stream stream) : System.Void`  

```csharp
public System.Void Write(System.IO.Stream stream);
```

- `public Write(System.IO.Stream stream, Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  

```csharp
public System.Void Write(System.IO.Stream stream, Colossal.Mono.Cecil.WriterParameters parameters);
```


## Nested types

- `Colossal.Mono.Cecil.ModuleDefinition+<>c`  
- `Colossal.Mono.Cecil.ModuleDefinition+<GetTypes>d__134`  

