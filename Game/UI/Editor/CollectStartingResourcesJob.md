# Game.UI.Editor.MapRequirementSystem+CollectStartingResourcesJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CollectStartingResourcesJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeArray<Unity.Entities.Entity> m_StartingTiles;
    public Unity.Entities.BufferLookup<Game.Areas.MapFeatureElement> m_MapFeatureElements;
    public Unity.Collections.NativeArray<System.Boolean> m_Results;

    private System.Void Check(Unity.Entities.Entity entity);
    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeArray<Unity.Entities.Entity> m_StartingTiles`  

```csharp
public Unity.Collections.NativeArray<Unity.Entities.Entity> m_StartingTiles;
```

- `public Unity.Entities.BufferLookup<Game.Areas.MapFeatureElement> m_MapFeatureElements`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.MapFeatureElement> m_MapFeatureElements;
```

- `public Unity.Collections.NativeArray<System.Boolean> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Boolean> m_Results;
```


## Methods

- `private Check(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void Check(Unity.Entities.Entity entity);
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


