# Game.Rendering.CompleteRenderingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class CompleteRenderingSystem : Game.GameSystemBase
{
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
    private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
    private Game.Rendering.WindTextureSystem m_WindTextureSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem;

    public CompleteRenderingSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem`  

```csharp
private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
```

- `private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem`  

```csharp
private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
```

- `private Game.Rendering.WindTextureSystem m_WindTextureSystem`  

```csharp
private Game.Rendering.WindTextureSystem m_WindTextureSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem`  

```csharp
private Game.Rendering.OverlayInfomodeSystem m_OverlayInfomodeSystem;
```


## Constructors

- `public CompleteRenderingSystem()`  

```csharp
public CompleteRenderingSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


