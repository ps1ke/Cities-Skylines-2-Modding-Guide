# Game.Net.ConnectionWarningSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ConnectionWarningSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.EntityQuery m_NewGameQuery;
    private Unity.Entities.EntityQuery m_WaterConfigQuery;
    private Unity.Entities.EntityQuery m_ElectricityConfigQuery;
    private Unity.Entities.EntityQuery m_TrafficConfigQuery;
    private System.Boolean m_IsNewGame;
    private Game.Net.ConnectionWarningSystem+TypeHandle __TypeHandle;

    public ConnectionWarningSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private T GetConfigData<T>(Unity.Entities.EntityQuery query);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.EntityQuery m_NewGameQuery`  

```csharp
private Unity.Entities.EntityQuery m_NewGameQuery;
```

- `private Unity.Entities.EntityQuery m_WaterConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterConfigQuery;
```

- `private Unity.Entities.EntityQuery m_ElectricityConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ElectricityConfigQuery;
```

- `private Unity.Entities.EntityQuery m_TrafficConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrafficConfigQuery;
```

- `private System.Boolean m_IsNewGame`  

```csharp
private System.Boolean m_IsNewGame;
```

- `private Game.Net.ConnectionWarningSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.ConnectionWarningSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ConnectionWarningSystem()`  

```csharp
public ConnectionWarningSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetConfigData<T>(Unity.Entities.EntityQuery query) : T`  

```csharp
private T GetConfigData<T>(Unity.Entities.EntityQuery query);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Net.ConnectionWarningSystem+CollectOwnersJob`  
- `Game.Net.ConnectionWarningSystem+CollectOwnersJob2`  
- `Game.Net.ConnectionWarningSystem+PathfindElement`  
- `Game.Net.ConnectionWarningSystem+BufferElement`  
- `Game.Net.ConnectionWarningSystem+Connection`  
- `Game.Net.ConnectionWarningSystem+CheckOwnersJob`  
- `Game.Net.ConnectionWarningSystem+TypeHandle`  

