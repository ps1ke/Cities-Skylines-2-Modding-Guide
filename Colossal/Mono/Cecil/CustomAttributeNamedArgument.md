# Colossal.Mono.Cecil.CustomAttributeNamedArgument

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CustomAttributeNamedArgument
{
    private readonly System.String name;
    private readonly Colossal.Mono.Cecil.CustomAttributeArgument argument;

    public System.String Name { get; }
    public Colossal.Mono.Cecil.CustomAttributeArgument Argument { get; }

    public CustomAttributeNamedArgument(System.String name, Colossal.Mono.Cecil.CustomAttributeArgument argument);

}
```


## Fields

- `private readonly System.String name`  

```csharp
private readonly System.String name;
```

- `private readonly Colossal.Mono.Cecil.CustomAttributeArgument argument`  

```csharp
private readonly Colossal.Mono.Cecil.CustomAttributeArgument argument;
```


## Properties

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public Colossal.Mono.Cecil.CustomAttributeArgument Argument { get }`  

```csharp
public Colossal.Mono.Cecil.CustomAttributeArgument Argument { get; }
```


## Constructors

- `public CustomAttributeNamedArgument(System.String name, Colossal.Mono.Cecil.CustomAttributeArgument argument)`  

```csharp
public CustomAttributeNamedArgument(System.String name, Colossal.Mono.Cecil.CustomAttributeArgument argument);
```


