# Game.Prefabs.DeliveryTruckSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct DeliveryTruckSelectData
{
    private Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> m_Items;

    public DeliveryTruckSelectData(Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> items);

    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Prefabs.DeliveryTruckSelectItem selectItem, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
    private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Unity.Entities.Entity prefab, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
    public System.Void GetCapacityRange(Game.Economy.Resource resources, System.Int32& min, System.Int32& max);
    public System.Boolean TrySelectItem(Unity.Mathematics.Random& random, Game.Economy.Resource resources, System.Int32 capacity, Game.Prefabs.DeliveryTruckSelectItem& item);
}
```


## Fields

- `private Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> m_Items`  

```csharp
private Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> m_Items;
```


## Constructors

- `public DeliveryTruckSelectData(Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> items)`  

```csharp
public DeliveryTruckSelectData(Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> items);
```


## Methods

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Prefabs.DeliveryTruckSelectItem selectItem, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Prefabs.DeliveryTruckSelectItem selectItem, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
```

- `private CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Unity.Entities.Entity prefab, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Unity.Entities.Entity prefab, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
```

- `public GetCapacityRange(Game.Economy.Resource resources, System.Int32& min, System.Int32& max) : System.Void`  

```csharp
public System.Void GetCapacityRange(Game.Economy.Resource resources, System.Int32& min, System.Int32& max);
```

- `public TrySelectItem(Unity.Mathematics.Random& random, Game.Economy.Resource resources, System.Int32 capacity, Game.Prefabs.DeliveryTruckSelectItem& item) : System.Boolean`  

```csharp
public System.Boolean TrySelectItem(Unity.Mathematics.Random& random, Game.Economy.Resource resources, System.Int32 capacity, Game.Prefabs.DeliveryTruckSelectItem& item);
```


