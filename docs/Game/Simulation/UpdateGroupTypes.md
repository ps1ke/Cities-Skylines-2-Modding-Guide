# Game.Simulation.UpdateGroupSystem+UpdateGroupTypes

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct UpdateGroupTypes
{
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Moving> m_MovingType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Stopped> m_StoppedType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Plant> m_PlantType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType;
    public Unity.Entities.ComponentTypeHandle<Game.Buildings.Extension> m_ExtensionType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Node> m_NodeType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_EdgeType;
    public Unity.Entities.ComponentTypeHandle<Game.Net.Lane> m_LaneType;
    public Unity.Entities.ComponentTypeHandle<Game.Companies.CompanyData> m_CompanyType;
    public Unity.Entities.ComponentTypeHandle<Game.Citizens.Household> m_HouseholdType;
    public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType;
    public Unity.Entities.ComponentTypeHandle<Game.Citizens.HouseholdPet> m_HouseholdPetType;
    public Unity.Entities.ComponentTypeHandle<Game.Creatures.CurrentVehicle> m_CurrentVehicleType;

    public UpdateGroupTypes(Unity.Entities.SystemBase system);

    public System.Void Update(Unity.Entities.SystemBase system);
}
```


## Fields

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Moving> m_MovingType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Moving> m_MovingType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Stopped> m_StoppedType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Stopped> m_StoppedType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Plant> m_PlantType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Plant> m_PlantType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Buildings.Extension> m_ExtensionType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Buildings.Extension> m_ExtensionType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Node> m_NodeType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Node> m_NodeType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_EdgeType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Edge> m_EdgeType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Net.Lane> m_LaneType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Net.Lane> m_LaneType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Companies.CompanyData> m_CompanyType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Companies.CompanyData> m_CompanyType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Household> m_HouseholdType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Citizens.Household> m_HouseholdType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Citizens.Citizen> m_CitizenType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Citizens.HouseholdPet> m_HouseholdPetType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Citizens.HouseholdPet> m_HouseholdPetType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Creatures.CurrentVehicle> m_CurrentVehicleType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Creatures.CurrentVehicle> m_CurrentVehicleType;
```


## Constructors

- `public UpdateGroupTypes(Unity.Entities.SystemBase system)`  

```csharp
public UpdateGroupTypes(Unity.Entities.SystemBase system);
```


## Methods

- `public Update(Unity.Entities.SystemBase system) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system);
```


