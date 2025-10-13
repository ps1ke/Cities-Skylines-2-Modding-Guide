# Colossal.Json.DecodeAliasAttribute

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class DecodeAliasAttribute : System.Attribute
{
    private System.String[] <names>k__BackingField;

    public System.String[] names { get; private set; }

    public DecodeAliasAttribute(System.String[] names);

    public System.Boolean Contains(System.String name);
}
```


## Fields

- `private System.String[] <names>k__BackingField`  

```csharp
private System.String[] <names>k__BackingField;
```


## Properties

- `public System.String[] names { get; private set }`  

```csharp
public System.String[] names { get; private set; }
```


## Constructors

- `public DecodeAliasAttribute(System.String[] names)`  

```csharp
public DecodeAliasAttribute(System.String[] names);
```


## Methods

- `public Contains(System.String name) : System.Boolean`  

```csharp
public System.Boolean Contains(System.String name);
```


