# Game.UI.InGame.DescriptionSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DescriptionSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private System.String <localeId>k__BackingField;
    private Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> m_LeisureDatas;
    private Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> m_LocalModifierDatas;
    private Unity.Collections.NativeList<Game.Prefabs.CityModifierData> m_CityModifierDatas;

    protected System.String group { protected get; }
    private System.String localeId { private get; private set; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }

    public DescriptionSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private System.String <localeId>k__BackingField`  

```csharp
private System.String <localeId>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> m_LeisureDatas`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> m_LeisureDatas;
```

- `private Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> m_LocalModifierDatas`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> m_LocalModifierDatas;
```

- `private Unity.Collections.NativeList<Game.Prefabs.CityModifierData> m_CityModifierDatas`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.CityModifierData> m_CityModifierDatas;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.String localeId { private get; private set }`  

```csharp
private System.String localeId { private get; private set; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```


## Constructors

- `public DescriptionSection()`  

```csharp
[Preserve]
	public DescriptionSection()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_LeisureDatas = new NativeList<LeisureProviderData>(10, Allocator.Persistent);
		m_LocalModifierDatas = new NativeList<LocalModifierData>(10, Allocator.Persistent);
		m_CityModifierDatas = new NativeList<CityModifierData>(10, Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_LeisureDatas.Dispose();
		m_LocalModifierDatas.Dispose();
		m_CityModifierDatas.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		m_PrefabUISystem.GetTitleAndDescription(selectedPrefab, out var _, out var descriptionId);
		localeId = descriptionId;
		if (base.EntityManager.TryGetBuffer(selectedPrefab, isReadOnly: true, out DynamicBuffer<LocalModifierData> buffer))
		{
			m_LocalModifierDatas.AddRange(buffer.AsNativeArray());
		}
		if (base.EntityManager.TryGetBuffer(selectedPrefab, isReadOnly: true, out DynamicBuffer<CityModifierData> buffer2))
		{
			m_CityModifierDatas.AddRange(buffer2.AsNativeArray());
		}
		if (base.EntityManager.TryGetComponent<LeisureProviderData>(selectedPrefab, out var component) && component.m_Efficiency > 0)
		{
			m_LeisureDatas.Add(in component);
		}
		if (!base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<InstalledUpgrade> buffer3))
		{
			return;
		}
		for (int i = 0; i < buffer3.Length; i++)
		{
			if (base.EntityManager.TryGetComponent<PrefabRef>(buffer3[i].m_Upgrade, out var component2))
			{
				if (base.EntityManager.TryGetBuffer(component2.m_Prefab, isReadOnly: true, out DynamicBuffer<LocalModifierData> buffer4))
				{
					LocalEffectSystem.AddToTempList(m_LocalModifierDatas, buffer4, disabled: false);
				}
				if (base.EntityManager.TryGetBuffer(component2.m_Prefab, isReadOnly: true, out DynamicBuffer<CityModifierData> buffer5))
				{
					CityModifierUpdateSystem.AddToTempList(m_CityModifierDatas, buffer5);
				}
				if (base.EntityManager.TryGetComponent<LeisureProviderData>(component2.m_Prefab, out var component3) && component3.m_Efficiency > 0)
				{
					LeisureSystem.AddToTempList(m_LeisureDatas, component3);
				}
			}
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
		writer.PropertyName("localeId");
		writer.Write(localeId);
		writer.PropertyName("effects");
		int num = 0;
		if (m_CityModifierDatas.Length > 0)
		{
			num++;
		}
		if (m_LocalModifierDatas.Length > 0)
		{
			num++;
		}
		if (m_LeisureDatas.Length > 0)
		{
			num++;
		}
		writer.ArrayBegin(num);
		if (m_CityModifierDatas.Length > 0)
		{
			PrefabUISystem.CityModifierBinder.Bind(writer, m_CityModifierDatas);
		}
		if (m_LocalModifierDatas.Length > 0)
		{
			PrefabUISystem.LocalModifierBinder.Bind(writer, m_LocalModifierDatas);
		}
		if (m_LeisureDatas.Length > 0)
		{
			PrefabUISystem.LeisureProviderBinder.Bind(writer, m_LeisureDatas);
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		m_LeisureDatas.Clear();
		m_LocalModifierDatas.Clear();
		m_CityModifierDatas.Clear();
		localeId = null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if ((base.EntityManager.HasComponent<Route>(selectedEntity) || (base.EntityManager.HasComponent<District>(selectedEntity) && base.EntityManager.HasComponent<Area>(selectedEntity)) || !base.EntityManager.HasComponent<ServiceObjectData>(selectedPrefab)) && !base.EntityManager.HasComponent<SignatureBuildingData>(selectedPrefab) && !base.EntityManager.HasComponent<Game.Objects.OutsideConnection>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(selectedEntity);
		}
		return true;
	}
```


