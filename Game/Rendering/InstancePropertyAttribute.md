# Game.Rendering.InstancePropertyAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class InstancePropertyAttribute : System.Attribute
{
    private System.String <ShaderPropertyName>k__BackingField;
    private System.Type <DataType>k__BackingField;
    private Game.Rendering.BatchFlags <RequiredFlags>k__BackingField;
    private System.Int32 <DataIndex>k__BackingField;
    private System.Boolean <IsBuiltin>k__BackingField;

    public System.String ShaderPropertyName { get; protected set; }
    public System.Type DataType { get; protected set; }
    public Game.Rendering.BatchFlags RequiredFlags { get; protected set; }
    public System.Int32 DataIndex { get; protected set; }
    public System.Boolean IsBuiltin { get; protected set; }

    public InstancePropertyAttribute(System.String shaderPropertyName, System.Type dataType, Game.Rendering.BatchFlags requiredFlags, System.Int32 dataIndex, System.Boolean isBuiltin);

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

- `private Game.Rendering.BatchFlags <RequiredFlags>k__BackingField`  

```csharp
private Game.Rendering.BatchFlags <RequiredFlags>k__BackingField;
```

- `private System.Int32 <DataIndex>k__BackingField`  

```csharp
private System.Int32 <DataIndex>k__BackingField;
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

- `public Game.Rendering.BatchFlags RequiredFlags { get; protected set }`  

```csharp
public Game.Rendering.BatchFlags RequiredFlags { get; protected set; }
```

- `public System.Int32 DataIndex { get; protected set }`  

```csharp
public System.Int32 DataIndex { get; protected set; }
```

- `public System.Boolean IsBuiltin { get; protected set }`  

```csharp
public System.Boolean IsBuiltin { get; protected set; }
```


## Constructors

- `public InstancePropertyAttribute(System.String shaderPropertyName, System.Type dataType, Game.Rendering.BatchFlags requiredFlags = 0, System.Int32 dataIndex = 0, System.Boolean isBuiltin = False)`  

```csharp
public InstancePropertyAttribute(System.String shaderPropertyName, System.Type dataType, Game.Rendering.BatchFlags requiredFlags, System.Int32 dataIndex, System.Boolean isBuiltin);
```


