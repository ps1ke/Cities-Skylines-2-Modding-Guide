# Game.Vehicles.ReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ReferencesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Objects.SearchSystem m_SearchSystem;
    private Unity.Entities.EntityQuery m_CarQuery;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityQuery m_LayoutQuery;
    private Game.Vehicles.ReferencesSystem+TypeHandle __TypeHandle;

    public ReferencesSystem();

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

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Unity.Entities.EntityQuery m_CarQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarQuery;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.EntityQuery m_LayoutQuery`  

```csharp
private Unity.Entities.EntityQuery m_LayoutQuery;
```

- `private Game.Vehicles.ReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Vehicles.ReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ReferencesSystem()`  

```csharp
public ReferencesSystem();
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

- `Game.Vehicles.ReferencesSystem+InitializeCurrentLaneJob`  
- `Game.Vehicles.ReferencesSystem+UpdateLayoutReferencesJob`  
- `Game.Vehicles.ReferencesSystem+UpdateVehicleReferencesJob`  
- `Game.Vehicles.ReferencesSystem+TypeHandle`  

