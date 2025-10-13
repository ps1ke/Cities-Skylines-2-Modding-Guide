# Colossal.TestFramework.TestDescriptorAttribute

**Assembly:** `Colossal.TestFramework`  
**Namespace:** `Colossal.TestFramework`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class TestDescriptorAttribute : System.Attribute
{
    public readonly System.String description;
    public readonly Colossal.TestFramework.Category category;
    public readonly System.Boolean skipBeta;
    public readonly Colossal.TestFramework.TestPhase testPhase;
    public readonly System.Boolean disabled;

    private TestDescriptorAttribute();
    public TestDescriptorAttribute(System.String description, Colossal.TestFramework.Category category, System.Boolean skipBeta, Colossal.TestFramework.TestPhase testPhase, System.Boolean disabled);

}
```


## Fields

- `public readonly System.String description`  

```csharp
public readonly System.String description;
```

- `public readonly Colossal.TestFramework.Category category`  

```csharp
public readonly Colossal.TestFramework.Category category;
```

- `public readonly System.Boolean skipBeta`  

```csharp
public readonly System.Boolean skipBeta;
```

- `public readonly Colossal.TestFramework.TestPhase testPhase`  

```csharp
public readonly Colossal.TestFramework.TestPhase testPhase;
```

- `public readonly System.Boolean disabled`  

```csharp
public readonly System.Boolean disabled;
```


## Constructors

- `private TestDescriptorAttribute()`  

```csharp
private TestDescriptorAttribute();
```

- `public TestDescriptorAttribute(System.String description, Colossal.TestFramework.Category category, System.Boolean skipBeta = False, Colossal.TestFramework.TestPhase testPhase = Default, System.Boolean disabled = False)`  

```csharp
public TestDescriptorAttribute(System.String description, Colossal.TestFramework.Category category, System.Boolean skipBeta, Colossal.TestFramework.TestPhase testPhase, System.Boolean disabled);
```


