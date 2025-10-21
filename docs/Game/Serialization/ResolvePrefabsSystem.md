# Game.Serialization.ResolvePrefabsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResolvePrefabsSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
    private Unity.Entities.EntityQuery m_ActualPrefabQuery;
    private Unity.Entities.EntityQuery m_EnabledLoadedPrefabQuery;
    private Unity.Entities.EntityQuery m_AllLoadedPrefabQuery;
    private Unity.Entities.EntityQuery m_LoadedZonePrefabQuery;
    private Unity.Entities.EntityQuery m_LoadedZoneCellQuery;
    private Unity.Entities.EntityQuery m_ActualBudgetQuery;
    private Game.Serialization.ResolvePrefabsSystem+TypeHandle __TypeHandle;

    public ResolvePrefabsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddOrRemoveComponent(Game.Serialization.ResolvePrefabsSystem+ComponentModification componentModification, Game.Prefabs.PrefabComponents mask, Unity.Entities.ComponentType type);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  

```csharp
private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
```

- `private Unity.Entities.EntityQuery m_ActualPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActualPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_EnabledLoadedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_EnabledLoadedPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_AllLoadedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllLoadedPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_LoadedZonePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedZonePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_LoadedZoneCellQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedZoneCellQuery;
```

- `private Unity.Entities.EntityQuery m_ActualBudgetQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActualBudgetQuery;
```

- `private Game.Serialization.ResolvePrefabsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ResolvePrefabsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResolvePrefabsSystem()`  

```csharp
public ResolvePrefabsSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AddOrRemoveComponent(Game.Serialization.ResolvePrefabsSystem+ComponentModification componentModification, Game.Prefabs.PrefabComponents mask, Unity.Entities.ComponentType type) : System.Void`  

```csharp
private System.Void AddOrRemoveComponent(Game.Serialization.ResolvePrefabsSystem+ComponentModification componentModification, Game.Prefabs.PrefabComponents mask, Unity.Entities.ComponentType type);
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

- `Game.Serialization.ResolvePrefabsSystem+ComponentModification`  
- `Game.Serialization.ResolvePrefabsSystem+FillLoadedPrefabsJob`  
- `Game.Serialization.ResolvePrefabsSystem+CheckActualPrefabsJob`  
- `Game.Serialization.ResolvePrefabsSystem+CopyBudgetDataJob`  
- `Game.Serialization.ResolvePrefabsSystem+FillZoneTypeArrayJob`  
- `Game.Serialization.ResolvePrefabsSystem+FixZoneTypeJob`  
- `Game.Serialization.ResolvePrefabsSystem+TypeHandle`  

