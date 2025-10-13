# Game.Prefabs.VehicleCarriageElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct VehicleCarriageElement : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Mathematics.int2 m_Count;
    public Game.Prefabs.VehicleCarriageDirection m_Direction;

    public VehicleCarriageElement(Unity.Entities.Entity carriage, System.Int32 minCount, System.Int32 maxCount, Game.Prefabs.VehicleCarriageDirection direction);

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Mathematics.int2 m_Count`  

```csharp
public Unity.Mathematics.int2 m_Count;
```

- `public Game.Prefabs.VehicleCarriageDirection m_Direction`  

```csharp
public Game.Prefabs.VehicleCarriageDirection m_Direction;
```


## Constructors

- `public VehicleCarriageElement(Unity.Entities.Entity carriage, System.Int32 minCount, System.Int32 maxCount, Game.Prefabs.VehicleCarriageDirection direction)`  

```csharp
public VehicleCarriageElement(Unity.Entities.Entity carriage, System.Int32 minCount, System.Int32 maxCount, Game.Prefabs.VehicleCarriageDirection direction);
```


