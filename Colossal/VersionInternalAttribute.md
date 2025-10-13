# Colossal.VersionInternalAttribute

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class VersionInternalAttribute : System.Attribute
{
    private System.String m_GeneratedVersion;

    public System.String generatedVersion { get; }

    private VersionInternalAttribute();
    public VersionInternalAttribute(System.String v);

}
```


## Fields

- `private System.String m_GeneratedVersion`  

```csharp
private System.String m_GeneratedVersion;
```


## Properties

- `public System.String generatedVersion { get }`  

```csharp
public System.String generatedVersion { get; }
```


## Constructors

- `private VersionInternalAttribute()`  

```csharp
private VersionInternalAttribute();
```

- `public VersionInternalAttribute(System.String v)`  

```csharp
public VersionInternalAttribute(System.String v);
```


