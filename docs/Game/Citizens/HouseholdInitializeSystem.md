# Game.Citizens.HouseholdInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CarPrefabGroup;
    private Unity.Entities.EntityQuery m_CitizenPrefabGroup;
    private Unity.Entities.EntityQuery m_HouseholdPetPrefabGroup;
    private Unity.Entities.EntityQuery m_Additions;
    private Game.Common.ModificationBarrier4 m_EndFrameBarrier;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
    private Game.Citizens.HouseholdInitializeSystem+TypeHandle __TypeHandle;

    public HouseholdInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CarPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_CarPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_CitizenPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_CitizenPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_HouseholdPetPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPetPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_Additions`  

```csharp
private Unity.Entities.EntityQuery m_Additions;
```

- `private Game.Common.ModificationBarrier4 m_EndFrameBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_EndFrameBarrier;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  

```csharp
private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
```

- `private Game.Citizens.HouseholdInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.HouseholdInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdInitializeSystem()`  

```csharp
public HouseholdInitializeSystem();
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

- `Game.Citizens.HouseholdInitializeSystem+InitializeHouseholdJob`  
- `Game.Citizens.HouseholdInitializeSystem+TypeHandle`  

