# Colossal.InvokeMethodAttribute

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `UnityEngine.PropertyAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class InvokeMethodAttribute : UnityEngine.PropertyAttribute
{
    private System.String <methodName>k__BackingField;
    private System.Boolean <onlyInPlayMode>k__BackingField;

    public System.String methodName { get; private set; }
    public System.Boolean onlyInPlayMode { get; private set; }

    public InvokeMethodAttribute(System.String methodName, System.Boolean onlyInPlayMode);

}
```


## Fields

- `private System.String <methodName>k__BackingField`  

```csharp
private System.String <methodName>k__BackingField;
```

- `private System.Boolean <onlyInPlayMode>k__BackingField`  

```csharp
private System.Boolean <onlyInPlayMode>k__BackingField;
```


## Properties

- `public System.String methodName { get; private set }`  

```csharp
public System.String methodName { get; private set; }
```

- `public System.Boolean onlyInPlayMode { get; private set }`  

```csharp
public System.Boolean onlyInPlayMode { get; private set; }
```


## Constructors

- `public InvokeMethodAttribute(System.String methodName, System.Boolean onlyInPlayMode = True)`  

```csharp
public InvokeMethodAttribute(System.String methodName, System.Boolean onlyInPlayMode);
```


