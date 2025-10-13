# Game.Buildings.ZoneCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneCheckSystem : Game.GameSystemBase
{
    private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Game.Buildings.ZoneCheckSystem+TypeHandle __TypeHandle;

    public ZoneCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem`  

```csharp
private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Game.Buildings.ZoneCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ZoneCheckSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ZoneCheckSystem()`  

```csharp
public ZoneCheckSystem();
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

- `Game.Buildings.ZoneCheckSystem+FindSpawnableBuildingsJob`  
- `Game.Buildings.ZoneCheckSystem+CollectEntitiesJob`  
- `Game.Buildings.ZoneCheckSystem+CheckBuildingZonesJob`  
- `Game.Buildings.ZoneCheckSystem+TypeHandle`  

