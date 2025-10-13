# Game.UI.InGame.AvatarsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AvatarsUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Unity.Entities.EntityQuery m_ColorsQuery;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AvatarsBinding;
    private static const System.String kGroup;
    private static const System.Int32 kIconSize;

    public AvatarsUISystem();

    private System.Void BindAvatar(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    private UnityEngine.Color32 GetColor(Unity.Entities.Entity entity);
    private System.String GetPicture(Unity.Entities.Entity entity);
    private System.Int32 GetRandomIndex(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Unity.Entities.EntityQuery m_ColorsQuery`  

```csharp
private Unity.Entities.EntityQuery m_ColorsQuery;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AvatarsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AvatarsBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.Int32 kIconSize`  

```csharp
private static const System.Int32 kIconSize;
```


## Constructors

- `public AvatarsUISystem()`  

```csharp
[Preserve]
	public AvatarsUISystem()
	{
	}
```


## Methods

- `private BindAvatar(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void BindAvatar(IJsonWriter writer, Entity entity)
	{
		writer.TypeBegin("avatars.AvatarData");
		writer.PropertyName("picture");
		writer.Write(GetPicture(entity));
		writer.PropertyName("name");
		m_NameSystem.BindName(writer, entity);
		Color32 color = GetColor(entity);
		writer.PropertyName("color");
		writer.Write(color);
		writer.TypeEnd();
	}
```

- `private GetColor(Unity.Entities.Entity entity) : UnityEngine.Color32`  

```csharp
private Color32 GetColor(Entity entity)
	{
		DynamicBuffer<UIAvatarColorData> singletonBuffer = m_ColorsQuery.GetSingletonBuffer<UIAvatarColorData>();
		int randomIndex = GetRandomIndex(entity);
		if (randomIndex < 0)
		{
			return singletonBuffer[0].m_Color;
		}
		return singletonBuffer[randomIndex % singletonBuffer.Length].m_Color;
	}
```

- `private GetPicture(Unity.Entities.Entity entity) : System.String`  

```csharp
[Colossal.Annotations.CanBeNull]
	private string GetPicture(Entity entity)
	{
		if (base.EntityManager.TryGetComponent<CompanyData>(entity, out var component))
		{
			entity = component.m_Brand;
		}
		if (base.EntityManager.TryGetComponent<PrefabData>(entity, out var component2) && m_PrefabSystem.TryGetPrefab<PrefabBase>(component2, out var prefab))
		{
			string icon = ImageSystem.GetIcon(prefab);
			if (icon != null)
			{
				return icon;
			}
			if (prefab is ChirperAccount chirperAccount && chirperAccount.m_InfoView != null && chirperAccount.m_InfoView.m_IconPath != null)
			{
				return chirperAccount.m_InfoView.m_IconPath;
			}
			if (prefab is BrandPrefab brandPrefab)
			{
				return $"{brandPrefab.thumbnailUrl}?width={32}&height={32}";
			}
		}
		return null;
	}
```

- `private GetRandomIndex(Unity.Entities.Entity entity) : System.Int32`  

```csharp
private int GetRandomIndex(Entity entity)
	{
		if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<RandomLocalizationIndex> buffer) && buffer.Length > 0)
		{
			return buffer[0].m_Index;
		}
		return 0;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_ColorsQuery = GetEntityQuery(ComponentType.ReadOnly<UIAvatarColorData>());
		AddBinding(m_AvatarsBinding = new RawMapBinding<Entity>("avatars", "avatarsMap", BindAvatar));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
	}
```


