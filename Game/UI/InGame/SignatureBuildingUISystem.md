# Game.UI.InGame.SignatureBuildingUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SignatureBuildingUISystem : Game.UI.UISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_UnlockedSignatureBuildingQuery;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_UnlockSignaturesBinding;
    private System.Boolean m_SkipUpdate;
    private System.Int32 m_LastListCount;
    private System.Boolean m_NeedTriggerUpdate;
    private static const System.String kGroup;

    public SignatureBuildingUISystem();

    public System.Void AddUnlockedSignature(Unity.Entities.Entity prefab);
    public System.Void ClearUnlockedSignature();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void RemoveUnlockedSignature();
    public System.Void SkipUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_UnlockedSignatureBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedSignatureBuildingQuery;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_UnlockSignaturesBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_UnlockSignaturesBinding;
```

- `private System.Boolean m_SkipUpdate`  

```csharp
private System.Boolean m_SkipUpdate;
```

- `private System.Int32 m_LastListCount`  

```csharp
private System.Int32 m_LastListCount;
```

- `private System.Boolean m_NeedTriggerUpdate`  

```csharp
private System.Boolean m_NeedTriggerUpdate;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public SignatureBuildingUISystem()`  

```csharp
[Preserve]
	public SignatureBuildingUISystem()
	{
	}
```


## Methods

- `public AddUnlockedSignature(Unity.Entities.Entity prefab) : System.Void`  

```csharp
public void AddUnlockedSignature(Entity prefab)
	{
		if (!m_UnlockSignaturesBinding.value.Contains(prefab))
		{
			m_UnlockSignaturesBinding.value.Insert(0, prefab);
			m_NeedTriggerUpdate = true;
		}
	}
```

- `public ClearUnlockedSignature() : System.Void`  

```csharp
public void ClearUnlockedSignature()
	{
		m_UnlockSignaturesBinding.value.Clear();
		m_NeedTriggerUpdate = true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_UnlockedSignatureBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		AddBinding(m_UnlockSignaturesBinding = new ValueBinding<List<Entity>>("signatureBuildings", "unlockedSignatures", new List<Entity>(), new ListWriter<Entity>()));
		AddBinding(new TriggerBinding("signatureBuildings", "removeUnlockedSignature", RemoveUnlockedSignature));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_SkipUpdate)
		{
			m_SkipUpdate = false;
		}
		else
		{
			if (!SharedSettings.instance.userInterface.blockingPopupsEnabled || m_CityConfigurationSystem.unlockAll)
			{
				return;
			}
			if (!m_UnlockedSignatureBuildingQuery.IsEmptyIgnoreFilter)
			{
				NativeArray<Unlock> nativeArray = m_UnlockedSignatureBuildingQuery.ToComponentDataArray<Unlock>(Allocator.TempJob);
				for (int i = 0; i < nativeArray.Length; i++)
				{
					if (base.EntityManager.HasComponent<SignatureBuildingData>(nativeArray[i].m_Prefab) && base.EntityManager.HasComponent<UIObjectData>(nativeArray[i].m_Prefab))
					{
						AddUnlockedSignature(nativeArray[i].m_Prefab);
					}
				}
				nativeArray.Dispose();
			}
			if (m_UnlockSignaturesBinding.value.Count != m_LastListCount || m_NeedTriggerUpdate)
			{
				m_UnlockSignaturesBinding.TriggerUpdate();
				m_LastListCount = m_UnlockSignaturesBinding.value.Count;
				m_NeedTriggerUpdate = false;
			}
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_UnlockSignaturesBinding.value.Clear();
		m_SkipUpdate = false;
	}
```

- `private RemoveUnlockedSignature() : System.Void`  

```csharp
private void RemoveUnlockedSignature()
	{
		m_UnlockSignaturesBinding.value.RemoveAt(0);
		m_NeedTriggerUpdate = true;
	}
```

- `public SkipUpdate() : System.Void`  

```csharp
public void SkipUpdate()
	{
		m_SkipUpdate = true;
	}
```


