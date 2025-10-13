# PDX.SDK.Contracts.Exceptions.ExceptionWithSubCategory

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Exceptions`  

**Type:** class public  

**Base:** `System.Exception`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public class ExceptionWithSubCategory : System.Exception, System.Runtime.Serialization.ISerializable
{
    private System.Enum <Subcategory>k__BackingField;

    public System.Enum Subcategory { get; private set; }

    public ExceptionWithSubCategory(System.Enum subcategory, System.String details);

    public PDX.SDK.Contracts.Result ToResult();
}
```


## Fields

- `private System.Enum <Subcategory>k__BackingField`  

```csharp
private System.Enum <Subcategory>k__BackingField;
```


## Properties

- `public System.Enum Subcategory { get; private set }`  

```csharp
public System.Enum Subcategory { get; private set; }
```


## Constructors

- `public ExceptionWithSubCategory(System.Enum subcategory, System.String details)`  

```csharp
public ExceptionWithSubCategory(System.Enum subcategory, System.String details);
```


## Methods

- `public ToResult() : PDX.SDK.Contracts.Result`  

```csharp
public PDX.SDK.Contracts.Result ToResult();
```


