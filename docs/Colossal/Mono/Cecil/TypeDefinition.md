# Colossal.Mono.Cecil.TypeDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IMemberDefinition`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.ISecurityDeclarationProvider`  

## Fields

- `private System.UInt32 attributes`  
- `private Colossal.Mono.Cecil.TypeReference base_type`  
- `internal Colossal.Mono.Cecil.Range fields_range`  
- `internal Colossal.Mono.Cecil.Range methods_range`  
- `private System.Int16 packing_size`  
- `private System.Int32 class_size`  
- `private Colossal.Mono.Cecil.InterfaceImplementationCollection interfaces`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> nested_types`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> methods`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> fields`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.EventDefinition> events`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.PropertyDefinition> properties`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations`  

## Properties

- `public Colossal.Mono.Cecil.TypeAttributes Attributes { get; set }`  
- `public Colossal.Mono.Cecil.TypeReference BaseType { get; set }`  
- `public System.String Name { get; set }`  
- `public System.Boolean HasLayoutInfo { get }`  
- `public System.Int16 PackingSize { get; set }`  
- `public System.Int32 ClassSize { get; set }`  
- `public System.Boolean HasInterfaces { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.InterfaceImplementation> Interfaces { get }`  
- `public System.Boolean HasNestedTypes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> NestedTypes { get }`  
- `public System.Boolean HasMethods { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> Methods { get }`  
- `public System.Boolean HasFields { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> Fields { get }`  
- `public System.Boolean HasEvents { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.EventDefinition> Events { get }`  
- `public System.Boolean HasProperties { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.PropertyDefinition> Properties { get }`  
- `public System.Boolean HasSecurityDeclarations { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public System.Boolean HasGenericParameters { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get }`  
- `public System.Boolean IsNotPublic { get; set }`  
- `public System.Boolean IsPublic { get; set }`  
- `public System.Boolean IsNestedPublic { get; set }`  
- `public System.Boolean IsNestedPrivate { get; set }`  
- `public System.Boolean IsNestedFamily { get; set }`  
- `public System.Boolean IsNestedAssembly { get; set }`  
- `public System.Boolean IsNestedFamilyAndAssembly { get; set }`  
- `public System.Boolean IsNestedFamilyOrAssembly { get; set }`  
- `public System.Boolean IsAutoLayout { get; set }`  
- `public System.Boolean IsSequentialLayout { get; set }`  
- `public System.Boolean IsExplicitLayout { get; set }`  
- `public System.Boolean IsClass { get; set }`  
- `public System.Boolean IsInterface { get; set }`  
- `public System.Boolean IsAbstract { get; set }`  
- `public System.Boolean IsSealed { get; set }`  
- `public System.Boolean IsSpecialName { get; set }`  
- `public System.Boolean IsImport { get; set }`  
- `public System.Boolean IsSerializable { get; set }`  
- `public System.Boolean IsWindowsRuntime { get; set }`  
- `public System.Boolean IsAnsiClass { get; set }`  
- `public System.Boolean IsUnicodeClass { get; set }`  
- `public System.Boolean IsAutoClass { get; set }`  
- `public System.Boolean IsBeforeFieldInit { get; set }`  
- `public System.Boolean IsRuntimeSpecialName { get; set }`  
- `public System.Boolean HasSecurity { get; set }`  
- `public System.Boolean IsEnum { get }`  
- `public System.Boolean IsValueType { get; set }`  
- `public System.Boolean IsPrimitive { get }`  
- `public Colossal.Mono.Cecil.MetadataType MetadataType { get }`  
- `public System.Boolean IsDefinition { get }`  
- `public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set }`  
- `internal Colossal.Mono.Cecil.TypeDefinitionProjection WindowsRuntimeProjection { internal get; internal set }`  

## Constructors

- `public TypeDefinition(System.String namespace, System.String name, Colossal.Mono.Cecil.TypeAttributes attributes)`  
- `public TypeDefinition(System.String namespace, System.String name, Colossal.Mono.Cecil.TypeAttributes attributes, Colossal.Mono.Cecil.TypeReference baseType)`  

## Methods

- `protected virtual ClearFullName() : System.Void`  
- `public virtual Resolve() : Colossal.Mono.Cecil.TypeDefinition`  
- `private ResolveLayout() : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.TypeDefinition+<>c`  

