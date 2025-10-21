# Game.Areas.CurrentDistrictSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CurrentDistrictSystem : Game.GameSystemBase
{
    private Game.Areas.UpdateCollectSystem m_UpdateCollectSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CurrentDistrictQuery;
    private Game.Areas.CurrentDistrictSystem+TypeHandle __TypeHandle;

    public CurrentDistrictSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Areas.UpdateCollectSystem m_UpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_UpdateCollectSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CurrentDistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_CurrentDistrictQuery;
```

- `private Game.Areas.CurrentDistrictSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.CurrentDistrictSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CurrentDistrictSystem()`  

```csharp
public CurrentDistrictSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Areas.CurrentDistrictSystem+FindUpdatedDistrictItemsJob`  
- `Game.Areas.CurrentDistrictSystem+CollectUpdatedDistrictItemsJob`  
- `Game.Areas.CurrentDistrictSystem+FindDistrictParallelJob`  
- `Game.Areas.CurrentDistrictSystem+FindDistrictChunkJob`  
- `Game.Areas.CurrentDistrictSystem+DistrictIterator`  
- `Game.Areas.CurrentDistrictSystem+TypeHandle`  

