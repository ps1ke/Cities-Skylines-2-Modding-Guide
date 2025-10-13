# Game.Prefabs.VehicleCapacitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleCapacitySystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_DeliveryTruckQuery;
    private Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems;
    private Unity.Jobs.JobHandle m_WriteDependency;
    private Game.Prefabs.VehicleSelectRequirementData m_VehicleSelectRequirementData;
    private System.Boolean m_RequireUpdate;
    private Game.Prefabs.VehicleCapacitySystem+TypeHandle __TypeHandle;

    public VehicleCapacitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Prefabs.DeliveryTruckSelectData GetDeliveryTruckSelectData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_DeliveryTruckQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeliveryTruckQuery;
```

- `private Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems;
```

- `private Unity.Jobs.JobHandle m_WriteDependency`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependency;
```

- `private Game.Prefabs.VehicleSelectRequirementData m_VehicleSelectRequirementData`  

```csharp
private Game.Prefabs.VehicleSelectRequirementData m_VehicleSelectRequirementData;
```

- `private System.Boolean m_RequireUpdate`  

```csharp
private System.Boolean m_RequireUpdate;
```

- `private Game.Prefabs.VehicleCapacitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.VehicleCapacitySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public VehicleCapacitySystem()`  

```csharp
public VehicleCapacitySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetDeliveryTruckSelectData() : Game.Prefabs.DeliveryTruckSelectData`  

```csharp
public Game.Prefabs.DeliveryTruckSelectData GetDeliveryTruckSelectData();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
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

- `Game.Prefabs.VehicleCapacitySystem+TypeHandle`  

