# Game.Rendering.MaterialPropertyAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class MaterialPropertyAttribute : System.Attribute
{
    private System.String <ShaderPropertyName>k__BackingField;
    private System.Type <DataType>k__BackingField;
    private System.Boolean <IsBuiltin>k__BackingField;

    public System.String ShaderPropertyName { get; protected set; }
    public System.Type DataType { get; protected set; }
    public System.Boolean IsBuiltin { get; protected set; }

    public MaterialPropertyAttribute(System.String shaderPropertyName, System.Type dataType, System.Boolean isBuiltin);

}
```


## Fields

- `private System.String <ShaderPropertyName>k__BackingField`  

```csharp
private System.String <ShaderPropertyName>k__BackingField;
```

- `private System.Type <DataType>k__BackingField`  

```csharp
private System.Type <DataType>k__BackingField;
```

- `private System.Boolean <IsBuiltin>k__BackingField`  

```csharp
private System.Boolean <IsBuiltin>k__BackingField;
```


## Properties

- `public System.String ShaderPropertyName { get; protected set }`  

```csharp
public System.String ShaderPropertyName { get; protected set; }
```

- `public System.Type DataType { get; protected set }`  

```csharp
public System.Type DataType { get; protected set; }
```

- `public System.Boolean IsBuiltin { get; protected set }`  

```csharp
public System.Boolean IsBuiltin { get; protected set; }
```


## Constructors

- `public MaterialPropertyAttribute(System.String shaderPropertyName, System.Type dataType, System.Boolean isBuiltin = False)`  

```csharp
public MaterialPropertyAttribute(System.String shaderPropertyName, System.Type dataType, System.Boolean isBuiltin);
```


