# Colossal.Mono.Cecil.BaseAssemblyResolver

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IAssemblyResolver`, `System.IDisposable`  

## Fields

- `private readonly Colossal.Mono.Collections.Generic.Collection<System.String> directories`  
- `private Colossal.Mono.Collections.Generic.Collection<System.String> gac_paths`  
- `private Colossal.Mono.Cecil.AssemblyResolveEventHandler ResolveFailure`  
- `private static readonly System.Boolean on_mono`  

## Constructors

- `protected BaseAssemblyResolver()`  

## Methods

- `public AddSearchDirectory(System.String directory) : System.Void`  
- `public Dispose() : System.Void`  
- `protected virtual Dispose(System.Boolean disposing) : System.Void`  
- `private GetAssembly(System.String file, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `private static GetAssemblyFile(Colossal.Mono.Cecil.AssemblyNameReference reference, System.String prefix, System.String gac) : System.String`  
- `private GetAssemblyInGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `private GetAssemblyInMonoGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `private GetAssemblyInNetGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `private GetCorlib(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `private static GetCurrentMonoGac() : System.String`  
- `private static GetDefaultMonoGacPaths() : Colossal.Mono.Collections.Generic.Collection<System.String>`  
- `private static GetGacPaths() : Colossal.Mono.Collections.Generic.Collection<System.String>`  
- `public GetSearchDirectories() : System.String[]`  
- `private static IsZero(System.Version version) : System.Boolean`  
- `public RemoveSearchDirectory(System.String directory) : System.Void`  
- `public virtual Resolve(Colossal.Mono.Cecil.AssemblyNameReference name) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `public virtual Resolve(Colossal.Mono.Cecil.AssemblyNameReference name, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  
- `protected virtual SearchDirectory(Colossal.Mono.Cecil.AssemblyNameReference name, System.Collections.Generic.IEnumerable<System.String> directories, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

## Events

- `ResolveFailure` : `Colossal.Mono.Cecil.AssemblyResolveEventHandler`  

