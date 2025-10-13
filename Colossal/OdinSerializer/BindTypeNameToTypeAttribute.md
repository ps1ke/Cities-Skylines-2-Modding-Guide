# Colossal.OdinSerializer.BindTypeNameToTypeAttribute

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public sealed class BindTypeNameToTypeAttribute : System.Attribute
{
    internal readonly System.Type NewType;
    internal readonly System.String OldTypeName;

    public BindTypeNameToTypeAttribute(System.String oldFullTypeName, System.Type newType);

}
```


## Fields

- `internal readonly System.Type NewType`  

```csharp
internal readonly System.Type NewType;
```

- `internal readonly System.String OldTypeName`  

```csharp
internal readonly System.String OldTypeName;
```


## Constructors

- `public BindTypeNameToTypeAttribute(System.String oldFullTypeName, System.Type newType)`  

```csharp
public BindTypeNameToTypeAttribute(System.String oldFullTypeName, System.Type newType);
```


