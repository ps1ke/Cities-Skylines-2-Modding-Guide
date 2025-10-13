# Colossal.Mono.Cecil.IConstantProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract interface IConstantProvider : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public System.Boolean HasConstant { get; set; }
    public System.Object Constant { get; set; }

}
```


## Properties

- `public System.Boolean HasConstant { get; set }`  

```csharp
public System.Boolean HasConstant { get; set; }
```

- `public System.Object Constant { get; set }`  

```csharp
public System.Object Constant { get; set; }
```


