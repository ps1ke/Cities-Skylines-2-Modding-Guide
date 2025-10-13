# Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.InteriorMapping`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Island
{
    private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> m_Triangles;

    public Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle first { get; }
    public System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles { get; }

    public Island();

    private System.Void AddAndSetAdded(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle tri);
    public System.Void RecursiveAdd(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle tri);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> m_Triangles`  

```csharp
private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> m_Triangles;
```


## Properties

- `public Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle first { get }`  

```csharp
public Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle first { get; }
```

- `public System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles { get; }
```


## Constructors

- `public Island()`  

```csharp
public Island();
```


## Methods

- `private AddAndSetAdded(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle tri) : System.Void`  

```csharp
private System.Void AddAndSetAdded(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle tri);
```

- `public RecursiveAdd(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle tri) : System.Void`  

```csharp
public System.Void RecursiveAdd(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle tri);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island+<get_triangles>d__6`  

