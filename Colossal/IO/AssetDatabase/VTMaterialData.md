# Colossal.IO.AssetDatabase.VTMaterialData

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class VTMaterialData
{
    public System.Boolean disabled;
    public UnityEngine.Shader shader;
    public System.Int32 mipBiasOverride;
    public Colossal.IO.AssetDatabase.VTMaterialStackData[] stacks;

    public System.Boolean hasMipBiasOverride { get; }

    public VTMaterialData();

    public System.Int32 GetLayerIndexInStack(System.Int32 stackConfigIndex, System.String textureName);
    public System.Int32 GetStackConfigIndex(System.String propName);
}
```


## Fields

- `public System.Boolean disabled`  

```csharp
public System.Boolean disabled;
```

- `public UnityEngine.Shader shader`  

```csharp
public UnityEngine.Shader shader;
```

- `public System.Int32 mipBiasOverride`  

```csharp
public System.Int32 mipBiasOverride;
```

- `public Colossal.IO.AssetDatabase.VTMaterialStackData[] stacks`  

```csharp
public Colossal.IO.AssetDatabase.VTMaterialStackData[] stacks;
```


## Properties

- `public System.Boolean hasMipBiasOverride { get }`  

```csharp
public System.Boolean hasMipBiasOverride { get; }
```


## Constructors

- `public VTMaterialData()`  

```csharp
public VTMaterialData();
```


## Methods

- `public GetLayerIndexInStack(System.Int32 stackConfigIndex, System.String textureName) : System.Int32`  

```csharp
public System.Int32 GetLayerIndexInStack(System.Int32 stackConfigIndex, System.String textureName);
```

- `public GetStackConfigIndex(System.String propName) : System.Int32`  

```csharp
public System.Int32 GetStackConfigIndex(System.String propName);
```


