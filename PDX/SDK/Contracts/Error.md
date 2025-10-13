# PDX.SDK.Contracts.Error

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Error
{
    private readonly PDX.SDK.Contracts.Enums.Errors.BaseCategory <Category>k__BackingField;
    private readonly System.Enum <SubCategory>k__BackingField;
    private readonly System.String <Details>k__BackingField;
    private readonly System.String <Raw>k__BackingField;

    public PDX.SDK.Contracts.Enums.Errors.BaseCategory Category { get; }
    public System.Enum SubCategory { get; }
    public System.String Details { get; }
    public System.String Raw { get; }

    public Error(System.String raw);
    public Error(System.Enum subCategory, System.String details, System.String raw);
    public Error(System.String categoryString, System.String subCategoryString, System.String details, System.String raw);

    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `private readonly PDX.SDK.Contracts.Enums.Errors.BaseCategory <Category>k__BackingField`  

```csharp
private readonly PDX.SDK.Contracts.Enums.Errors.BaseCategory <Category>k__BackingField;
```

- `private readonly System.Enum <SubCategory>k__BackingField`  

```csharp
private readonly System.Enum <SubCategory>k__BackingField;
```

- `private readonly System.String <Details>k__BackingField`  

```csharp
private readonly System.String <Details>k__BackingField;
```

- `private readonly System.String <Raw>k__BackingField`  

```csharp
private readonly System.String <Raw>k__BackingField;
```


## Properties

- `public PDX.SDK.Contracts.Enums.Errors.BaseCategory Category { get }`  

```csharp
public PDX.SDK.Contracts.Enums.Errors.BaseCategory Category { get; }
```

- `public System.Enum SubCategory { get }`  

```csharp
public System.Enum SubCategory { get; }
```

- `public System.String Details { get }`  

```csharp
public System.String Details { get; }
```

- `public System.String Raw { get }`  

```csharp
public System.String Raw { get; }
```


## Constructors

- `public Error(System.String raw)`  

```csharp
public Error(System.String raw);
```

- `public Error(System.Enum subCategory, System.String details, System.String raw)`  

```csharp
public Error(System.Enum subCategory, System.String details, System.String raw);
```

- `public Error(System.String categoryString, System.String subCategoryString, System.String details, System.String raw)`  

```csharp
public Error(System.String categoryString, System.String subCategoryString, System.String details, System.String raw);
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


