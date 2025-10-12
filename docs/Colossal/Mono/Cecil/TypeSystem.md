# Colossal.Mono.Cecil.TypeSystem

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Fields

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  
- `private Colossal.Mono.Cecil.TypeReference type_object`  
- `private Colossal.Mono.Cecil.TypeReference type_void`  
- `private Colossal.Mono.Cecil.TypeReference type_bool`  
- `private Colossal.Mono.Cecil.TypeReference type_char`  
- `private Colossal.Mono.Cecil.TypeReference type_sbyte`  
- `private Colossal.Mono.Cecil.TypeReference type_byte`  
- `private Colossal.Mono.Cecil.TypeReference type_int16`  
- `private Colossal.Mono.Cecil.TypeReference type_uint16`  
- `private Colossal.Mono.Cecil.TypeReference type_int32`  
- `private Colossal.Mono.Cecil.TypeReference type_uint32`  
- `private Colossal.Mono.Cecil.TypeReference type_int64`  
- `private Colossal.Mono.Cecil.TypeReference type_uint64`  
- `private Colossal.Mono.Cecil.TypeReference type_single`  
- `private Colossal.Mono.Cecil.TypeReference type_double`  
- `private Colossal.Mono.Cecil.TypeReference type_intptr`  
- `private Colossal.Mono.Cecil.TypeReference type_uintptr`  
- `private Colossal.Mono.Cecil.TypeReference type_string`  
- `private Colossal.Mono.Cecil.TypeReference type_typedref`  

## Properties

- `public Colossal.Mono.Cecil.IMetadataScope Corlib { get }`  
- `public Colossal.Mono.Cecil.IMetadataScope CoreLibrary { get }`  
- `public Colossal.Mono.Cecil.TypeReference Object { get }`  
- `public Colossal.Mono.Cecil.TypeReference Void { get }`  
- `public Colossal.Mono.Cecil.TypeReference Boolean { get }`  
- `public Colossal.Mono.Cecil.TypeReference Char { get }`  
- `public Colossal.Mono.Cecil.TypeReference SByte { get }`  
- `public Colossal.Mono.Cecil.TypeReference Byte { get }`  
- `public Colossal.Mono.Cecil.TypeReference Int16 { get }`  
- `public Colossal.Mono.Cecil.TypeReference UInt16 { get }`  
- `public Colossal.Mono.Cecil.TypeReference Int32 { get }`  
- `public Colossal.Mono.Cecil.TypeReference UInt32 { get }`  
- `public Colossal.Mono.Cecil.TypeReference Int64 { get }`  
- `public Colossal.Mono.Cecil.TypeReference UInt64 { get }`  
- `public Colossal.Mono.Cecil.TypeReference Single { get }`  
- `public Colossal.Mono.Cecil.TypeReference Double { get }`  
- `public Colossal.Mono.Cecil.TypeReference IntPtr { get }`  
- `public Colossal.Mono.Cecil.TypeReference UIntPtr { get }`  
- `public Colossal.Mono.Cecil.TypeReference String { get }`  
- `public Colossal.Mono.Cecil.TypeReference TypedReference { get }`  

## Constructors

- `private TypeSystem(Colossal.Mono.Cecil.ModuleDefinition module)`  

## Methods

- `internal static CreateTypeSystem(Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.TypeSystem`  
- `private LookupSystemType(Colossal.Mono.Cecil.TypeReference& reference, System.String name, Colossal.Mono.Cecil.Metadata.ElementType element_type) : Colossal.Mono.Cecil.TypeReference`  
- `private LookupSystemValueType(Colossal.Mono.Cecil.TypeReference& typeRef, System.String name, Colossal.Mono.Cecil.Metadata.ElementType element_type) : Colossal.Mono.Cecil.TypeReference`  
- `internal abstract LookupType(System.String namespace, System.String name) : Colossal.Mono.Cecil.TypeReference`  

## Nested types

- `Colossal.Mono.Cecil.TypeSystem+CoreTypeSystem`  
- `Colossal.Mono.Cecil.TypeSystem+CommonTypeSystem`  

