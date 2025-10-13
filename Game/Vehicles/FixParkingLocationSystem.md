# Game.Vehicles.FixParkingLocationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FixParkingLocationSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Unity.Entities.EntityQuery m_FixQuery;
    private Game.Vehicles.FixParkingLocationSystem+TypeHandle __TypeHandle;

    public FixParkingLocationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Unity.Entities.EntityQuery m_FixQuery`  

```csharp
private Unity.Entities.EntityQuery m_FixQuery;
```

- `private Game.Vehicles.FixParkingLocationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Vehicles.FixParkingLocationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FixParkingLocationSystem()`  

```csharp
public FixParkingLocationSystem();
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

- `Game.Vehicles.FixParkingLocationSystem+CollectParkedCarsJob`  
- `Game.Vehicles.FixParkingLocationSystem+FixParkingLocationJob`  
- `Game.Vehicles.FixParkingLocationSystem+TypeHandle`  

