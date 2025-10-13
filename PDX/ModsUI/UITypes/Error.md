# PDX.ModsUI.UITypes.Error

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Error
{
    private System.String <Category>k__BackingField;
    private System.String <SubCategory>k__BackingField;
    private System.String <Details>k__BackingField;
    private System.String <Raw>k__BackingField;

    public System.String Category { get; private set; }
    public System.String SubCategory { get; private set; }
    public System.String Details { get; private set; }
    public System.String Raw { get; private set; }

    public Error(System.String category, System.String subCategory, System.String details, System.String raw);

    public virtual System.String ToString();
}
```


## Fields

- `private System.String <Category>k__BackingField`  

```csharp
private System.String <Category>k__BackingField;
```

- `private System.String <SubCategory>k__BackingField`  

```csharp
private System.String <SubCategory>k__BackingField;
```

- `private System.String <Details>k__BackingField`  

```csharp
private System.String <Details>k__BackingField;
```

- `private System.String <Raw>k__BackingField`  

```csharp
private System.String <Raw>k__BackingField;
```


## Properties

- `public System.String Category { get; private set }`  

```csharp
public System.String Category { get; private set; }
```

- `public System.String SubCategory { get; private set }`  

```csharp
public System.String SubCategory { get; private set; }
```

- `public System.String Details { get; private set }`  

```csharp
public System.String Details { get; private set; }
```

- `public System.String Raw { get; private set }`  

```csharp
public System.String Raw { get; private set; }
```


## Constructors

- `public Error(System.String category, System.String subCategory, System.String details, System.String raw)`  

```csharp
public Error(System.String category, System.String subCategory, System.String details, System.String raw);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


