# Game.Prefabs.Modes.GameModeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public class GameModeSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private System.String <overrideMode>k__BackingField;
    private System.String <currentModeName>k__BackingField;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.Modes.ModeSetting m_ModeSetting;
    private Game.Prefabs.Modes.ModeSetting m_NextMode;
    private Unity.Entities.EntityQuery m_ModeSettingQuery;
    private Unity.Entities.EntityQuery m_ModeInfoQuery;

    public System.String overrideMode { get; set; }
    public Game.Prefabs.Modes.ModeSetting modeSetting { get; }
    public System.String currentModeName { get; private set; }

    public GameModeSystem();

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo> GetGameModeInfo();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private System.String <overrideMode>k__BackingField`  

```csharp
private System.String <overrideMode>k__BackingField;
```

- `private System.String <currentModeName>k__BackingField`  

```csharp
private System.String <currentModeName>k__BackingField;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.Modes.ModeSetting m_ModeSetting`  

```csharp
private Game.Prefabs.Modes.ModeSetting m_ModeSetting;
```

- `private Game.Prefabs.Modes.ModeSetting m_NextMode`  

```csharp
private Game.Prefabs.Modes.ModeSetting m_NextMode;
```

- `private Unity.Entities.EntityQuery m_ModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModeSettingQuery;
```

- `private Unity.Entities.EntityQuery m_ModeInfoQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModeInfoQuery;
```


## Properties

- `public System.String overrideMode { get; set }`  

```csharp
public System.String overrideMode { get; set; }
```

- `public Game.Prefabs.Modes.ModeSetting modeSetting { get }`  

```csharp
public Game.Prefabs.Modes.ModeSetting modeSetting { get; }
```

- `public System.String currentModeName { get; private set }`  

```csharp
public System.String currentModeName { get; private set; }
```


## Constructors

- `public GameModeSystem()`  

```csharp
[Preserve]
	public GameModeSystem()
	{
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetGameModeInfo() : System.Collections.Generic.List<Game.Prefabs.Modes.GameModeInfo>`  

```csharp
public List<GameModeInfo> GetGameModeInfo()
	{
		List<GameModeInfo> list = new List<GameModeInfo>();
		NativeArray<Entity> nativeArray = m_ModeInfoQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			GameModeInfo gameModeInfo = m_PrefabSystem.GetPrefab<GameModeInfoPrefab>(entity).GetGameModeInfo();
			list.Add(gameModeInfo);
		}
		nativeArray.Dispose();
		return list;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ModeSettingQuery = GetEntityQuery(ComponentType.ReadOnly<GameModeSettingData>());
		m_ModeInfoQuery = GetEntityQuery(ComponentType.ReadOnly<GameModeInfoData>());
		currentModeName = string.Empty;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (overrideMode != null)
		{
			NativeArray<Entity> nativeArray = m_ModeSettingQuery.ToEntityArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity entity = nativeArray[i];
				ModeSetting prefab = m_PrefabSystem.GetPrefab<ModeSetting>(entity);
				if (prefab.prefab.name == overrideMode)
				{
					m_NextMode = prefab;
					break;
				}
			}
			nativeArray.Dispose();
			overrideMode = null;
		}
		if (m_ModeSetting != null)
		{
			COSystemBase.baseLog.Debug("Clean up " + m_ModeSetting.prefab.name);
			m_ModeSetting.RestoreDefaultData(base.EntityManager, m_PrefabSystem);
			m_ModeSetting = null;
		}
		m_ModeSetting = m_NextMode;
		m_NextMode = null;
		if (m_ModeSetting == null)
		{
			NativeArray<Entity> nativeArray2 = m_ModeSettingQuery.ToEntityArray(Allocator.TempJob);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				Entity entity2 = nativeArray2[j];
				ModeSetting prefab2 = m_PrefabSystem.GetPrefab<ModeSetting>(entity2);
				if (prefab2.prefab.name == "NormalMode")
				{
					m_ModeSetting = prefab2;
					break;
				}
			}
			nativeArray2.Dispose();
		}
		if (m_ModeSetting != null)
		{
			COSystemBase.baseLog.Debug("Apply " + m_ModeSetting.prefab.name);
			m_ModeSetting.StoreDefaultData(base.EntityManager, m_PrefabSystem);
			base.Dependency = m_ModeSetting.ApplyMode(base.EntityManager, m_PrefabSystem, base.Dependency);
			currentModeName = m_ModeSetting.prefab.name;
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
	}
```


