# Colossal.Mono.Cecil.BaseAssemblyResolver

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IAssemblyResolver`, `System.IDisposable`  

## Code

```csharp
public abstract class BaseAssemblyResolver : Colossal.Mono.Cecil.IAssemblyResolver, System.IDisposable
{
    private readonly Colossal.Mono.Collections.Generic.Collection<System.String> directories;
    private Colossal.Mono.Collections.Generic.Collection<System.String> gac_paths;
    private Colossal.Mono.Cecil.AssemblyResolveEventHandler ResolveFailure;
    private static readonly System.Boolean on_mono;

    protected BaseAssemblyResolver();

    public System.Void AddSearchDirectory(System.String directory);
    public System.Void Dispose();
    protected virtual System.Void Dispose(System.Boolean disposing);
    private Colossal.Mono.Cecil.AssemblyDefinition GetAssembly(System.String file, Colossal.Mono.Cecil.ReaderParameters parameters);
    private static System.String GetAssemblyFile(Colossal.Mono.Cecil.AssemblyNameReference reference, System.String prefix, System.String gac);
    private Colossal.Mono.Cecil.AssemblyDefinition GetAssemblyInGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters);
    private Colossal.Mono.Cecil.AssemblyDefinition GetAssemblyInMonoGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters);
    private Colossal.Mono.Cecil.AssemblyDefinition GetAssemblyInNetGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters);
    private Colossal.Mono.Cecil.AssemblyDefinition GetCorlib(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters);
    private static System.String GetCurrentMonoGac();
    private static Colossal.Mono.Collections.Generic.Collection<System.String> GetDefaultMonoGacPaths();
    private static Colossal.Mono.Collections.Generic.Collection<System.String> GetGacPaths();
    public System.String[] GetSearchDirectories();
    private static System.Boolean IsZero(System.Version version);
    public System.Void RemoveSearchDirectory(System.String directory);
    public virtual Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name);
    public virtual Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name, Colossal.Mono.Cecil.ReaderParameters parameters);
    protected virtual Colossal.Mono.Cecil.AssemblyDefinition SearchDirectory(Colossal.Mono.Cecil.AssemblyNameReference name, System.Collections.Generic.IEnumerable<System.String> directories, Colossal.Mono.Cecil.ReaderParameters parameters);
}
```


## Fields

- `private readonly Colossal.Mono.Collections.Generic.Collection<System.String> directories`  

```csharp
private readonly Colossal.Mono.Collections.Generic.Collection<System.String> directories;
```

- `private Colossal.Mono.Collections.Generic.Collection<System.String> gac_paths`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<System.String> gac_paths;
```

- `private Colossal.Mono.Cecil.AssemblyResolveEventHandler ResolveFailure`  

```csharp
private Colossal.Mono.Cecil.AssemblyResolveEventHandler ResolveFailure;
```

- `private static readonly System.Boolean on_mono`  

```csharp
private static readonly System.Boolean on_mono;
```


## Constructors

- `protected BaseAssemblyResolver()`  

```csharp
protected BaseAssemblyResolver();
```


## Methods

- `public AddSearchDirectory(System.String directory) : System.Void`  

```csharp
public System.Void AddSearchDirectory(System.String directory);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `protected virtual Dispose(System.Boolean disposing) : System.Void`  

```csharp
protected virtual System.Void Dispose(System.Boolean disposing);
```

- `private GetAssembly(System.String file, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
private Colossal.Mono.Cecil.AssemblyDefinition GetAssembly(System.String file, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `private static GetAssemblyFile(Colossal.Mono.Cecil.AssemblyNameReference reference, System.String prefix, System.String gac) : System.String`  

```csharp
private static System.String GetAssemblyFile(Colossal.Mono.Cecil.AssemblyNameReference reference, System.String prefix, System.String gac);
```

- `private GetAssemblyInGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
private Colossal.Mono.Cecil.AssemblyDefinition GetAssemblyInGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `private GetAssemblyInMonoGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
private Colossal.Mono.Cecil.AssemblyDefinition GetAssemblyInMonoGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `private GetAssemblyInNetGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
private Colossal.Mono.Cecil.AssemblyDefinition GetAssemblyInNetGac(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `private GetCorlib(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
private Colossal.Mono.Cecil.AssemblyDefinition GetCorlib(Colossal.Mono.Cecil.AssemblyNameReference reference, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `private static GetCurrentMonoGac() : System.String`  

```csharp
private static System.String GetCurrentMonoGac();
```

- `private static GetDefaultMonoGacPaths() : Colossal.Mono.Collections.Generic.Collection<System.String>`  

```csharp
private static Colossal.Mono.Collections.Generic.Collection<System.String> GetDefaultMonoGacPaths();
```

- `private static GetGacPaths() : Colossal.Mono.Collections.Generic.Collection<System.String>`  

```csharp
private static Colossal.Mono.Collections.Generic.Collection<System.String> GetGacPaths();
```

- `public GetSearchDirectories() : System.String[]`  

```csharp
public System.String[] GetSearchDirectories();
```

- `private static IsZero(System.Version version) : System.Boolean`  

```csharp
private static System.Boolean IsZero(System.Version version);
```

- `public RemoveSearchDirectory(System.String directory) : System.Void`  

```csharp
public System.Void RemoveSearchDirectory(System.String directory);
```

- `public virtual Resolve(Colossal.Mono.Cecil.AssemblyNameReference name) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name);
```

- `public virtual Resolve(Colossal.Mono.Cecil.AssemblyNameReference name, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name, Colossal.Mono.Cecil.ReaderParameters parameters);
```

- `protected virtual SearchDirectory(Colossal.Mono.Cecil.AssemblyNameReference name, System.Collections.Generic.IEnumerable<System.String> directories, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
protected virtual Colossal.Mono.Cecil.AssemblyDefinition SearchDirectory(Colossal.Mono.Cecil.AssemblyNameReference name, System.Collections.Generic.IEnumerable<System.String> directories, Colossal.Mono.Cecil.ReaderParameters parameters);
```


## Events

- `ResolveFailure` : `Colossal.Mono.Cecil.AssemblyResolveEventHandler`  

```csharp
public event Colossal.Mono.Cecil.AssemblyResolveEventHandler ResolveFailure;
```


