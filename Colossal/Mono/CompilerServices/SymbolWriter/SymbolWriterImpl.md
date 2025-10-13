# Colossal.Mono.CompilerServices.SymbolWriter.SymbolWriterImpl

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Diagnostics.SymbolStore.ISymbolWriter`  

## Code

```csharp
public class SymbolWriterImpl : System.Diagnostics.SymbolStore.ISymbolWriter
{
    private Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter msw;
    private System.Int32 nextLocalIndex;
    private System.Int32 currentToken;
    private System.String methodName;
    private System.Collections.Stack namespaceStack;
    private System.Boolean methodOpened;
    private System.Collections.Hashtable documents;
    private System.Reflection.Emit.ModuleBuilder mb;
    private Colossal.Mono.CompilerServices.SymbolWriter.SymbolWriterImpl+GetGuidFunc get_guid_func;

    public SymbolWriterImpl(System.Reflection.Emit.ModuleBuilder mb);

    public System.Void Close();
    public System.Void CloseMethod();
    public System.Void CloseNamespace();
    public System.Void CloseScope(System.Int32 endOffset);
    public System.Diagnostics.SymbolStore.ISymbolDocumentWriter DefineDocument(System.String url, System.Guid language, System.Guid languageVendor, System.Guid documentType);
    public System.Void DefineField(System.Diagnostics.SymbolStore.SymbolToken parent, System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3);
    public System.Void DefineGlobalVariable(System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3);
    public System.Void DefineLocalVariable(System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3, System.Int32 startOffset, System.Int32 endOffset);
    public System.Void DefineParameter(System.String name, System.Reflection.ParameterAttributes attributes, System.Int32 sequence, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3);
    public System.Void DefineSequencePoints(System.Diagnostics.SymbolStore.ISymbolDocumentWriter document, System.Int32[] offsets, System.Int32[] lines, System.Int32[] columns, System.Int32[] endLines, System.Int32[] endColumns);
    private System.Int32 GetCurrentNamespace(System.Diagnostics.SymbolStore.ISymbolDocumentWriter doc);
    public System.Void Initialize(System.IntPtr emitter, System.String filename, System.Boolean fFullBuild);
    public System.Void OpenMethod(System.Diagnostics.SymbolStore.SymbolToken method);
    public System.Void OpenNamespace(System.String name);
    public System.Int32 OpenScope(System.Int32 startOffset);
    public System.Void SetMethodSourceRange(System.Diagnostics.SymbolStore.ISymbolDocumentWriter startDoc, System.Int32 startLine, System.Int32 startColumn, System.Diagnostics.SymbolStore.ISymbolDocumentWriter endDoc, System.Int32 endLine, System.Int32 endColumn);
    public System.Void SetScopeRange(System.Int32 scopeID, System.Int32 startOffset, System.Int32 endOffset);
    public System.Void SetSymAttribute(System.Diagnostics.SymbolStore.SymbolToken parent, System.String name, System.Byte[] data);
    public System.Void SetUnderlyingWriter(System.IntPtr underlyingWriter);
    public System.Void SetUserEntryPoint(System.Diagnostics.SymbolStore.SymbolToken entryMethod);
    public System.Void UsingNamespace(System.String fullName);
}
```


## Fields

- `private Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter msw`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter msw;
```

- `private System.Int32 nextLocalIndex`  

```csharp
private System.Int32 nextLocalIndex;
```

- `private System.Int32 currentToken`  

```csharp
private System.Int32 currentToken;
```

- `private System.String methodName`  

```csharp
private System.String methodName;
```

- `private System.Collections.Stack namespaceStack`  

```csharp
private System.Collections.Stack namespaceStack;
```

- `private System.Boolean methodOpened`  

```csharp
private System.Boolean methodOpened;
```

- `private System.Collections.Hashtable documents`  

```csharp
private System.Collections.Hashtable documents;
```

- `private System.Reflection.Emit.ModuleBuilder mb`  

```csharp
private System.Reflection.Emit.ModuleBuilder mb;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.SymbolWriterImpl+GetGuidFunc get_guid_func`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.SymbolWriterImpl+GetGuidFunc get_guid_func;
```


## Constructors

- `public SymbolWriterImpl(System.Reflection.Emit.ModuleBuilder mb)`  

```csharp
public SymbolWriterImpl(System.Reflection.Emit.ModuleBuilder mb);
```


## Methods

- `public Close() : System.Void`  

```csharp
public System.Void Close();
```

- `public CloseMethod() : System.Void`  

```csharp
public System.Void CloseMethod();
```

- `public CloseNamespace() : System.Void`  

```csharp
public System.Void CloseNamespace();
```

- `public CloseScope(System.Int32 endOffset) : System.Void`  

```csharp
public System.Void CloseScope(System.Int32 endOffset);
```

- `public DefineDocument(System.String url, System.Guid language, System.Guid languageVendor, System.Guid documentType) : System.Diagnostics.SymbolStore.ISymbolDocumentWriter`  

```csharp
public System.Diagnostics.SymbolStore.ISymbolDocumentWriter DefineDocument(System.String url, System.Guid language, System.Guid languageVendor, System.Guid documentType);
```

- `public DefineField(System.Diagnostics.SymbolStore.SymbolToken parent, System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3) : System.Void`  

```csharp
public System.Void DefineField(System.Diagnostics.SymbolStore.SymbolToken parent, System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3);
```

- `public DefineGlobalVariable(System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3) : System.Void`  

```csharp
public System.Void DefineGlobalVariable(System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3);
```

- `public DefineLocalVariable(System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3, System.Int32 startOffset, System.Int32 endOffset) : System.Void`  

```csharp
public System.Void DefineLocalVariable(System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3, System.Int32 startOffset, System.Int32 endOffset);
```

- `public DefineParameter(System.String name, System.Reflection.ParameterAttributes attributes, System.Int32 sequence, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3) : System.Void`  

```csharp
public System.Void DefineParameter(System.String name, System.Reflection.ParameterAttributes attributes, System.Int32 sequence, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3);
```

- `public DefineSequencePoints(System.Diagnostics.SymbolStore.ISymbolDocumentWriter document, System.Int32[] offsets, System.Int32[] lines, System.Int32[] columns, System.Int32[] endLines, System.Int32[] endColumns) : System.Void`  

```csharp
public System.Void DefineSequencePoints(System.Diagnostics.SymbolStore.ISymbolDocumentWriter document, System.Int32[] offsets, System.Int32[] lines, System.Int32[] columns, System.Int32[] endLines, System.Int32[] endColumns);
```

- `private GetCurrentNamespace(System.Diagnostics.SymbolStore.ISymbolDocumentWriter doc) : System.Int32`  

```csharp
private System.Int32 GetCurrentNamespace(System.Diagnostics.SymbolStore.ISymbolDocumentWriter doc);
```

- `public Initialize(System.IntPtr emitter, System.String filename, System.Boolean fFullBuild) : System.Void`  

```csharp
public System.Void Initialize(System.IntPtr emitter, System.String filename, System.Boolean fFullBuild);
```

- `public OpenMethod(System.Diagnostics.SymbolStore.SymbolToken method) : System.Void`  

```csharp
public System.Void OpenMethod(System.Diagnostics.SymbolStore.SymbolToken method);
```

- `public OpenNamespace(System.String name) : System.Void`  

```csharp
public System.Void OpenNamespace(System.String name);
```

- `public OpenScope(System.Int32 startOffset) : System.Int32`  

```csharp
public System.Int32 OpenScope(System.Int32 startOffset);
```

- `public SetMethodSourceRange(System.Diagnostics.SymbolStore.ISymbolDocumentWriter startDoc, System.Int32 startLine, System.Int32 startColumn, System.Diagnostics.SymbolStore.ISymbolDocumentWriter endDoc, System.Int32 endLine, System.Int32 endColumn) : System.Void`  

```csharp
public System.Void SetMethodSourceRange(System.Diagnostics.SymbolStore.ISymbolDocumentWriter startDoc, System.Int32 startLine, System.Int32 startColumn, System.Diagnostics.SymbolStore.ISymbolDocumentWriter endDoc, System.Int32 endLine, System.Int32 endColumn);
```

- `public SetScopeRange(System.Int32 scopeID, System.Int32 startOffset, System.Int32 endOffset) : System.Void`  

```csharp
public System.Void SetScopeRange(System.Int32 scopeID, System.Int32 startOffset, System.Int32 endOffset);
```

- `public SetSymAttribute(System.Diagnostics.SymbolStore.SymbolToken parent, System.String name, System.Byte[] data) : System.Void`  

```csharp
public System.Void SetSymAttribute(System.Diagnostics.SymbolStore.SymbolToken parent, System.String name, System.Byte[] data);
```

- `public SetUnderlyingWriter(System.IntPtr underlyingWriter) : System.Void`  

```csharp
public System.Void SetUnderlyingWriter(System.IntPtr underlyingWriter);
```

- `public SetUserEntryPoint(System.Diagnostics.SymbolStore.SymbolToken entryMethod) : System.Void`  

```csharp
public System.Void SetUserEntryPoint(System.Diagnostics.SymbolStore.SymbolToken entryMethod);
```

- `public UsingNamespace(System.String fullName) : System.Void`  

```csharp
public System.Void UsingNamespace(System.String fullName);
```


## Nested types

- `Colossal.Mono.CompilerServices.SymbolWriter.SymbolWriterImpl+GetGuidFunc`  

