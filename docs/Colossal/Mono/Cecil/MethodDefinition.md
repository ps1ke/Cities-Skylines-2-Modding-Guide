# Colossal.Mono.Cecil.MethodDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.MethodReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMethodSignature`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IMemberDefinition`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.ISecurityDeclarationProvider`, `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`  

## Fields

- `private System.UInt16 attributes`  
- `private System.UInt16 impl_attributes`  
- `internal System.Boolean sem_attrs_ready`  
- `internal Colossal.Mono.Cecil.MethodSemanticsAttributes sem_attrs`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations`  
- `internal System.UInt32 rva`  
- `internal Colossal.Mono.Cecil.PInvokeInfo pinvoke`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodReference> overrides`  
- `internal Colossal.Mono.Cecil.Cil.MethodBody body`  
- `internal Colossal.Mono.Cecil.Cil.MethodDebugInformation debug_info`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> custom_infos`  

## Properties

- `public System.String Name { get; set }`  
- `public Colossal.Mono.Cecil.MethodAttributes Attributes { get; set }`  
- `public Colossal.Mono.Cecil.MethodImplAttributes ImplAttributes { get; set }`  
- `public Colossal.Mono.Cecil.MethodSemanticsAttributes SemanticsAttributes { get; set }`  
- `internal Colossal.Mono.Cecil.MethodDefinitionProjection WindowsRuntimeProjection { internal get; internal set }`  
- `public System.Boolean HasSecurityDeclarations { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public System.Int32 RVA { get }`  
- `public System.Boolean HasBody { get }`  
- `public Colossal.Mono.Cecil.Cil.MethodBody Body { get; set }`  
- `public Colossal.Mono.Cecil.Cil.MethodDebugInformation DebugInformation { get; set }`  
- `public System.Boolean HasPInvokeInfo { get }`  
- `public Colossal.Mono.Cecil.PInvokeInfo PInvokeInfo { get; set }`  
- `public System.Boolean HasOverrides { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodReference> Overrides { get }`  
- `public System.Boolean HasGenericParameters { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get }`  
- `public System.Boolean HasCustomDebugInformations { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.CustomDebugInformation> CustomDebugInformations { get }`  
- `public System.Boolean IsCompilerControlled { get; set }`  
- `public System.Boolean IsPrivate { get; set }`  
- `public System.Boolean IsFamilyAndAssembly { get; set }`  
- `public System.Boolean IsAssembly { get; set }`  
- `public System.Boolean IsFamily { get; set }`  
- `public System.Boolean IsFamilyOrAssembly { get; set }`  
- `public System.Boolean IsPublic { get; set }`  
- `public System.Boolean IsStatic { get; set }`  
- `public System.Boolean IsFinal { get; set }`  
- `public System.Boolean IsVirtual { get; set }`  
- `public System.Boolean IsHideBySig { get; set }`  
- `public System.Boolean IsReuseSlot { get; set }`  
- `public System.Boolean IsNewSlot { get; set }`  
- `public System.Boolean IsCheckAccessOnOverride { get; set }`  
- `public System.Boolean IsAbstract { get; set }`  
- `public System.Boolean IsSpecialName { get; set }`  
- `public System.Boolean IsPInvokeImpl { get; set }`  
- `public System.Boolean IsUnmanagedExport { get; set }`  
- `public System.Boolean IsRuntimeSpecialName { get; set }`  
- `public System.Boolean HasSecurity { get; set }`  
- `public System.Boolean IsIL { get; set }`  
- `public System.Boolean IsNative { get; set }`  
- `public System.Boolean IsRuntime { get; set }`  
- `public System.Boolean IsUnmanaged { get; set }`  
- `public System.Boolean IsManaged { get; set }`  
- `public System.Boolean IsForwardRef { get; set }`  
- `public System.Boolean IsPreserveSig { get; set }`  
- `public System.Boolean IsInternalCall { get; set }`  
- `public System.Boolean IsSynchronized { get; set }`  
- `public System.Boolean NoInlining { get; set }`  
- `public System.Boolean NoOptimization { get; set }`  
- `public System.Boolean AggressiveInlining { get; set }`  
- `public System.Boolean IsSetter { get; set }`  
- `public System.Boolean IsGetter { get; set }`  
- `public System.Boolean IsOther { get; set }`  
- `public System.Boolean IsAddOn { get; set }`  
- `public System.Boolean IsRemoveOn { get; set }`  
- `public System.Boolean IsFire { get; set }`  
- `public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set }`  
- `public System.Boolean IsConstructor { get }`  
- `public System.Boolean IsDefinition { get }`  

## Constructors

- `internal MethodDefinition()`  
- `public MethodDefinition(System.String name, Colossal.Mono.Cecil.MethodAttributes attributes, Colossal.Mono.Cecil.TypeReference returnType)`  

## Methods

- `internal ReadSemantics() : System.Void`  
- `public virtual Resolve() : Colossal.Mono.Cecil.MethodDefinition`  

## Nested types

- `Colossal.Mono.Cecil.MethodDefinition+<>c`  

