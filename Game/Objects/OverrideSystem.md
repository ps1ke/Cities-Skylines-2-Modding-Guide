# Game.Objects.OverrideSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OverrideSystem : Game.GameSystemBase
{
    private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.ComponentTypeSet m_OverriddenUpdatedSet;
    private Game.Objects.OverrideSystem+TypeHandle __TypeHandle;

    public OverrideSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle CollectUpdatedObjects(Unity.Collections.NativeList<Unity.Entities.Entity> updateObjectsList, Unity.Collections.NativeHashSet<Unity.Entities.Entity> objectSet);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  

```csharp
private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
```

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.ComponentTypeSet m_OverriddenUpdatedSet`  

```csharp
private Unity.Entities.ComponentTypeSet m_OverriddenUpdatedSet;
```

- `private Game.Objects.OverrideSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.OverrideSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public OverrideSystem()`  

```csharp
public OverrideSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CollectUpdatedObjects(Unity.Collections.NativeList<Unity.Entities.Entity> updateObjectsList, Unity.Collections.NativeHashSet<Unity.Entities.Entity> objectSet) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle CollectUpdatedObjects(Unity.Collections.NativeList<Unity.Entities.Entity> updateObjectsList, Unity.Collections.NativeHashSet<Unity.Entities.Entity> objectSet);
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

- `Game.Objects.OverrideSystem+TreeAction`  
- `Game.Objects.OverrideSystem+OverridableAction`  
- `Game.Objects.OverrideSystem+UpdateObjectOverrideJob`  
- `Game.Objects.OverrideSystem+FindUpdatedObjectsJob`  
- `Game.Objects.OverrideSystem+CollectObjectsJob`  
- `Game.Objects.OverrideSystem+CheckObjectOverrideJob`  
- `Game.Objects.OverrideSystem+TypeHandle`  

