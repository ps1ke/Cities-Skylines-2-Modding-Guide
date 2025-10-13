# Colossal.VersionConstantAttribute

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class VersionConstantAttribute : System.Attribute
{
    private readonly Colossal.Version m_Version;

    public Colossal.Version version { get; }

    public VersionConstantAttribute();
    public VersionConstantAttribute(System.String v);

}
```


## Fields

- `private readonly Colossal.Version m_Version`  

```csharp
private readonly Colossal.Version m_Version;
```


## Properties

- `public Colossal.Version version { get }`  

```csharp
public Colossal.Version version { get; }
```


## Constructors

- `public VersionConstantAttribute()`  

```csharp
public VersionConstantAttribute();
```

- `public VersionConstantAttribute(System.String v)`  

```csharp
public VersionConstantAttribute(System.String v);
```


