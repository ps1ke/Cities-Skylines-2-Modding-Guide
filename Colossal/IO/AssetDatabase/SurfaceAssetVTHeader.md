# Colossal.IO.AssetDatabase.SurfaceAssetVTHeader

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SurfaceAssetVTHeader
{
    public System.Int32 m_NbVTStacks;
    private Colossal.IO.AssetDatabase.PerStackData m_StackData0;
    private Colossal.IO.AssetDatabase.PerStackData m_StackData1;

    public SurfaceAssetVTHeader(System.Int32 nbVTStacks);

    public Colossal.Hash128 GetPreProcessedTextureGuid(System.Int32 guidIndex);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize GetUnbiasedStackTextureSize(System.Int32 stackIndex);
    public System.Void SetPreProcessedTextureGuid(System.Int32 guidIndex, Colossal.Hash128 guid);
    public System.Void SetTextureGuid(System.Int32 guidIndex, Colossal.Hash128 guid);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize SetUnbiasedStackTextureSize(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height);
}
```


## Fields

- `public System.Int32 m_NbVTStacks`  

```csharp
public System.Int32 m_NbVTStacks;
```

- `private Colossal.IO.AssetDatabase.PerStackData m_StackData0`  

```csharp
private Colossal.IO.AssetDatabase.PerStackData m_StackData0;
```

- `private Colossal.IO.AssetDatabase.PerStackData m_StackData1`  

```csharp
private Colossal.IO.AssetDatabase.PerStackData m_StackData1;
```


## Constructors

- `public SurfaceAssetVTHeader(System.Int32 nbVTStacks)`  

```csharp
public SurfaceAssetVTHeader(System.Int32 nbVTStacks);
```


## Methods

- `public GetPreProcessedTextureGuid(System.Int32 guidIndex) : Colossal.Hash128`  

```csharp
public Colossal.Hash128 GetPreProcessedTextureGuid(System.Int32 guidIndex);
```

- `public GetUnbiasedStackTextureSize(System.Int32 stackIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize GetUnbiasedStackTextureSize(System.Int32 stackIndex);
```

- `public SetPreProcessedTextureGuid(System.Int32 guidIndex, Colossal.Hash128 guid) : System.Void`  

```csharp
public System.Void SetPreProcessedTextureGuid(System.Int32 guidIndex, Colossal.Hash128 guid);
```

- `public SetTextureGuid(System.Int32 guidIndex, Colossal.Hash128 guid) : System.Void`  

```csharp
public System.Void SetTextureGuid(System.Int32 guidIndex, Colossal.Hash128 guid);
```

- `public SetUnbiasedStackTextureSize(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize SetUnbiasedStackTextureSize(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height);
```


