# Colossal.Mono.Cecil.FieldDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.FieldReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMemberDefinition`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IConstantProvider`, `Colossal.Mono.Cecil.IMarshalInfoProvider`  

## Fields

- `private System.UInt16 attributes`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  
- `private System.Int32 offset`  
- `internal System.Int32 rva`  
- `private System.Byte[] initial_value`  
- `private System.Object constant`  
- `private Colossal.Mono.Cecil.MarshalInfo marshal_info`  

## Properties

- `public System.Boolean HasLayoutInfo { get }`  
- `public System.Int32 Offset { get; set }`  
- `internal Colossal.Mono.Cecil.FieldDefinitionProjection WindowsRuntimeProjection { internal get; internal set }`  
- `public System.Int32 RVA { get }`  
- `public System.Byte[] InitialValue { get; set }`  
- `public Colossal.Mono.Cecil.FieldAttributes Attributes { get; set }`  
- `public System.Boolean HasConstant { get; set }`  
- `public System.Object Constant { get; set }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public System.Boolean HasMarshalInfo { get }`  
- `public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set }`  
- `public System.Boolean IsCompilerControlled { get; set }`  
- `public System.Boolean IsPrivate { get; set }`  
- `public System.Boolean IsFamilyAndAssembly { get; set }`  
- `public System.Boolean IsAssembly { get; set }`  
- `public System.Boolean IsFamily { get; set }`  
- `public System.Boolean IsFamilyOrAssembly { get; set }`  
- `public System.Boolean IsPublic { get; set }`  
- `public System.Boolean IsStatic { get; set }`  
- `public System.Boolean IsInitOnly { get; set }`  
- `public System.Boolean IsLiteral { get; set }`  
- `public System.Boolean IsNotSerialized { get; set }`  
- `public System.Boolean IsSpecialName { get; set }`  
- `public System.Boolean IsPInvokeImpl { get; set }`  
- `public System.Boolean IsRuntimeSpecialName { get; set }`  
- `public System.Boolean HasDefault { get; set }`  
- `public System.Boolean HasFieldRVA { get; set }`  
- `public System.Boolean IsDefinition { get }`  
- `public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set }`  

## Constructors

- `public FieldDefinition(System.String name, Colossal.Mono.Cecil.FieldAttributes attributes, Colossal.Mono.Cecil.TypeReference fieldType)`  

## Methods

- `public virtual Resolve() : Colossal.Mono.Cecil.FieldDefinition`  
- `private ResolveLayout() : System.Void`  
- `private ResolveRVA() : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.FieldDefinition+<>c`  

