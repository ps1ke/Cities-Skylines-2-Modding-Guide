# Game.ArtPipeline.Preview.MeshAnalyzer

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class MeshAnalyzer
{
    private System.Single m_FloorHeight;
    private Game.ArtPipeline.Preview.MeshAnalyzer+ShowType m_ShowType;
    private System.Collections.Generic.List<Game.ArtPipeline.Preview.MeshAnalyzer+MeshInfo> m_MeshInfos;

    public Game.ArtPipeline.Preview.MeshAnalyzer+ShowType showType { get; set; }

    public MeshAnalyzer();

    public System.Void Analyze(UnityEngine.GameObject root);
    private static System.Int32 GetTriangleStart(System.Int32 i);
    public System.Void Render();
    private static System.Single SnapCeilValue(System.Single input, System.Single factor);
    private static System.Single SnapFloorValue(System.Single input, System.Single factor);
    private static System.Single SnapValue(System.Single input, System.Single factor);
}
```


## Fields

- `private System.Single m_FloorHeight`  

```csharp
private System.Single m_FloorHeight;
```

- `private Game.ArtPipeline.Preview.MeshAnalyzer+ShowType m_ShowType`  

```csharp
private Game.ArtPipeline.Preview.MeshAnalyzer+ShowType m_ShowType;
```

- `private System.Collections.Generic.List<Game.ArtPipeline.Preview.MeshAnalyzer+MeshInfo> m_MeshInfos`  

```csharp
private System.Collections.Generic.List<Game.ArtPipeline.Preview.MeshAnalyzer+MeshInfo> m_MeshInfos;
```


## Properties

- `public Game.ArtPipeline.Preview.MeshAnalyzer+ShowType showType { get; set }`  

```csharp
public Game.ArtPipeline.Preview.MeshAnalyzer+ShowType showType { get; set; }
```


## Constructors

- `public MeshAnalyzer()`  

```csharp
public MeshAnalyzer();
```


## Methods

- `public Analyze(UnityEngine.GameObject root) : System.Void`  

```csharp
public System.Void Analyze(UnityEngine.GameObject root);
```

- `private static GetTriangleStart(System.Int32 i) : System.Int32`  

```csharp
private static System.Int32 GetTriangleStart(System.Int32 i);
```

- `public Render() : System.Void`  

```csharp
public System.Void Render();
```

- `private static SnapCeilValue(System.Single input, System.Single factor) : System.Single`  

```csharp
private static System.Single SnapCeilValue(System.Single input, System.Single factor);
```

- `private static SnapFloorValue(System.Single input, System.Single factor) : System.Single`  

```csharp
private static System.Single SnapFloorValue(System.Single input, System.Single factor);
```

- `private static SnapValue(System.Single input, System.Single factor) : System.Single`  

```csharp
private static System.Single SnapValue(System.Single input, System.Single factor);
```


## Nested types

- `Game.ArtPipeline.Preview.MeshAnalyzer+ShowType`  
- `Game.ArtPipeline.Preview.MeshAnalyzer+Triangle`  
- `Game.ArtPipeline.Preview.MeshAnalyzer+Island`  
- `Game.ArtPipeline.Preview.MeshAnalyzer+Room`  
- `Game.ArtPipeline.Preview.MeshAnalyzer+Floor`  
- `Game.ArtPipeline.Preview.MeshAnalyzer+MeshInfo`  

