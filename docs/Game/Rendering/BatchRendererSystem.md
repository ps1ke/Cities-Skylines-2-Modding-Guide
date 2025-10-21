# Game.Rendering.BatchRendererSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class BatchRendererSystem : Game.GameSystemBase
{
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;

    public BatchRendererSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```


## Constructors

- `public BatchRendererSystem()`  

```csharp
public BatchRendererSystem();
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


## Nested types

- `Game.Rendering.BatchRendererSystem+ClearUpdatedMetaDatasJob`  

