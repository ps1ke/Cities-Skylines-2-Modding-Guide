# Colossal.InstaLOD.Remeshing

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Remeshing
{
    private System.IntPtr m_Ptr;
    private System.IntPtr m_SDK;

    public Remeshing(Colossal.InstaLOD.InstaLODSDK sdk);

    public System.Void AddMesh(Colossal.InstaLOD.InstaLODMesh mesh);
    public System.Void Dispose();
    public Colossal.InstaLOD.InstaLODMaterial Execute(Colossal.InstaLOD.InstaLODMesh outputMesh, Colossal.InstaLOD.RemeshingSettings settings);
    public System.Void SetMaterialData(Colossal.InstaLOD.InstaLODMaterialData matData);
}
```


## Fields

- `private System.IntPtr m_Ptr`  

```csharp
private System.IntPtr m_Ptr;
```

- `private System.IntPtr m_SDK`  

```csharp
private System.IntPtr m_SDK;
```


## Constructors

- `public Remeshing(Colossal.InstaLOD.InstaLODSDK sdk)`  

```csharp
public Remeshing(Colossal.InstaLOD.InstaLODSDK sdk);
```


## Methods

- `public AddMesh(Colossal.InstaLOD.InstaLODMesh mesh) : System.Void`  

```csharp
public System.Void AddMesh(Colossal.InstaLOD.InstaLODMesh mesh);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Execute(Colossal.InstaLOD.InstaLODMesh outputMesh, Colossal.InstaLOD.RemeshingSettings settings) : Colossal.InstaLOD.InstaLODMaterial`  

```csharp
public Colossal.InstaLOD.InstaLODMaterial Execute(Colossal.InstaLOD.InstaLODMesh outputMesh, Colossal.InstaLOD.RemeshingSettings settings);
```

- `public SetMaterialData(Colossal.InstaLOD.InstaLODMaterialData matData) : System.Void`  

```csharp
public System.Void SetMaterialData(Colossal.InstaLOD.InstaLODMaterialData matData);
```


