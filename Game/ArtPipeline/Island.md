# Game.ArtPipeline.InteriorMappingProcessor+Island

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Island
{
    private System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Triangle> m_Triangles;

    public Game.ArtPipeline.InteriorMappingProcessor+Triangle first { get; }
    public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> triangles { get; }

    public Island();

    private System.Void AddAndSetAdded(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri);
    public System.Void RecursiveAdd(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri);
}
```


## Fields

- `private System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Triangle> m_Triangles`  

```csharp
private System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Triangle> m_Triangles;
```


## Properties

- `public Game.ArtPipeline.InteriorMappingProcessor+Triangle first { get }`  

```csharp
public Game.ArtPipeline.InteriorMappingProcessor+Triangle first { get; }
```

- `public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> triangles { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> triangles { get; }
```


## Constructors

- `public Island()`  

```csharp
public Island();
```


## Methods

- `private AddAndSetAdded(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri) : System.Void`  

```csharp
private System.Void AddAndSetAdded(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri);
```

- `public RecursiveAdd(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri) : System.Void`  

```csharp
public System.Void RecursiveAdd(Game.ArtPipeline.InteriorMappingProcessor+Triangle tri);
```


## Nested types

- `Game.ArtPipeline.InteriorMappingProcessor+Island+<get_triangles>d__6`  

