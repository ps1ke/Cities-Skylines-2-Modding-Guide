# Game.Serialization.SerializerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class SerializerSystem : Game.GameSystemBase
{
    private System.Int32 <totalSize>k__BackingField;
    private Game.Serialization.SaveGameSystem m_SaveGameSystem;
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Serialization.WriteSystem m_WriteSystem;
    private Game.Serialization.ReadSystem m_ReadSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Colossal.Serialization.Entities.ComponentSerializerLibrary m_ComponentSerializerLibrary;
    private Colossal.Serialization.Entities.SystemSerializerLibrary m_SystemSerializerLibrary;
    private Unity.Entities.EntityQuery m_Query;

    public Colossal.Serialization.Entities.ComponentSerializerLibrary componentLibrary { get; }
    public Colossal.Serialization.Entities.SystemSerializerLibrary systemLibrary { get; }
    public System.Int32 totalSize { get; set; }

    public SerializerSystem();

    private System.Void CreateQuery(System.Collections.Generic.IEnumerable<Unity.Entities.ComponentType> serializableComponents);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void SetDirty();
}
```


## Fields

- `private System.Int32 <totalSize>k__BackingField`  

```csharp
private System.Int32 <totalSize>k__BackingField;
```

- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  

```csharp
private Game.Serialization.SaveGameSystem m_SaveGameSystem;
```

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Serialization.WriteSystem m_WriteSystem`  

```csharp
private Game.Serialization.WriteSystem m_WriteSystem;
```

- `private Game.Serialization.ReadSystem m_ReadSystem`  

```csharp
private Game.Serialization.ReadSystem m_ReadSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Colossal.Serialization.Entities.ComponentSerializerLibrary m_ComponentSerializerLibrary`  

```csharp
private Colossal.Serialization.Entities.ComponentSerializerLibrary m_ComponentSerializerLibrary;
```

- `private Colossal.Serialization.Entities.SystemSerializerLibrary m_SystemSerializerLibrary`  

```csharp
private Colossal.Serialization.Entities.SystemSerializerLibrary m_SystemSerializerLibrary;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```


## Properties

- `public Colossal.Serialization.Entities.ComponentSerializerLibrary componentLibrary { get }`  

```csharp
public Colossal.Serialization.Entities.ComponentSerializerLibrary componentLibrary { get; }
```

- `public Colossal.Serialization.Entities.SystemSerializerLibrary systemLibrary { get }`  

```csharp
public Colossal.Serialization.Entities.SystemSerializerLibrary systemLibrary { get; }
```

- `public System.Int32 totalSize { get; set }`  

```csharp
public System.Int32 totalSize { get; set; }
```


## Constructors

- `public SerializerSystem()`  

```csharp
[Preserve]
	public SerializerSystem()
	{
	}
```


## Methods

- `private CreateQuery(System.Collections.Generic.IEnumerable<Unity.Entities.ComponentType> serializableComponents) : System.Void`  

```csharp
private void CreateQuery(IEnumerable<ComponentType> serializableComponents)
	{
		HashSet<ComponentType> hashSet = new HashSet<ComponentType>
		{
			ComponentType.ReadOnly<LoadedIndex>(),
			ComponentType.ReadOnly<PrefabRef>(),
			ComponentType.ReadOnly<ElectricityFlowNode>(),
			ComponentType.ReadOnly<ElectricityFlowEdge>(),
			ComponentType.ReadOnly<WaterPipeNode>(),
			ComponentType.ReadOnly<WaterPipeEdge>(),
			ComponentType.ReadOnly<ServiceRequest>(),
			ComponentType.ReadOnly<Game.Simulation.WaterSourceData>(),
			ComponentType.ReadOnly<Game.City.City>(),
			ComponentType.ReadOnly<SchoolSeeker>(),
			ComponentType.ReadOnly<JobSeeker>(),
			ComponentType.ReadOnly<CityStatistic>(),
			ComponentType.ReadOnly<ServiceBudgetData>(),
			ComponentType.ReadOnly<FloodCounterData>(),
			ComponentType.ReadOnly<CoordinatedMeeting>(),
			ComponentType.ReadOnly<LookingForPartner>(),
			ComponentType.ReadOnly<AtmosphereData>(),
			ComponentType.ReadOnly<BiomeData>(),
			ComponentType.ReadOnly<TimeData>()
		};
		foreach (ComponentType serializableComponent in serializableComponents)
		{
			hashSet.Add(ComponentType.ReadOnly(serializableComponent.TypeIndex));
		}
		m_Query = GetEntityQuery(new EntityQueryDesc
		{
			Any = hashSet.ToArray(),
			None = new ComponentType[5]
			{
				ComponentType.ReadOnly<NetCompositionData>(),
				ComponentType.ReadOnly<EffectInstance>(),
				ComponentType.ReadOnly<LivePath>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SaveGameSystem = base.World.GetOrCreateSystemManaged<SaveGameSystem>();
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_WriteSystem = base.World.GetOrCreateSystemManaged<WriteSystem>();
		m_ReadSystem = base.World.GetOrCreateSystemManaged<ReadSystem>();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		CreateQuery(Array.Empty<ComponentType>());
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		if (m_ComponentSerializerLibrary != null)
		{
			m_ComponentSerializerLibrary.Dispose();
		}
		if (m_SystemSerializerLibrary != null)
		{
			m_SystemSerializerLibrary.Dispose();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ComponentSerializerLibrary == null)
		{
			m_ComponentSerializerLibrary = new ComponentSerializerLibrary();
		}
		if (m_ComponentSerializerLibrary.isDirty)
		{
			m_ComponentSerializerLibrary.Initialize(this, out var serializableComponents);
			CreateQuery(serializableComponents);
		}
		if (m_SystemSerializerLibrary == null)
		{
			m_SystemSerializerLibrary = new SystemSerializerLibrary();
		}
		if (m_SystemSerializerLibrary.isDirty)
		{
			m_SystemSerializerLibrary.Initialize(base.World);
		}
		switch (m_UpdateSystem.currentPhase)
		{
		case SystemUpdatePhase.Serialize:
		{
			EntitySerializer<WriteBuffer> entitySerializer = new EntitySerializer<WriteBuffer>(base.EntityManager, m_ComponentSerializerLibrary, m_SystemSerializerLibrary, m_WriteSystem);
			try
			{
				totalSize = 0;
				Context context2 = m_SaveGameSystem.context;
				entitySerializer.Serialize<BinaryWriter, FormatTags>(context2, m_Query, BufferFormat.CompressedZStd, new ComponentType[1] { ComponentType.ReadWrite<PrefabData>() });
				break;
			}
			finally
			{
				entitySerializer.Dispose();
			}
		}
		case SystemUpdatePhase.Deserialize:
		{
			EntityDeserializer<ReadBuffer> entityDeserializer = new EntityDeserializer<ReadBuffer>(base.EntityManager, m_ComponentSerializerLibrary, m_SystemSerializerLibrary, m_ReadSystem);
			try
			{
				totalSize = 0;
				Context context = m_LoadGameSystem.context;
				bool num = entityDeserializer.Deserialize<BinaryReader, FormatTags>(ref context, Array.Empty<ComponentType>());
				COSystemBase.baseLog.InfoFormat("Serialized version: {0}", context.version);
				if (num)
				{
					string[] names = Enum.GetNames(typeof(FormatTags));
					FormatTags[] array = (FormatTags[])Enum.GetValues(typeof(FormatTags));
					List<string> list = new List<string>(names.Length);
					for (int i = 0; i < array.Length; i++)
					{
						if (context.format.Has(array[i]))
						{
							list.Add(names[i]);
						}
					}
					COSystemBase.baseLog.InfoFormat("Format tags: {0}", string.Join(", ", list));
				}
				else
				{
					Colossal.Hash128 instigatorGuid = context.instigatorGuid;
					Colossal.Serialization.Entities.Purpose purpose = context.purpose switch
					{
						Colossal.Serialization.Entities.Purpose.LoadMap => Colossal.Serialization.Entities.Purpose.NewMap, 
						Colossal.Serialization.Entities.Purpose.LoadGame => Colossal.Serialization.Entities.Purpose.NewGame, 
						_ => context.purpose, 
					};
					if (purpose != context.purpose)
					{
						context.Dispose();
						context = new Context(purpose, Version.current, instigatorGuid, Enum.GetNames(typeof(FormatTags)).Length, Allocator.Persistent);
					}
				}
				m_LoadGameSystem.context = context;
				break;
			}
			finally
			{
				entityDeserializer.Dispose();
			}
		}
		}
	}
```

- `public SetDirty() : System.Void`  

```csharp
public void SetDirty()
	{
		if (m_ComponentSerializerLibrary != null)
		{
			m_ComponentSerializerLibrary.SetDirty();
		}
		if (m_SystemSerializerLibrary != null)
		{
			m_SystemSerializerLibrary.SetDirty();
		}
	}
```


