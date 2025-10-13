# Colossal.Mono.Cecil.CustomAttributeArgument

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CustomAttributeArgument
{
    private readonly Colossal.Mono.Cecil.TypeReference type;
    private readonly System.Object value;

    public Colossal.Mono.Cecil.TypeReference Type { get; }
    public System.Object Value { get; }

    public CustomAttributeArgument(Colossal.Mono.Cecil.TypeReference type, System.Object value);

}
```


## Fields

- `private readonly Colossal.Mono.Cecil.TypeReference type`  

```csharp
private readonly Colossal.Mono.Cecil.TypeReference type;
```

- `private readonly System.Object value`  

```csharp
private readonly System.Object value;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference Type { get }`  

```csharp
public Colossal.Mono.Cecil.TypeReference Type { get; }
```

- `public System.Object Value { get }`  

```csharp
public System.Object Value { get; }
```


## Constructors

- `public CustomAttributeArgument(Colossal.Mono.Cecil.TypeReference type, System.Object value)`  

```csharp
public CustomAttributeArgument(Colossal.Mono.Cecil.TypeReference type, System.Object value);
```


