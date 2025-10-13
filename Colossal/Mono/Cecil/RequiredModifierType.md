# Colossal.Mono.Cecil.RequiredModifierType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IModifierType`  

## Code

```csharp
public sealed class RequiredModifierType : Colossal.Mono.Cecil.TypeSpecification, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext, Colossal.Mono.Cecil.IModifierType
{
    private Colossal.Mono.Cecil.TypeReference modifier_type;

    public Colossal.Mono.Cecil.TypeReference ModifierType { get; set; }
    public System.String Name { get; }
    public System.String FullName { get; }
    private System.String Suffix { private get; }
    public System.Boolean IsValueType { get; set; }
    public System.Boolean IsRequiredModifier { get; }
    public System.Boolean ContainsGenericParameter { get; }

    public RequiredModifierType(Colossal.Mono.Cecil.TypeReference modifierType, Colossal.Mono.Cecil.TypeReference type);

}
```


## Fields

- `private Colossal.Mono.Cecil.TypeReference modifier_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference modifier_type;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference ModifierType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ModifierType { get; set; }
```

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `private System.String Suffix { private get }`  

```csharp
private System.String Suffix { private get; }
```

- `public System.Boolean IsValueType { get; set }`  

```csharp
public System.Boolean IsValueType { get; set; }
```

- `public System.Boolean IsRequiredModifier { get }`  

```csharp
public System.Boolean IsRequiredModifier { get; }
```

- `public System.Boolean ContainsGenericParameter { get }`  

```csharp
public System.Boolean ContainsGenericParameter { get; }
```


## Constructors

- `public RequiredModifierType(Colossal.Mono.Cecil.TypeReference modifierType, Colossal.Mono.Cecil.TypeReference type)`  

```csharp
public RequiredModifierType(Colossal.Mono.Cecil.TypeReference modifierType, Colossal.Mono.Cecil.TypeReference type);
```


