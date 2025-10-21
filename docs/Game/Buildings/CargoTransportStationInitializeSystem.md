# Game.Buildings.CargoTransportStationInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CargoTransportStationInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Additions;
    private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
    private Game.Buildings.CargoTransportStationInitializeSystem+TypeHandle __TypeHandle;

    public CargoTransportStationInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Additions`  

```csharp
private Unity.Entities.EntityQuery m_Additions;
```

- `private Game.Common.ModificationBarrier5 m_EndFrameBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
```

- `private Game.Buildings.CargoTransportStationInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.CargoTransportStationInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CargoTransportStationInitializeSystem()`  

```csharp
public CargoTransportStationInitializeSystem();
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

- `Game.Buildings.CargoTransportStationInitializeSystem+InitializeCargoTransportStationJob`  
- `Game.Buildings.CargoTransportStationInitializeSystem+TypeHandle`  

