# Colossal.Mono.Cecil.Cil.AsyncMethodBodyDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.CustomDebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class AsyncMethodBodyDebugInformation : Colossal.Mono.Cecil.Cil.CustomDebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    internal Colossal.Mono.Cecil.Cil.InstructionOffset catch_handler;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> yields;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> resumes;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> resume_methods;
    public static System.Guid KindIdentifier;

    public Colossal.Mono.Cecil.Cil.InstructionOffset CatchHandler { get; set; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> Yields { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> Resumes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> ResumeMethods { get; }
    public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }

    internal AsyncMethodBodyDebugInformation(System.Int32 catchHandler);
    public AsyncMethodBodyDebugInformation(Colossal.Mono.Cecil.Cil.Instruction catchHandler);
    public AsyncMethodBodyDebugInformation();

}
```


## Fields

- `internal Colossal.Mono.Cecil.Cil.InstructionOffset catch_handler`  

```csharp
internal Colossal.Mono.Cecil.Cil.InstructionOffset catch_handler;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> yields`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> yields;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> resumes`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> resumes;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> resume_methods`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> resume_methods;
```

- `public static System.Guid KindIdentifier`  

```csharp
public static System.Guid KindIdentifier;
```


## Properties

- `public Colossal.Mono.Cecil.Cil.InstructionOffset CatchHandler { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.InstructionOffset CatchHandler { get; set; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> Yields { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> Yields { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> Resumes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> Resumes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> ResumeMethods { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> ResumeMethods { get; }
```

- `public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }
```


## Constructors

- `internal AsyncMethodBodyDebugInformation(System.Int32 catchHandler)`  

```csharp
internal AsyncMethodBodyDebugInformation(System.Int32 catchHandler);
```

- `public AsyncMethodBodyDebugInformation(Colossal.Mono.Cecil.Cil.Instruction catchHandler)`  

```csharp
public AsyncMethodBodyDebugInformation(Colossal.Mono.Cecil.Cil.Instruction catchHandler);
```

- `public AsyncMethodBodyDebugInformation()`  

```csharp
public AsyncMethodBodyDebugInformation();
```


