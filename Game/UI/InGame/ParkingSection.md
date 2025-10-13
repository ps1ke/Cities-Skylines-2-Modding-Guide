# Game.UI.InGame.ParkingSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkingSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <parkingFee>k__BackingField;
    private System.Int32 <parkedCars>k__BackingField;
    private System.Int32 <parkingCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 parkingFee { private get; private set; }
    private System.Int32 parkedCars { private get; private set; }
    private System.Int32 parkingCapacity { private get; private set; }

    public ParkingSection();

    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& laneCount);
    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& laneCount);
    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& laneCount);
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <parkingFee>k__BackingField`  

```csharp
private System.Int32 <parkingFee>k__BackingField;
```

- `private System.Int32 <parkedCars>k__BackingField`  

```csharp
private System.Int32 <parkedCars>k__BackingField;
```

- `private System.Int32 <parkingCapacity>k__BackingField`  

```csharp
private System.Int32 <parkingCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 parkingFee { private get; private set }`  

```csharp
private System.Int32 parkingFee { private get; private set; }
```

- `private System.Int32 parkedCars { private get; private set }`  

```csharp
private System.Int32 parkedCars { private get; private set; }
```

- `private System.Int32 parkingCapacity { private get; private set }`  

```csharp
private System.Int32 parkingCapacity { private get; private set; }
```


## Constructors

- `public ParkingSection()`  

```csharp
[Preserve]
	public ParkingSection()
	{
	}
```


## Methods

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& laneCount) : System.Void`  

```csharp
private void CheckParkingLanes(DynamicBuffer<Game.Net.SubLane> subLanes, ref int laneCount)
	{
		for (int i = 0; i < subLanes.Length; i++)
		{
			Entity subLane = subLanes[i].m_SubLane;
			GarageLane component2;
			if (base.EntityManager.TryGetComponent<Game.Net.ParkingLane>(subLane, out var component))
			{
				if ((component.m_Flags & ParkingLaneFlags.VirtualLane) != 0)
				{
					continue;
				}
				Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(subLane).m_Prefab;
				Curve componentData = base.EntityManager.GetComponentData<Curve>(subLane);
				DynamicBuffer<LaneObject> buffer = base.EntityManager.GetBuffer<LaneObject>(subLane, isReadOnly: true);
				ParkingLaneData componentData2 = base.EntityManager.GetComponentData<ParkingLaneData>(prefab);
				if (componentData2.m_SlotInterval != 0f)
				{
					int parkingSlotCount = NetUtils.GetParkingSlotCount(componentData, component, componentData2);
					parkingCapacity += parkingSlotCount;
				}
				else
				{
					parkingCapacity = -1000000;
				}
				for (int j = 0; j < buffer.Length; j++)
				{
					if (base.EntityManager.HasComponent<ParkedCar>(buffer[j].m_LaneObject))
					{
						parkedCars++;
					}
				}
				parkingFee += component.m_ParkingFee;
				laneCount++;
			}
			else if (base.EntityManager.TryGetComponent<GarageLane>(subLane, out component2))
			{
				parkingCapacity += component2.m_VehicleCapacity;
				parkedCars += component2.m_VehicleCount;
				parkingFee += component2.m_ParkingFee;
				laneCount++;
			}
		}
	}
```

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& laneCount) : System.Void`  

```csharp
private void CheckParkingLanes(DynamicBuffer<Game.Net.SubLane> subLanes, ref int laneCount)
	{
		for (int i = 0; i < subLanes.Length; i++)
		{
			Entity subLane = subLanes[i].m_SubLane;
			GarageLane component2;
			if (base.EntityManager.TryGetComponent<Game.Net.ParkingLane>(subLane, out var component))
			{
				if ((component.m_Flags & ParkingLaneFlags.VirtualLane) != 0)
				{
					continue;
				}
				Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(subLane).m_Prefab;
				Curve componentData = base.EntityManager.GetComponentData<Curve>(subLane);
				DynamicBuffer<LaneObject> buffer = base.EntityManager.GetBuffer<LaneObject>(subLane, isReadOnly: true);
				ParkingLaneData componentData2 = base.EntityManager.GetComponentData<ParkingLaneData>(prefab);
				if (componentData2.m_SlotInterval != 0f)
				{
					int parkingSlotCount = NetUtils.GetParkingSlotCount(componentData, component, componentData2);
					parkingCapacity += parkingSlotCount;
				}
				else
				{
					parkingCapacity = -1000000;
				}
				for (int j = 0; j < buffer.Length; j++)
				{
					if (base.EntityManager.HasComponent<ParkedCar>(buffer[j].m_LaneObject))
					{
						parkedCars++;
					}
				}
				parkingFee += component.m_ParkingFee;
				laneCount++;
			}
			else if (base.EntityManager.TryGetComponent<GarageLane>(subLane, out component2))
			{
				parkingCapacity += component2.m_VehicleCapacity;
				parkedCars += component2.m_VehicleCount;
				parkingFee += component2.m_ParkingFee;
				laneCount++;
			}
		}
	}
```

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& laneCount) : System.Void`  

```csharp
private void CheckParkingLanes(DynamicBuffer<Game.Net.SubLane> subLanes, ref int laneCount)
	{
		for (int i = 0; i < subLanes.Length; i++)
		{
			Entity subLane = subLanes[i].m_SubLane;
			GarageLane component2;
			if (base.EntityManager.TryGetComponent<Game.Net.ParkingLane>(subLane, out var component))
			{
				if ((component.m_Flags & ParkingLaneFlags.VirtualLane) != 0)
				{
					continue;
				}
				Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(subLane).m_Prefab;
				Curve componentData = base.EntityManager.GetComponentData<Curve>(subLane);
				DynamicBuffer<LaneObject> buffer = base.EntityManager.GetBuffer<LaneObject>(subLane, isReadOnly: true);
				ParkingLaneData componentData2 = base.EntityManager.GetComponentData<ParkingLaneData>(prefab);
				if (componentData2.m_SlotInterval != 0f)
				{
					int parkingSlotCount = NetUtils.GetParkingSlotCount(componentData, component, componentData2);
					parkingCapacity += parkingSlotCount;
				}
				else
				{
					parkingCapacity = -1000000;
				}
				for (int j = 0; j < buffer.Length; j++)
				{
					if (base.EntityManager.HasComponent<ParkedCar>(buffer[j].m_LaneObject))
					{
						parkedCars++;
					}
				}
				parkingFee += component.m_ParkingFee;
				laneCount++;
			}
			else if (base.EntityManager.TryGetComponent<GarageLane>(subLane, out component2))
			{
				parkingCapacity += component2.m_VehicleCapacity;
				parkedCars += component2.m_VehicleCount;
				parkingFee += component2.m_ParkingFee;
				laneCount++;
			}
		}
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		int laneCount = 0;
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Game.Net.SubLane> buffer))
		{
			CheckParkingLanes(buffer, ref laneCount);
		}
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Game.Net.SubNet> buffer2))
		{
			CheckParkingLanes(buffer2, ref laneCount);
		}
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Game.Objects.SubObject> buffer3))
		{
			CheckParkingLanes(buffer3, ref laneCount);
		}
		if (laneCount != 0)
		{
			parkingFee /= laneCount;
		}
		if (parkingCapacity < 0)
		{
			parkingCapacity = 0;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("parkedCars");
		writer.Write(parkedCars);
		writer.PropertyName("parkingCapacity");
		writer.Write(parkingCapacity);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		parkingFee = 0;
		parkedCars = 0;
		parkingCapacity = 0;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.ParkingFacility>(selectedEntity);
	}
```


