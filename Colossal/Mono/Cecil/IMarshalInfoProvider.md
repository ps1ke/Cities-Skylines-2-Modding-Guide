# Colossal.Mono.Cecil.IMarshalInfoProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract interface IMarshalInfoProvider : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public System.Boolean HasMarshalInfo { get; }
    public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set; }

}
```


## Properties

- `public System.Boolean HasMarshalInfo { get }`  

```csharp
public System.Boolean HasMarshalInfo { get; }
```

- `public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set }`  

```csharp
public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set; }
```


