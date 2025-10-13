# Colossal.ConditionalAttribute

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `UnityEngine.PropertyAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class ConditionalAttribute : UnityEngine.PropertyAttribute
{
    private System.String <conditionalSourceField>k__BackingField;
    private System.Boolean <hideInInspector>k__BackingField;

    public System.String conditionalSourceField { get; private set; }
    public System.Boolean hideInInspector { get; private set; }

    public ConditionalAttribute(System.String conditionalSourceField, System.Boolean hideInInspector);

}
```


## Fields

- `private System.String <conditionalSourceField>k__BackingField`  

```csharp
private System.String <conditionalSourceField>k__BackingField;
```

- `private System.Boolean <hideInInspector>k__BackingField`  

```csharp
private System.Boolean <hideInInspector>k__BackingField;
```


## Properties

- `public System.String conditionalSourceField { get; private set }`  

```csharp
public System.String conditionalSourceField { get; private set; }
```

- `public System.Boolean hideInInspector { get; private set }`  

```csharp
public System.Boolean hideInInspector { get; private set; }
```


## Constructors

- `public ConditionalAttribute(System.String conditionalSourceField, System.Boolean hideInInspector = True)`  

```csharp
public ConditionalAttribute(System.String conditionalSourceField, System.Boolean hideInInspector);
```


