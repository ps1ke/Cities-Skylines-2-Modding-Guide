# Colossal.Mono.Cecil.ArrayDimension

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ArrayDimension
{
    private System.Nullable<System.Int32> lower_bound;
    private System.Nullable<System.Int32> upper_bound;

    public System.Nullable<System.Int32> LowerBound { get; set; }
    public System.Nullable<System.Int32> UpperBound { get; set; }
    public System.Boolean IsSized { get; }

    public ArrayDimension(System.Nullable<System.Int32> lowerBound, System.Nullable<System.Int32> upperBound);

    public virtual System.String ToString();
}
```


## Fields

- `private System.Nullable<System.Int32> lower_bound`  

```csharp
private System.Nullable<System.Int32> lower_bound;
```

- `private System.Nullable<System.Int32> upper_bound`  

```csharp
private System.Nullable<System.Int32> upper_bound;
```


## Properties

- `public System.Nullable<System.Int32> LowerBound { get; set }`  

```csharp
public System.Nullable<System.Int32> LowerBound { get; set; }
```

- `public System.Nullable<System.Int32> UpperBound { get; set }`  

```csharp
public System.Nullable<System.Int32> UpperBound { get; set; }
```

- `public System.Boolean IsSized { get }`  

```csharp
public System.Boolean IsSized { get; }
```


## Constructors

- `public ArrayDimension(System.Nullable<System.Int32> lowerBound, System.Nullable<System.Int32> upperBound)`  

```csharp
public ArrayDimension(System.Nullable<System.Int32> lowerBound, System.Nullable<System.Int32> upperBound);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


