# Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class MaterialDescription
{
    public System.Int32 m_Hash;
    public UnityEngine.Material m_Material;
    public System.Boolean m_SupportsVT;
    public System.Int32 m_MipBiasOverride;
    public Colossal.IO.AssetDatabase.MaterialStackProperties[] m_Stacks;

    public System.Boolean hasMipBiasOverride { get; }

    public MaterialDescription();

    public System.Int32 GetLayerIndexInStack(System.Int32 stackConfigIndex, System.String textureName);
    public System.Int32 GetStackConfigIndex(System.String propName);
    public System.Boolean IsValid();
}
```


## Fields

- `public System.Int32 m_Hash`  

```csharp
public System.Int32 m_Hash;
```

- `public UnityEngine.Material m_Material`  

```csharp
public UnityEngine.Material m_Material;
```

- `public System.Boolean m_SupportsVT`  

```csharp
public System.Boolean m_SupportsVT;
```

- `public System.Int32 m_MipBiasOverride`  

```csharp
public System.Int32 m_MipBiasOverride;
```

- `public Colossal.IO.AssetDatabase.MaterialStackProperties[] m_Stacks`  

```csharp
public Colossal.IO.AssetDatabase.MaterialStackProperties[] m_Stacks;
```


## Properties

- `public System.Boolean hasMipBiasOverride { get }`  

```csharp
public System.Boolean hasMipBiasOverride { get; }
```


## Constructors

- `public MaterialDescription()`  

```csharp
public MaterialDescription();
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

- `public IsValid() : System.Boolean`  

```csharp
public System.Boolean IsValid();
```


