# Game.Net.OutsideConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OutsideConnectionSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_ConnectionQuery;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private System.Boolean m_Regenerate;
    private Game.Net.OutsideConnectionSystem+TypeHandle __TypeHandle;

    public OutsideConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context context);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_ConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private System.Boolean m_Regenerate`  

```csharp
private System.Boolean m_Regenerate;
```

- `private Game.Net.OutsideConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.OutsideConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public OutsideConnectionSystem()`  

```csharp
public OutsideConnectionSystem();
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context context);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Net.OutsideConnectionSystem+ConnectionType`  
- `Game.Net.OutsideConnectionSystem+NodeData`  
- `Game.Net.OutsideConnectionSystem+LaneData`  
- `Game.Net.OutsideConnectionSystem+UpdateOutsideConnectionsJob`  
- `Game.Net.OutsideConnectionSystem+TypeHandle`  

