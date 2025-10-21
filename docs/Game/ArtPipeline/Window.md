# Game.ArtPipeline.InteriorMappingProcessor+Window

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Window
{
    private System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Island> m_Islands;
    private UnityEngine.Bounds m_Bounds;
    private System.Boolean m_Empty;
    private UnityEngine.Vector3 <normal>k__BackingField;
    private UnityEngine.Vector3 <tangent>k__BackingField;
    private UnityEngine.Vector3 <up>k__BackingField;
    private UnityEngine.Vector3 <center>k__BackingField;
    private System.Single <width>k__BackingField;
    private System.Single <height>k__BackingField;
    private System.Int32 <room>k__BackingField;
    private System.Int32 <roomIndex>k__BackingField;
    private System.Int32 <floor>k__BackingField;

    public UnityEngine.Vector3 normal { get; private set; }
    public UnityEngine.Vector3 tangent { get; private set; }
    public UnityEngine.Vector3 up { get; private set; }
    public UnityEngine.Vector3 center { get; private set; }
    public System.Single width { get; private set; }
    public System.Single height { get; private set; }
    public System.Int32 room { get; private set; }
    public System.Int32 roomIndex { get; set; }
    public System.Int32 floor { get; set; }
    public UnityEngine.Bounds bounds { get; }
    public System.Boolean valid { get; }
    public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> triangles { get; }

    public Window();

    public System.Boolean AddIsland(Game.ArtPipeline.InteriorMappingProcessor+Island island);
    public System.Void CalculateNormalTangent(System.Int32[] indices, UnityEngine.Vector3[] normals, UnityEngine.Vector3[] vertices);
    private static System.Int32 DeterimineFace(UnityEngine.Vector3 normal);
    public System.Void DetermineRoom(System.Collections.Generic.List<UnityEngine.Vector4> uvs, System.Int32[] Indices);
    public System.Boolean Merge(Game.ArtPipeline.InteriorMappingProcessor+Window window);
    public System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window> Split(System.Int32[] indices, UnityEngine.Vector3[] normals);
}
```


## Fields

- `private System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Island> m_Islands`  

```csharp
private System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Island> m_Islands;
```

- `private UnityEngine.Bounds m_Bounds`  

```csharp
private UnityEngine.Bounds m_Bounds;
```

- `private System.Boolean m_Empty`  

```csharp
private System.Boolean m_Empty;
```

- `private UnityEngine.Vector3 <normal>k__BackingField`  

```csharp
private UnityEngine.Vector3 <normal>k__BackingField;
```

- `private UnityEngine.Vector3 <tangent>k__BackingField`  

```csharp
private UnityEngine.Vector3 <tangent>k__BackingField;
```

- `private UnityEngine.Vector3 <up>k__BackingField`  

```csharp
private UnityEngine.Vector3 <up>k__BackingField;
```

- `private UnityEngine.Vector3 <center>k__BackingField`  

```csharp
private UnityEngine.Vector3 <center>k__BackingField;
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

- `public UnityEngine.Vector3 normal { get; private set }`  

```csharp
public UnityEngine.Vector3 normal { get; private set; }
```

- `public UnityEngine.Vector3 tangent { get; private set }`  

```csharp
public UnityEngine.Vector3 tangent { get; private set; }
```

- `public UnityEngine.Vector3 up { get; private set }`  

```csharp
public UnityEngine.Vector3 up { get; private set; }
```

- `public UnityEngine.Vector3 center { get; private set }`  

```csharp
public UnityEngine.Vector3 center { get; private set; }
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

- `public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> triangles { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> triangles { get; }
```


## Constructors

- `public Window()`  

```csharp
public Window();
```


## Methods

- `public AddIsland(Game.ArtPipeline.InteriorMappingProcessor+Island island) : System.Boolean`  

```csharp
public System.Boolean AddIsland(Game.ArtPipeline.InteriorMappingProcessor+Island island);
```

- `public CalculateNormalTangent(System.Int32[] indices, UnityEngine.Vector3[] normals, UnityEngine.Vector3[] vertices) : System.Void`  

```csharp
public System.Void CalculateNormalTangent(System.Int32[] indices, UnityEngine.Vector3[] normals, UnityEngine.Vector3[] vertices);
```

- `private static DeterimineFace(UnityEngine.Vector3 normal) : System.Int32`  

```csharp
private static System.Int32 DeterimineFace(UnityEngine.Vector3 normal);
```

- `public DetermineRoom(System.Collections.Generic.List<UnityEngine.Vector4> uvs, System.Int32[] Indices) : System.Void`  

```csharp
public System.Void DetermineRoom(System.Collections.Generic.List<UnityEngine.Vector4> uvs, System.Int32[] Indices);
```

- `public Merge(Game.ArtPipeline.InteriorMappingProcessor+Window window) : System.Boolean`  

```csharp
public System.Boolean Merge(Game.ArtPipeline.InteriorMappingProcessor+Window window);
```

- `public Split(System.Int32[] indices, UnityEngine.Vector3[] normals) : System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window>`  

```csharp
public System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window> Split(System.Int32[] indices, UnityEngine.Vector3[] normals);
```


## Nested types

- `Game.ArtPipeline.InteriorMappingProcessor+Window+<get_triangles>d__44`  

