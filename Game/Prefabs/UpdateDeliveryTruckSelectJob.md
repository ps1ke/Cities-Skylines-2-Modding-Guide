# Game.Prefabs.UpdateDeliveryTruckSelectJob

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UpdateDeliveryTruckSelectJob : Unity.Jobs.IJob
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.DeliveryTruckData> m_DeliveryTruckDataType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    public Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    public Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems;

    private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData);
    private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData);
    private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData forthData);
    private System.Void CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData);
    private System.Void CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData);
    private System.Void CheckTrailers(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData);
    public System.Void Execute();
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.DeliveryTruckData> m_DeliveryTruckDataType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.DeliveryTruckData> m_DeliveryTruckDataType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
```

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
```

- `public Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  

```csharp
public Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
```

- `public Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems`  

```csharp
public Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems;
```


## Methods

- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData) : System.Void`  

```csharp
private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData);
```

- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData) : System.Void`  

```csharp
private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData);
```

- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData forthData) : System.Void`  

```csharp
private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData forthData);
```

- `private CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData) : System.Void`  

```csharp
private System.Void CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData);
```

- `private CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData) : System.Void`  

```csharp
private System.Void CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData);
```

- `private CheckTrailers(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData) : System.Void`  

```csharp
private System.Void CheckTrailers(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData);
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


## Nested types

- `Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData`  

