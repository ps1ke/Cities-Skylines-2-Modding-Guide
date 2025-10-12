# Colossal.Mono.CompilerServices.SymbolWriter.SymbolWriterImpl

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Diagnostics.SymbolStore.ISymbolWriter`  

## Fields

- `private Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter msw`  
- `private System.Int32 nextLocalIndex`  
- `private System.Int32 currentToken`  
- `private System.String methodName`  
- `private System.Collections.Stack namespaceStack`  
- `private System.Boolean methodOpened`  
- `private System.Collections.Hashtable documents`  
- `private System.Reflection.Emit.ModuleBuilder mb`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.SymbolWriterImpl+GetGuidFunc get_guid_func`  

## Constructors

- `public SymbolWriterImpl(System.Reflection.Emit.ModuleBuilder mb)`  

## Methods

- `public Close() : System.Void`  
- `public CloseMethod() : System.Void`  
- `public CloseNamespace() : System.Void`  
- `public CloseScope(System.Int32 endOffset) : System.Void`  
- `public DefineDocument(System.String url, System.Guid language, System.Guid languageVendor, System.Guid documentType) : System.Diagnostics.SymbolStore.ISymbolDocumentWriter`  
- `public DefineField(System.Diagnostics.SymbolStore.SymbolToken parent, System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3) : System.Void`  
- `public DefineGlobalVariable(System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3) : System.Void`  
- `public DefineLocalVariable(System.String name, System.Reflection.FieldAttributes attributes, System.Byte[] signature, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3, System.Int32 startOffset, System.Int32 endOffset) : System.Void`  
- `public DefineParameter(System.String name, System.Reflection.ParameterAttributes attributes, System.Int32 sequence, System.Diagnostics.SymbolStore.SymAddressKind addrKind, System.Int32 addr1, System.Int32 addr2, System.Int32 addr3) : System.Void`  
- `public DefineSequencePoints(System.Diagnostics.SymbolStore.ISymbolDocumentWriter document, System.Int32[] offsets, System.Int32[] lines, System.Int32[] columns, System.Int32[] endLines, System.Int32[] endColumns) : System.Void`  
- `private GetCurrentNamespace(System.Diagnostics.SymbolStore.ISymbolDocumentWriter doc) : System.Int32`  
- `public Initialize(System.IntPtr emitter, System.String filename, System.Boolean fFullBuild) : System.Void`  
- `public OpenMethod(System.Diagnostics.SymbolStore.SymbolToken method) : System.Void`  
- `public OpenNamespace(System.String name) : System.Void`  
- `public OpenScope(System.Int32 startOffset) : System.Int32`  
- `public SetMethodSourceRange(System.Diagnostics.SymbolStore.ISymbolDocumentWriter startDoc, System.Int32 startLine, System.Int32 startColumn, System.Diagnostics.SymbolStore.ISymbolDocumentWriter endDoc, System.Int32 endLine, System.Int32 endColumn) : System.Void`  
- `public SetScopeRange(System.Int32 scopeID, System.Int32 startOffset, System.Int32 endOffset) : System.Void`  
- `public SetSymAttribute(System.Diagnostics.SymbolStore.SymbolToken parent, System.String name, System.Byte[] data) : System.Void`  
- `public SetUnderlyingWriter(System.IntPtr underlyingWriter) : System.Void`  
- `public SetUserEntryPoint(System.Diagnostics.SymbolStore.SymbolToken entryMethod) : System.Void`  
- `public UsingNamespace(System.String fullName) : System.Void`  

## Nested types

- `Colossal.Mono.CompilerServices.SymbolWriter.SymbolWriterImpl+GetGuidFunc`  

