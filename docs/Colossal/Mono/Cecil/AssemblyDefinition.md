# Colossal.Mono.Cecil.AssemblyDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.ISecurityDeclarationProvider`, `System.IDisposable`  

## Fields

- `private Colossal.Mono.Cecil.AssemblyNameDefinition name`  
- `internal Colossal.Mono.Cecil.ModuleDefinition main_module`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleDefinition> modules`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations`  

## Properties

- `public Colossal.Mono.Cecil.AssemblyNameDefinition Name { get; set }`  
- `public System.String FullName { get }`  
- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleDefinition> Modules { get }`  
- `public Colossal.Mono.Cecil.ModuleDefinition MainModule { get }`  
- `public Colossal.Mono.Cecil.MethodDefinition EntryPoint { get; set }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public System.Boolean HasSecurityDeclarations { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get }`  

## Constructors

- `internal AssemblyDefinition()`  

## Methods

- `public static CreateAssembly(Colossal.Mono.Cecil.AssemblyNameDefinition assemblyName, System.String moduleName, Colossal.Mono.Cecil.ModuleKind kind) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `public static CreateAssembly(Colossal.Mono.Cecil.AssemblyNameDefinition assemblyName, System.String moduleName, Colossal.Mono.Cecil.ModuleParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `public Dispose() : System.Void`  
- `public static ReadAssembly(System.String fileName) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `public static ReadAssembly(System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `public static ReadAssembly(System.IO.Stream stream) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `public static ReadAssembly(System.IO.Stream stream, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `private static ReadAssembly(Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `public virtual ToString() : System.String`  
- `public Write(System.String fileName) : System.Void`  
- `public Write(System.String fileName, Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  
- `public Write() : System.Void`  
- `public Write(Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  
- `public Write(System.IO.Stream stream) : System.Void`  
- `public Write(System.IO.Stream stream, Colossal.Mono.Cecil.WriterParameters parameters) : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.AssemblyDefinition+<>c`  

