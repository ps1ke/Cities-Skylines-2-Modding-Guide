# Game.Vehicles.ComponentsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ComponentsSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Vehicles.ComponentsSystem+TypeHandle __TypeHandle;

    public ComponentsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Vehicles.ComponentsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Vehicles.ComponentsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ComponentsSystem()`  

```csharp
public ComponentsSystem();
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

- `Game.Vehicles.ComponentsSystem+VehicleComponentsJob`  
- `Game.Vehicles.ComponentsSystem+TypeHandle`  

