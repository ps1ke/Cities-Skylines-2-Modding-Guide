# Colossal.Mono.Cecil.DefaultReflectionImporter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IReflectionImporter`  

## Fields

- `protected readonly Colossal.Mono.Cecil.ModuleDefinition module`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.Mono.Cecil.Metadata.ElementType> type_etype_mapping`  

## Constructors

- `public DefaultReflectionImporter(Colossal.Mono.Cecil.ModuleDefinition module)`  

## Methods

- `private static HasCallingConvention(System.Reflection.MethodBase method, System.Reflection.CallingConventions conventions) : System.Boolean`  
- `private static ImportElementType(System.Type type) : Colossal.Mono.Cecil.Metadata.ElementType`  
- `private ImportField(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.FieldReference`  
- `private ImportGenericInstance(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  
- `private static ImportGenericParameter(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  
- `private static ImportGenericParameters(Colossal.Mono.Cecil.IGenericParameterProvider provider, System.Type[] arguments) : System.Void`  
- `private ImportMethod(System.Reflection.MethodBase method, Colossal.Mono.Cecil.ImportGenericContext context, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind) : Colossal.Mono.Cecil.MethodReference`  
- `private ImportMethodSpecification(System.Reflection.MethodBase method, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.MethodReference`  
- `private static ImportOpenGenericMethod(System.Reflection.MethodBase method, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind) : System.Boolean`  
- `private static ImportOpenGenericType(System.Type type, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind) : System.Boolean`  
- `public virtual ImportReference(System.Reflection.AssemblyName name) : Colossal.Mono.Cecil.AssemblyNameReference`  
- `public virtual ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  
- `public virtual ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  
- `public virtual ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  
- `protected virtual ImportScope(System.Type type) : Colossal.Mono.Cecil.IMetadataScope`  
- `protected ImportScope(System.Reflection.Assembly assembly) : Colossal.Mono.Cecil.AssemblyNameReference`  
- `private ImportType(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  
- `private ImportType(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind) : Colossal.Mono.Cecil.TypeReference`  
- `private ImportTypeSpecification(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  
- `private static IsGenericInstance(System.Type type) : System.Boolean`  
- `private static IsMethodSpecification(System.Reflection.MethodBase method) : System.Boolean`  
- `private static IsNestedType(System.Type type) : System.Boolean`  
- `private static IsTypeSpecification(System.Type type) : System.Boolean`  
- `private static NormalizeMethodName(System.Reflection.MethodBase method) : System.String`  
- `private static NormalizeTypeFullName(System.Type type) : System.String`  
- `private static ResolveFieldDefinition(System.Reflection.FieldInfo field) : System.Reflection.FieldInfo`  
- `private static ResolveMethodDefinition(System.Reflection.MethodBase method) : System.Reflection.MethodBase`  
- `private TryGetAssemblyNameReference(System.Reflection.AssemblyName name, Colossal.Mono.Cecil.AssemblyNameReference& assembly_reference) : System.Boolean`  

## Nested types

- `Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind`  

