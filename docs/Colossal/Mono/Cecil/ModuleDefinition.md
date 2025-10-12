# Colossal.Mono.Cecil.ModuleDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.ModuleReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataScope`, `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `System.IDisposable`  

## Fields

- `internal Colossal.Mono.Cecil.PE.Image Image`  
- `internal Colossal.Mono.Cecil.MetadataSystem MetadataSystem`  
- `internal Colossal.Mono.Cecil.ReadingMode ReadingMode`  
- `internal Colossal.Mono.Cecil.Cil.ISymbolReaderProvider SymbolReaderProvider`  
- `internal Colossal.Mono.Cecil.Cil.ISymbolReader symbol_reader`  
- `internal Colossal.Mono.Disposable<Colossal.Mono.Cecil.IAssemblyResolver> assembly_resolver`  
- `internal Colossal.Mono.Cecil.IMetadataResolver metadata_resolver`  
- `internal Colossal.Mono.Cecil.TypeSystem type_system`  
- `internal readonly Colossal.Mono.Cecil.MetadataReader reader`  
- `private readonly System.String file_name`  
- `internal System.String runtime_version`  
- `internal Colossal.Mono.Cecil.ModuleKind kind`  
- `private Colossal.Mono.Cecil.WindowsRuntimeProjections projections`  
- `private Colossal.Mono.Cecil.MetadataKind metadata_kind`  
- `private Colossal.Mono.Cecil.TargetRuntime runtime`  
- `private Colossal.Mono.Cecil.TargetArchitecture architecture`  
- `private Colossal.Mono.Cecil.ModuleAttributes attributes`  
- `private Colossal.Mono.Cecil.ModuleCharacteristics characteristics`  
- `private System.Guid mvid`  
- `internal System.UInt16 linker_version`  
- `internal System.UInt16 subsystem_major`  
- `internal System.UInt16 subsystem_minor`  
- `internal System.UInt32 timestamp`  
- `internal Colossal.Mono.Cecil.AssemblyDefinition assembly`  
- `private Colossal.Mono.Cecil.MethodDefinition entry_point`  
- `private System.Boolean entry_point_set`  
- `internal Colossal.Mono.Cecil.IReflectionImporter reflection_importer`  
- `internal Colossal.Mono.Cecil.IMetadataImporter metadata_importer`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.AssemblyNameReference> references`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleReference> modules`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Resource> resources`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ExportedType> exported_types`  
- `private Colossal.Mono.Cecil.TypeDefinitionCollection types`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> custom_infos`  
- `internal Colossal.Mono.Cecil.MetadataBuilder metadata_builder`  
- `private readonly System.Object module_lock`  

## Properties

- `public System.Boolean IsMain { get }`  
- `public Colossal.Mono.Cecil.ModuleKind Kind { get; set }`  
- `public Colossal.Mono.Cecil.MetadataKind MetadataKind { get; set }`  
- `internal Colossal.Mono.Cecil.WindowsRuntimeProjections Projections { internal get }`  
- `public Colossal.Mono.Cecil.TargetRuntime Runtime { get; set }`  
- `public System.String RuntimeVersion { get; set }`  
- `public Colossal.Mono.Cecil.TargetArchitecture Architecture { get; set }`  
- `public Colossal.Mono.Cecil.ModuleAttributes Attributes { get; set }`  
- `public Colossal.Mono.Cecil.ModuleCharacteristics Characteristics { get; set }`  
- `public System.String FullyQualifiedName { get }`  
- `public System.String FileName { get }`  
- `public System.Guid Mvid { get; set }`  
- `internal System.Boolean HasImage { internal get }`  
- `public System.Boolean HasSymbols { get }`  
- `public Colossal.Mono.Cecil.Cil.ISymbolReader SymbolReader { get }`  
- `public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get }`  
- `public Colossal.Mono.Cecil.AssemblyDefinition Assembly { get }`  
- `internal Colossal.Mono.Cecil.IReflectionImporter ReflectionImporter { internal get }`  
- `internal Colossal.Mono.Cecil.IMetadataImporter MetadataImporter { internal get }`  
- `public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get }`  
- `public Colossal.Mono.Cecil.IMetadataResolver MetadataResolver { get }`  
- `public Colossal.Mono.Cecil.TypeSystem TypeSystem { get }`  
- `public System.Boolean HasAssemblyReferences { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.AssemblyNameReference> AssemblyReferences { get }`  
- `public System.Boolean HasModuleReferences { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleReference> ModuleReferences { get }`  
- `public System.Boolean HasResources { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Resource> Resources { get }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public System.Boolean HasTypes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> Types { get }`  
- `public System.Boolean HasExportedTypes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ExportedType> ExportedTypes { get }`  
- `public Colossal.Mono.Cecil.MethodDefinition EntryPoint { get; set }`  
- `public System.Boolean HasCustomDebugInformations { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> CustomDebugInformations { get }`  
- `internal System.Object SyncRoot { internal get }`  
- `public System.Boolean HasDebugHeader { get }`  

## Constructors

- `internal ModuleDefinition()`  
- `internal ModuleDefinition(Colossal.Mono.Cecil.PE.Image image)`  

## Methods

- `private static CheckContext(Colossal.Mono.Cecil.IGenericParameterProvider context, Colossal.Mono.Cecil.ModuleDefinition module) : System.Void`  
- `private static CreateAssemblyName(System.String name) : Colossal.Mono.Cecil.AssemblyNameDefinition`  
- `public static CreateModule(System.String name, Colossal.Mono.Cecil.ModuleKind kind) : Colossal.Mono.Cecil.ModuleDefinition`  
- `public static CreateModule(System.String name, Colossal.Mono.Cecil.ModuleParameters parameters) : Colossal.Mono.Cecil.ModuleDefinition`  
- `public Dispose() : System.Void`  
- `public GetCustomAttributes() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.CustomAttribute>`  
- `public GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  
- `private static GetFileStream(System.String fileName, System.IO.FileMode mode, System.IO.FileAccess access, System.IO.FileShare share) : System.IO.Stream`  
- `public GetMemberReferences() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.MemberReference>`  
- `private GetNestedType(System.String fullname) : Colossal.Mono.Cecil.TypeDefinition`  
- `public GetType(System.String fullName, System.Boolean runtimeName) : Colossal.Mono.Cecil.TypeReference`  
- `public GetType(System.String fullName) : Colossal.Mono.Cecil.TypeDefinition`  
- `public GetType(System.String namespace, System.String name) : Colossal.Mono.Cecil.TypeDefinition`  
- `private GetTypeReference(System.String scope, System.String fullname) : Colossal.Mono.Cecil.TypeReference`  
- `public GetTypeReferences() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeReference>`  
- `public GetTypes() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeDefinition>`  
- `private static GetTypes(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> types) : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.TypeDefinition>`  
- `public HasTypeReference(System.String fullName) : System.Boolean`  
- `public HasTypeReference(System.String scope, System.String fullName) : System.Boolean`  
- `public ImmediateRead() : System.Void`  
- `public Import(System.Type type) : Colossal.Mono.Cecil.TypeReference`  
- `public Import(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  
- `public Import(System.Reflection.FieldInfo field) : Colossal.Mono.Cecil.FieldReference`  
- `public Import(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  
- `public Import(System.Reflection.MethodBase method) : Colossal.Mono.Cecil.MethodReference`  
- `public Import(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  
- `public Import(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeReference`  
- `public Import(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  
- `public Import(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldReference`  
- `public Import(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  
- `public Import(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodReference`  
- `public Import(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  
- `public ImportReference(System.Type type) : Colossal.Mono.Cecil.TypeReference`  
- `public ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  
- `public ImportReference(System.Reflection.FieldInfo field) : Colossal.Mono.Cecil.FieldReference`  
- `public ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  
- `public ImportReference(System.Reflection.MethodBase method) : Colossal.Mono.Cecil.MethodReference`  
- `public ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  
- `public ImportReference(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeReference`  
- `public ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  
- `public ImportReference(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldReference`  
- `public ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  
- `public ImportReference(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodReference`  
- `public ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  
- `public LookupToken(System.Int32 token) : Colossal.Mono.Cecil.IMetadataTokenProvider`  
- `public LookupToken(Colossal.Mono.Cecil.MetadataToken token) : Colossal.Mono.Cecil.IMetadataTokenProvider`  
- `internal Read<TItem>(TItem item, System.Action<TItem, Colossal.Mono.Cecil.MetadataReader> read) : System.Void`  
- `internal Read<TItem, TRet>(TItem item, System.Func<TItem, Colossal.Mono.Cecil.MetadataReader, TRet> read) : TRet`  
- `internal Read<TItem, TRet>(TRet& variable, TItem item, System.Func<TItem, Colossal.Mono.Cecil.MetadataReader, TRet> read) : TRet`  
- `public static ReadModule(System.String fileName) : Colossal.Mono.Cecil.ModuleDefinition`  
- `public static ReadModule(System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.ModuleDefinition`  
- `public static ReadModule(System.IO.Stream stream) : Colossal.Mono.Cecil.ModuleDefinition`  
- `public static ReadModule(System.IO.Stream stream, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.ModuleDefinition`  
- `private static ReadModule(Colossal.Mono.Disposable<System.IO.Stream> stream, System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.ModuleDefinition`  
- `public ReadSymbols() : System.Void`  
- `public ReadSymbols(Colossal.Mono.Cecil.Cil.ISymbolReader reader) : System.Void`  
- `public ReadSymbols(Colossal.Mono.Cecil.Cil.ISymbolReader reader, System.Boolean throwIfSymbolsAreNotMaching) : System.Void`  
- `internal Resolve(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldDefinition`  
- `internal Resolve(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodDefinition`  
- `internal Resolve(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeDefinition`  
- `public TryGetTypeReference(System.String fullName, Colossal.Mono.Cecil.TypeReference& type) : System.Boolean`  
- `public TryGetTypeReference(System.String scope, System.String fullName, Colossal.Mono.Cecil.TypeReference& type) : System.Boolean`  
- `public Write(System.String fileName) : System.Void`  
- `public Write(System.String fileName, Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  
- `public Write() : System.Void`  
- `public Write(Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  
- `public Write(System.IO.Stream stream) : System.Void`  
- `public Write(System.IO.Stream stream, Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.ModuleDefinition+<>c`  
- `Colossal.Mono.Cecil.ModuleDefinition+<GetTypes>d__134`  

