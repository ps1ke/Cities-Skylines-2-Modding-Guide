# Game.Prefabs.VehicleInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.VehicleInitializeSystem+TypeHandle __TypeHandle;

    public VehicleInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.VehicleInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.VehicleInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public VehicleInitializeSystem()`  

```csharp
public VehicleInitializeSystem();
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

- `Game.Prefabs.VehicleInitializeSystem+InitializeVehiclesJob`  
- `Game.Prefabs.VehicleInitializeSystem+TypeHandle`  

