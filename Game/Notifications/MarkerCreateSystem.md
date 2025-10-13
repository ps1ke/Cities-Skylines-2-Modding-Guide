# Game.Notifications.MarkerCreateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MarkerCreateSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_EntityQuery;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_IconQuery;
    private System.UInt32 m_TransportTypeMask;
    private System.UInt32 m_BuildingTypeMask;
    private System.UInt32 m_BuildingStatusTypeMask;
    private System.UInt32 m_VehicleTypeMask;
    private System.UInt32 m_MarkerTypeMask;
    private System.Boolean m_Loaded;
    private Game.Notifications.MarkerCreateSystem+TypeHandle __TypeHandle;

    public MarkerCreateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
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

- `private Unity.Entities.EntityQuery m_EntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_EntityQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private System.UInt32 m_TransportTypeMask`  

```csharp
private System.UInt32 m_TransportTypeMask;
```

- `private System.UInt32 m_BuildingTypeMask`  

```csharp
private System.UInt32 m_BuildingTypeMask;
```

- `private System.UInt32 m_BuildingStatusTypeMask`  

```csharp
private System.UInt32 m_BuildingStatusTypeMask;
```

- `private System.UInt32 m_VehicleTypeMask`  

```csharp
private System.UInt32 m_VehicleTypeMask;
```

- `private System.UInt32 m_MarkerTypeMask`  

```csharp
private System.UInt32 m_MarkerTypeMask;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Notifications.MarkerCreateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Notifications.MarkerCreateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MarkerCreateSystem()`  

```csharp
public MarkerCreateSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
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

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Notifications.MarkerCreateSystem+MarkerCreateJob`  
- `Game.Notifications.MarkerCreateSystem+TypeHandle`  

