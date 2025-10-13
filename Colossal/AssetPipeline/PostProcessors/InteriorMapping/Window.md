# Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.InteriorMapping`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Window
{
    private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island> m_Islands;
    private UnityEngine.Bounds m_Bounds;
    private System.Boolean m_Empty;
    private Unity.Mathematics.float3 <normal>k__BackingField;
    private Unity.Mathematics.float3 <tangent>k__BackingField;
    private Unity.Mathematics.float3 <up>k__BackingField;
    private Unity.Mathematics.float3 <center>k__BackingField;
    private System.Single <width>k__BackingField;
    private System.Single <height>k__BackingField;
    private System.Int32 <room>k__BackingField;
    private System.Int32 <roomIndex>k__BackingField;
    private System.Int32 <floor>k__BackingField;

    public Unity.Mathematics.float3 normal { get; private set; }
    public Unity.Mathematics.float3 tangent { get; private set; }
    public Unity.Mathematics.float3 up { get; private set; }
    public Unity.Mathematics.float3 center { get; private set; }
    public System.Single width { get; private set; }
    public System.Single height { get; private set; }
    public System.Int32 room { get; private set; }
    public System.Int32 roomIndex { get; set; }
    public System.Int32 floor { get; set; }
    public UnityEngine.Bounds bounds { get; }
    public System.Boolean valid { get; }
    public System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles { get; }

    public Window();

    public System.Boolean AddIsland(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island island);
    public System.Void CalculateNormalTangent(System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float3> vertices);
    private static System.Int32 DetectFacing(Unity.Mathematics.float3 normal);
    public System.Void DetermineRoom(System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.ReadOnlySpan<System.Int32> indices);
    public System.Boolean Merge(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window);
    public System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> Split(System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island> m_Islands`  

```csharp
private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island> m_Islands;
```

- `private UnityEngine.Bounds m_Bounds`  

```csharp
private UnityEngine.Bounds m_Bounds;
```

- `private System.Boolean m_Empty`  

```csharp
private System.Boolean m_Empty;
```

- `private Unity.Mathematics.float3 <normal>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <normal>k__BackingField;
```

- `private Unity.Mathematics.float3 <tangent>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <tangent>k__BackingField;
```

- `private Unity.Mathematics.float3 <up>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <up>k__BackingField;
```

- `private Unity.Mathematics.float3 <center>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <center>k__BackingField;
```

- `private System.Single <width>k__BackingField`  

```csharp
private System.Single <width>k__BackingField;
```

- `private System.Single <height>k__BackingField`  

```csharp
private System.Single <height>k__BackingField;
```

- `private System.Int32 <room>k__BackingField`  

```csharp
private System.Int32 <room>k__BackingField;
```

- `private System.Int32 <roomIndex>k__BackingField`  

```csharp
private System.Int32 <roomIndex>k__BackingField;
```

- `private System.Int32 <floor>k__BackingField`  

```csharp
private System.Int32 <floor>k__BackingField;
```


## Properties

- `public Unity.Mathematics.float3 normal { get; private set }`  

```csharp
public Unity.Mathematics.float3 normal { get; private set; }
```

- `public Unity.Mathematics.float3 tangent { get; private set }`  

```csharp
public Unity.Mathematics.float3 tangent { get; private set; }
```

- `public Unity.Mathematics.float3 up { get; private set }`  

```csharp
public Unity.Mathematics.float3 up { get; private set; }
```

- `public Unity.Mathematics.float3 center { get; private set }`  

```csharp
public Unity.Mathematics.float3 center { get; private set; }
```

- `public System.Single width { get; private set }`  

```csharp
public System.Single width { get; private set; }
```

- `public System.Single height { get; private set }`  

```csharp
public System.Single height { get; private set; }
```

- `public System.Int32 room { get; private set }`  

```csharp
public System.Int32 room { get; private set; }
```

- `public System.Int32 roomIndex { get; set }`  

```csharp
public System.Int32 roomIndex { get; set; }
```

- `public System.Int32 floor { get; set }`  

```csharp
public System.Int32 floor { get; set; }
```

- `public UnityEngine.Bounds bounds { get }`  

```csharp
public UnityEngine.Bounds bounds { get; }
```

- `public System.Boolean valid { get }`  

```csharp
public System.Boolean valid { get; }
```

- `public System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles { get; }
```


## Constructors

- `public Window()`  

```csharp
public Window();
```


## Methods

- `public AddIsland(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island island) : System.Boolean`  

```csharp
public System.Boolean AddIsland(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island island);
```

- `public CalculateNormalTangent(System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float3> vertices) : System.Void`  

```csharp
public System.Void CalculateNormalTangent(System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float3> vertices);
```

- `private static DetectFacing(Unity.Mathematics.float3 normal) : System.Int32`  

```csharp
private static System.Int32 DetectFacing(Unity.Mathematics.float3 normal);
```

- `public DetermineRoom(System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.ReadOnlySpan<System.Int32> indices) : System.Void`  

```csharp
public System.Void DetermineRoom(System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.ReadOnlySpan<System.Int32> indices);
```

- `public Merge(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window) : System.Boolean`  

```csharp
public System.Boolean Merge(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window);
```

- `public Split(System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals) : System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window>`  

```csharp
public System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window> Split(System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window+<get_triangles>d__44`  

