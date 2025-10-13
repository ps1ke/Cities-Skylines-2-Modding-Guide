# Colossal.Mono.Cecil.AssemblyDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.ISecurityDeclarationProvider`, `System.IDisposable`  

## Code

```csharp
public sealed class AssemblyDefinition : Colossal.Mono.Cecil.ICustomAttributeProvider, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.ISecurityDeclarationProvider, System.IDisposable
{
    private Colossal.Mono.Cecil.AssemblyNameDefinition name;
    internal Colossal.Mono.Cecil.ModuleDefinition main_module;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleDefinition> modules;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations;

    public Colossal.Mono.Cecil.AssemblyNameDefinition Name { get; set; }
    public System.String FullName { get; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleDefinition> Modules { get; }
    public Colossal.Mono.Cecil.ModuleDefinition MainModule { get; }
    public Colossal.Mono.Cecil.MethodDefinition EntryPoint { get; set; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public System.Boolean HasSecurityDeclarations { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get; }

    internal AssemblyDefinition();

    public static Colossal.Mono.Cecil.AssemblyDefinition CreateAssembly(Colossal.Mono.Cecil.AssemblyNameDefinition assemblyName, System.String moduleName, Colossal.Mono.Cecil.ModuleKind kind);
    public static Colossal.Mono.Cecil.AssemblyDefinition CreateAssembly(Colossal.Mono.Cecil.AssemblyNameDefinition assemblyName, System.String moduleName, Colossal.Mono.Cecil.ModuleParameters parameters);
    public System.Void Dispose();
    public static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(System.String fileName);
    public static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters);
    public static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(System.IO.Stream stream);
    public static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(System.IO.Stream stream, Colossal.Mono.Cecil.ReaderParameters parameters);
    private static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(Colossal.Mono.Cecil.ModuleDefinition module);
    public virtual System.String ToString();
    public System.Void Write(System.String fileName);
    public System.Void Write(System.String fileName, Colossal.Mono.Cecil.WriterParameters parameters);
    public System.Void Write();
    public System.Void Write(Colossal.Mono.Cecil.WriterParameters parameters);
    public System.Void Write(System.IO.Stream stream);
    public System.Void Write(System.IO.Stream stream, Colossal.Mono.Cecil.WriterParameters parameters);
}
```


## Fields

- `private Colossal.Mono.Cecil.AssemblyNameDefinition name`  

```csharp
private Colossal.Mono.Cecil.AssemblyNameDefinition name;
```

- `internal Colossal.Mono.Cecil.ModuleDefinition main_module`  

```csharp
internal Colossal.Mono.Cecil.ModuleDefinition main_module;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleDefinition> modules`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleDefinition> modules;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations;
```


## Properties

- `public Colossal.Mono.Cecil.AssemblyNameDefinition Name { get; set }`  

```csharp
public Colossal.Mono.Cecil.AssemblyNameDefinition Name { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleDefinition> Modules { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ModuleDefinition> Modules { get; }
```

- `public Colossal.Mono.Cecil.ModuleDefinition MainModule { get }`  

```csharp
public Colossal.Mono.Cecil.ModuleDefinition MainModule { get; }
```

- `public Colossal.Mono.Cecil.MethodDefinition EntryPoint { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition EntryPoint { get; set; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public System.Boolean HasSecurityDeclarations { get }`  

```csharp
public System.Boolean HasSecurityDeclarations { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get; }
```


## Constructors

- `internal AssemblyDefinition()`  

```csharp
internal AssemblyDefinition();
```


## Methods

- `public static CreateAssembly(Colossal.Mono.Cecil.AssemblyNameDefinition assemblyName, System.String moduleName, Colossal.Mono.Cecil.ModuleKind kind) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public static Colossal.Mono.Cecil.AssemblyDefinition CreateAssembly(Colossal.Mono.Cecil.AssemblyNameDefinition assemblyName, System.String moduleName, Colossal.Mono.Cecil.ModuleKind kind);
```

- `public static CreateAssembly(Colossal.Mono.Cecil.AssemblyNameDefinition assemblyName, System.String moduleName, Colossal.Mono.Cecil.ModuleParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public static Colossal.Mono.Cecil.AssemblyDefinition CreateAssembly(Colossal.Mono.Cecil.AssemblyNameDefinition assemblyName, System.String moduleName, Colossal.Mono.Cecil.ModuleParameters parameters);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public static ReadAssembly(System.String fileName) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(System.String fileName);
```

- `public static ReadAssembly(System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(System.String fileName, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `public static ReadAssembly(System.IO.Stream stream) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(System.IO.Stream stream);
```

- `public static ReadAssembly(System.IO.Stream stream, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(System.IO.Stream stream, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `private static ReadAssembly(Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
private static Colossal.Mono.Cecil.AssemblyDefinition ReadAssembly(Colossal.Mono.Cecil.ModuleDefinition module);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
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

- `Colossal.Mono.Cecil.AssemblyDefinition+<>c`  

