# Game.UI.InGame.ChirpLinkSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ChirpLinkSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.UI.NameSystem m_NameSystem;
    private Unity.Entities.EntityQuery m_CreatedChirpQuery;
    private Unity.Entities.EntityQuery m_AllChirpsQuery;
    private Unity.Entities.EntityQuery m_DeletedChirpQuery;
    private Unity.Entities.EntityQuery m_UpdatedLinkEntityQuery;
    private Unity.Entities.EntityQuery m_DeletedLinkEntityQuery;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.UI.InGame.ChirpLinkSystem+CachedChirpData> m_CachedChirpData;

    public ChirpLinkSystem();

    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void Initialize();
    private System.Boolean LinkExists(Unity.Entities.DynamicBuffer<Game.Triggers.ChirpLink> links, Unity.Entities.Entity link);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RegisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Boolean TryGetData(Unity.Entities.Entity chirp, Game.UI.InGame.ChirpLinkSystem+CachedChirpData& data);
    private System.Void UnregisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity);
}
```


## Fields

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedChirpQuery;
```

- `private Unity.Entities.EntityQuery m_AllChirpsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllChirpsQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedChirpQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLinkEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLinkEntityQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedLinkEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedLinkEntityQuery;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.UI.InGame.ChirpLinkSystem+CachedChirpData> m_CachedChirpData`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.UI.InGame.ChirpLinkSystem+CachedChirpData> m_CachedChirpData;
```


## Constructors

- `public ChirpLinkSystem()`  

```csharp
[Preserve]
	public ChirpLinkSystem()
	{
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private Initialize() : System.Void`  

```csharp
private void Initialize()
	{
		m_CachedChirpData.Clear();
		NativeArray<Chirp> nativeArray = m_AllChirpsQuery.ToComponentDataArray<Chirp>(Allocator.TempJob);
		NativeArray<Entity> nativeArray2 = m_AllChirpsQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray2.Length; i++)
		{
			if (base.EntityManager.TryGetBuffer(nativeArray2[i], isReadOnly: true, out DynamicBuffer<ChirpEntity> buffer))
			{
				m_CachedChirpData[nativeArray2[i]] = new CachedChirpData(m_NameSystem, nativeArray[i], buffer);
				NativeArray<ChirpEntity> nativeArray3 = new NativeArray<ChirpEntity>(buffer.AsNativeArray(), Allocator.Temp);
				for (int j = 0; j < nativeArray3.Length; j++)
				{
					if (base.EntityManager.Exists(nativeArray3[j].m_Entity))
					{
						RegisterLink(nativeArray3[j].m_Entity, nativeArray2[i]);
					}
				}
				nativeArray3.Dispose();
			}
			else
			{
				m_CachedChirpData[nativeArray2[i]] = new CachedChirpData(m_NameSystem, nativeArray[i]);
			}
			if (base.EntityManager.Exists(nativeArray[i].m_Sender))
			{
				RegisterLink(nativeArray[i].m_Sender, nativeArray2[i]);
			}
		}
		nativeArray2.Dispose();
		nativeArray.Dispose();
	}
```

- `private LinkExists(Unity.Entities.DynamicBuffer<Game.Triggers.ChirpLink> links, Unity.Entities.Entity link) : System.Boolean`  

```csharp
private bool LinkExists(DynamicBuffer<ChirpLink> links, Entity link)
	{
		for (int i = 0; i < links.Length; i++)
		{
			if (links[i].m_Chirp == link)
			{
				return true;
			}
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_CreatedChirpQuery = GetEntityQuery(ComponentType.ReadOnly<Chirp>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Deleted>());
		m_AllChirpsQuery = GetEntityQuery(ComponentType.ReadOnly<Chirp>(), ComponentType.Exclude<Deleted>());
		m_DeletedChirpQuery = GetEntityQuery(ComponentType.ReadOnly<Chirp>(), ComponentType.ReadOnly<Deleted>());
		m_UpdatedLinkEntityQuery = GetEntityQuery(ComponentType.ReadOnly<ChirpLink>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>());
		m_DeletedLinkEntityQuery = GetEntityQuery(ComponentType.ReadOnly<ChirpLink>(), ComponentType.ReadOnly<Deleted>());
		m_CachedChirpData = new Dictionary<Entity, CachedChirpData>();
		RequireAnyForUpdate(m_CreatedChirpQuery, m_UpdatedLinkEntityQuery, m_DeletedLinkEntityQuery, m_DeletedChirpQuery);
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (m_CachedChirpData.Count == 0)
		{
			Initialize();
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_CreatedChirpQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = m_CreatedChirpQuery.ToEntityArray(Allocator.TempJob);
			NativeArray<Chirp> nativeArray2 = m_CreatedChirpQuery.ToComponentDataArray<Chirp>(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (base.EntityManager.TryGetBuffer(nativeArray[i], isReadOnly: true, out DynamicBuffer<ChirpEntity> buffer))
				{
					m_CachedChirpData[nativeArray[i]] = new CachedChirpData(m_NameSystem, nativeArray2[i], buffer);
					NativeArray<ChirpEntity> nativeArray3 = new NativeArray<ChirpEntity>(buffer.AsNativeArray(), Allocator.Temp);
					for (int j = 0; j < nativeArray3.Length; j++)
					{
						if (base.EntityManager.Exists(nativeArray3[j].m_Entity))
						{
							RegisterLink(nativeArray3[j].m_Entity, nativeArray[i]);
						}
					}
					nativeArray3.Dispose();
				}
				else
				{
					m_CachedChirpData[nativeArray[i]] = new CachedChirpData(m_NameSystem, nativeArray2[i]);
				}
				if (base.EntityManager.Exists(nativeArray2[i].m_Sender))
				{
					RegisterLink(nativeArray2[i].m_Sender, nativeArray[i]);
				}
			}
			nativeArray.Dispose();
			nativeArray2.Dispose();
		}
		if (!m_UpdatedLinkEntityQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray4 = m_UpdatedLinkEntityQuery.ToEntityArray(Allocator.TempJob);
			for (int k = 0; k < nativeArray4.Length; k++)
			{
				DynamicBuffer<ChirpLink> buffer2 = base.EntityManager.GetBuffer<ChirpLink>(nativeArray4[k], isReadOnly: true);
				for (int l = 0; l < buffer2.Length; l++)
				{
					if (m_CachedChirpData.TryGetValue(buffer2[l].m_Chirp, out var value))
					{
						m_CachedChirpData[buffer2[l].m_Chirp] = value.Update(m_NameSystem, nativeArray4[k]);
					}
				}
			}
			nativeArray4.Dispose();
		}
		if (!m_DeletedLinkEntityQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray5 = m_DeletedLinkEntityQuery.ToEntityArray(Allocator.TempJob);
			for (int m = 0; m < nativeArray5.Length; m++)
			{
				DynamicBuffer<ChirpLink> buffer3 = base.EntityManager.GetBuffer<ChirpLink>(nativeArray5[m], isReadOnly: true);
				for (int n = 0; n < buffer3.Length; n++)
				{
					if (m_CachedChirpData.TryGetValue(buffer3[n].m_Chirp, out var value2))
					{
						m_CachedChirpData[buffer3[n].m_Chirp] = value2.Remove(nativeArray5[m]);
					}
				}
			}
			nativeArray5.Dispose();
		}
		if (m_DeletedChirpQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<Entity> nativeArray6 = m_DeletedChirpQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<Chirp> nativeArray7 = m_DeletedChirpQuery.ToComponentDataArray<Chirp>(Allocator.TempJob);
		for (int num = 0; num < nativeArray6.Length; num++)
		{
			if (base.EntityManager.TryGetBuffer(nativeArray6[num], isReadOnly: true, out DynamicBuffer<ChirpEntity> buffer4))
			{
				NativeArray<ChirpEntity> nativeArray8 = new NativeArray<ChirpEntity>(buffer4.AsNativeArray(), Allocator.Temp);
				for (int num2 = 0; num2 < nativeArray8.Length; num2++)
				{
					UnregisterLink(nativeArray8[num2].m_Entity, nativeArray6[num]);
				}
				nativeArray8.Dispose();
			}
			UnregisterLink(nativeArray7[num].m_Sender, nativeArray6[num]);
			m_CachedChirpData.Remove(nativeArray6[num]);
		}
		nativeArray7.Dispose();
		nativeArray6.Dispose();
	}
```

- `private RegisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity) : System.Void`  

```csharp
private void RegisterLink(Entity linkEntity, Entity chirpEntity)
	{
		if (!base.EntityManager.TryGetBuffer(linkEntity, isReadOnly: false, out DynamicBuffer<ChirpLink> buffer))
		{
			buffer = base.EntityManager.AddBuffer<ChirpLink>(linkEntity);
		}
		if (!LinkExists(buffer, chirpEntity))
		{
			buffer.Add(new ChirpLink
			{
				m_Chirp = chirpEntity
			});
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_CachedChirpData.Clear();
	}
```

- `public TryGetData(Unity.Entities.Entity chirp, Game.UI.InGame.ChirpLinkSystem+CachedChirpData& data) : System.Boolean`  

```csharp
public bool TryGetData(Entity chirp, out CachedChirpData data)
	{
		if (m_CachedChirpData.TryGetValue(chirp, out data))
		{
			return true;
		}
		return false;
	}
```

- `private UnregisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity) : System.Void`  

```csharp
private void UnregisterLink(Entity linkEntity, Entity chirpEntity)
	{
		if (!base.EntityManager.TryGetBuffer(linkEntity, isReadOnly: false, out DynamicBuffer<ChirpLink> buffer))
		{
			return;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i].m_Chirp == chirpEntity)
			{
				buffer.RemoveAt(i);
				break;
			}
		}
		if (buffer.Length == 0)
		{
			base.EntityManager.RemoveComponent<ChirpLink>(linkEntity);
		}
	}
```


## Nested types

- `Game.UI.InGame.ChirpLinkSystem+CachedChirpData`  
- `Game.UI.InGame.ChirpLinkSystem+CachedEntityName`  

