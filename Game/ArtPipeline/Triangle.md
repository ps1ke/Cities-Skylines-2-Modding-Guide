# Game.ArtPipeline.InteriorMappingProcessor+Triangle

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Triangle
{
    private System.Collections.Generic.HashSet<Game.ArtPipeline.InteriorMappingProcessor+Triangle> m_Neighbours;
    private UnityEngine.Bounds <bounds>k__BackingField;
    private System.Int32 <startIndex>k__BackingField;
    private System.Boolean <added>k__BackingField;

    public UnityEngine.Bounds bounds { get; private set; }
    public System.Int32 startIndex { get; private set; }
    public System.Boolean added { get; set; }
    public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> neighbours { get; }

    public Triangle(System.Int32 startIndex, System.Int32[] indices, UnityEngine.Vector3[] vertices);

    public System.Void AddNeighbour(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri);
}
```


## Fields

- `private System.Collections.Generic.HashSet<Game.ArtPipeline.InteriorMappingProcessor+Triangle> m_Neighbours`  

```csharp
private System.Collections.Generic.HashSet<Game.ArtPipeline.InteriorMappingProcessor+Triangle> m_Neighbours;
```

- `private UnityEngine.Bounds <bounds>k__BackingField`  

```csharp
private UnityEngine.Bounds <bounds>k__BackingField;
```

- `private System.Int32 <startIndex>k__BackingField`  

```csharp
private System.Int32 <startIndex>k__BackingField;
```

- `private System.Boolean <added>k__BackingField`  

```csharp
private System.Boolean <added>k__BackingField;
```


## Properties

- `public UnityEngine.Bounds bounds { get; private set }`  

```csharp
public UnityEngine.Bounds bounds { get; private set; }
```

- `public System.Int32 startIndex { get; private set }`  

```csharp
public System.Int32 startIndex { get; private set; }
```

- `public System.Boolean added { get; set }`  

```csharp
public System.Boolean added { get; set; }
```

- `public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> neighbours { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> neighbours { get; }
```


## Constructors

- `public Triangle(System.Int32 startIndex, System.Int32[] indices, UnityEngine.Vector3[] vertices)`  

```csharp
public Triangle(System.Int32 startIndex, System.Int32[] indices, UnityEngine.Vector3[] vertices);
```


## Methods

- `public AddNeighbour(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri) : System.Void`  

```csharp
public System.Void AddNeighbour(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri);
```


## Nested types

- `Game.ArtPipeline.InteriorMappingProcessor+Triangle+<get_neighbours>d__16`  

