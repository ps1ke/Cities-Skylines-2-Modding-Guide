# Colossal.IO.AssetDatabase.ExecutableAsset+ExecutableResolver

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.BaseAssemblyResolver`  
**Implements:** `Colossal.Mono.Cecil.IAssemblyResolver`, `System.IDisposable`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.Dictionary<System.Version, Colossal.Mono.Cecil.AssemblyDefinition>> m_Cache`  
- `private static System.String[] m_SearchDirectories`  

## Constructors

- `public ExecutableResolver()`  

## Methods

- `public RegisterAssembly(Colossal.Mono.Cecil.AssemblyDefinition assembly) : System.Void`  
- `public RegisterAsset(Colossal.IO.AssetDatabase.ExecutableAsset asset) : System.Void`  
- `public virtual Resolve(Colossal.Mono.Cecil.AssemblyNameReference toResolve) : Colossal.Mono.Cecil.AssemblyDefinition`  

## Nested types

- `Colossal.IO.AssetDatabase.ExecutableAsset+ExecutableResolver+<>c`  

