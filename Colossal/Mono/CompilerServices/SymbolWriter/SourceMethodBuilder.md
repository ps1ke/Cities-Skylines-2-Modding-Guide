# Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class SourceMethodBuilder
{
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry> _locals;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry> _blocks;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable> _scope_vars;
    private System.Collections.Generic.Stack<Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry> _block_stack;
    private readonly System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry> method_lines;
    private readonly Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit _comp_unit;
    private readonly System.Int32 ns_id;
    private readonly Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method;

    public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] Blocks { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry CurrentBlock { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] Locals { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit SourceFile { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] ScopeVariables { get; }

    public SourceMethodBuilder(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit comp_unit);
    public SourceMethodBuilder(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit comp_unit, System.Int32 ns_id, Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method);

    public System.Void AddLocal(System.Int32 index, System.String name);
    public System.Void AddScopeVariable(System.Int32 scope, System.Int32 index);
    public System.Void DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file);
    public System.Void DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, System.Int32 token);
    public System.Void EndBlock(System.Int32 end_offset);
    public System.Void MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Boolean is_hidden);
    public System.Void MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Int32 end_line, System.Int32 end_column, System.Boolean is_hidden);
    public System.Void StartBlock(Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset);
    public System.Void StartBlock(Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset, System.Int32 scopeIndex);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry> _locals`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry> _locals;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry> _blocks`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry> _blocks;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable> _scope_vars`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable> _scope_vars;
```

- `private System.Collections.Generic.Stack<Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry> _block_stack`  

```csharp
private System.Collections.Generic.Stack<Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry> _block_stack;
```

- `private readonly System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry> method_lines`  

```csharp
private readonly System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry> method_lines;
```

- `private readonly Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit _comp_unit`  

```csharp
private readonly Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit _comp_unit;
```

- `private readonly System.Int32 ns_id`  

```csharp
private readonly System.Int32 ns_id;
```

- `private readonly Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method`  

```csharp
private readonly Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method;
```


## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] Blocks { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] Blocks { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry CurrentBlock { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry CurrentBlock { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] Locals { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] Locals { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit SourceFile { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit SourceFile { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] ScopeVariables { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] ScopeVariables { get; }
```


## Constructors

- `public SourceMethodBuilder(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit comp_unit)`  

```csharp
public SourceMethodBuilder(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit comp_unit);
```

- `public SourceMethodBuilder(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit comp_unit, System.Int32 ns_id, Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method)`  

```csharp
public SourceMethodBuilder(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit comp_unit, System.Int32 ns_id, Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method);
```


## Methods

- `public AddLocal(System.Int32 index, System.String name) : System.Void`  

```csharp
public System.Void AddLocal(System.Int32 index, System.String name);
```

- `public AddScopeVariable(System.Int32 scope, System.Int32 index) : System.Void`  

```csharp
public System.Void AddScopeVariable(System.Int32 scope, System.Int32 index);
```

- `public DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file) : System.Void`  

```csharp
public System.Void DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file);
```

- `public DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, System.Int32 token) : System.Void`  

```csharp
public System.Void DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, System.Int32 token);
```

- `public EndBlock(System.Int32 end_offset) : System.Void`  

```csharp
public System.Void EndBlock(System.Int32 end_offset);
```

- `public MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Boolean is_hidden) : System.Void`  

```csharp
public System.Void MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Boolean is_hidden);
```

- `public MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Int32 end_line, System.Int32 end_column, System.Boolean is_hidden) : System.Void`  

```csharp
public System.Void MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Int32 end_line, System.Int32 end_column, System.Boolean is_hidden);
```

- `public StartBlock(Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset) : System.Void`  

```csharp
public System.Void StartBlock(Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset);
```

- `public StartBlock(Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset, System.Int32 scopeIndex) : System.Void`  

```csharp
public System.Void StartBlock(Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset, System.Int32 scopeIndex);
```


