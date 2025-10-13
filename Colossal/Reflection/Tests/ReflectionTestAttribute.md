# Colossal.Reflection.Tests.ReflectionTestAttribute

**Assembly:** `Colossal.Core.TestScenarios`  
**Namespace:** `Colossal.Reflection.Tests`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class ReflectionTestAttribute : System.Attribute
{
    private readonly System.String <Name>k__BackingField;
    private readonly System.Int32 <Order>k__BackingField;

    public System.String Name { get; }
    public System.Int32 Order { get; }

    public ReflectionTestAttribute(System.String name, System.Int32 order);

}
```


## Fields

- `private readonly System.String <Name>k__BackingField`  

```csharp
private readonly System.String <Name>k__BackingField;
```

- `private readonly System.Int32 <Order>k__BackingField`  

```csharp
private readonly System.Int32 <Order>k__BackingField;
```


## Properties

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public System.Int32 Order { get }`  

```csharp
public System.Int32 Order { get; }
```


## Constructors

- `public ReflectionTestAttribute(System.String name, System.Int32 order = 0)`  

```csharp
public ReflectionTestAttribute(System.String name, System.Int32 order);
```


