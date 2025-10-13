# Game.UI.Menu.WhatsNewPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WhatsNewPanelUISystem : Game.UI.UISystemBase
{
    private Colossal.UI.Binding.RawValueBinding m_PanelBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibilityBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_InitialTabBinding;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private static const System.String kGroup;

    public WhatsNewPanelUISystem();

    private System.Void BindPanel(Colossal.UI.Binding.IJsonWriter writer);
    private System.Collections.Generic.List<Game.Prefabs.UIWhatsNewPanelPrefab> GetSortedWhatsNewTabs(Unity.Entities.EntityQuery query);
    private System.Void OnClose(System.Boolean dismiss);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
}
```


## Fields

- `private Colossal.UI.Binding.RawValueBinding m_PanelBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_PanelBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibilityBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibilityBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InitialTabBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_InitialTabBinding;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public WhatsNewPanelUISystem()`  

```csharp
[Preserve]
	public WhatsNewPanelUISystem()
	{
	}
```


## Methods

- `private BindPanel(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindPanel(IJsonWriter writer)
	{
		List<UIWhatsNewPanelPrefab> sortedWhatsNewTabs = GetSortedWhatsNewTabs(m_Query);
		writer.ArrayBegin(sortedWhatsNewTabs.Count);
		for (int i = 0; i < sortedWhatsNewTabs.Count; i++)
		{
			UIWhatsNewPanelPrefab uIWhatsNewPanelPrefab = sortedWhatsNewTabs[i];
			DlcRequirement component = uIWhatsNewPanelPrefab.GetComponent<DlcRequirement>();
			writer.TypeBegin(typeof(UIWhatsNewPanelPrefab).FullName);
			writer.PropertyName("id");
			writer.Write(component.m_Dlc.id);
			writer.PropertyName("dlc");
			writer.Write(PlatformManager.instance.GetDlcName(component.m_Dlc));
			writer.PropertyName("pages");
			writer.ArrayBegin(uIWhatsNewPanelPrefab.m_Pages.Length);
			for (int j = 0; j < uIWhatsNewPanelPrefab.m_Pages.Length; j++)
			{
				UIWhatsNewPanelPrefab.UIWhatsNewPanelPage uIWhatsNewPanelPage = uIWhatsNewPanelPrefab.m_Pages[j];
				writer.TypeBegin(typeof(UIWhatsNewPanelPrefab.UIWhatsNewPanelPage).FullName);
				writer.PropertyName("items");
				writer.ArrayBegin(uIWhatsNewPanelPage.m_Items.Length);
				for (int k = 0; k < uIWhatsNewPanelPage.m_Items.Length; k++)
				{
					UIWhatsNewPanelPrefab.UIWhatsNewPanelPageItem uIWhatsNewPanelPageItem = uIWhatsNewPanelPage.m_Items[k];
					writer.TypeBegin(typeof(UIWhatsNewPanelPrefab.UIWhatsNewPanelPageItem).FullName);
					writer.PropertyName("images");
					writer.ArrayBegin(uIWhatsNewPanelPageItem.m_Images.Length);
					for (int l = 0; l < uIWhatsNewPanelPageItem.m_Images.Length; l++)
					{
						UIWhatsNewPanelPrefab.UIWhatsNewPanelImage uIWhatsNewPanelImage = uIWhatsNewPanelPageItem.m_Images[l];
						writer.TypeBegin(typeof(UIWhatsNewPanelPrefab.UIWhatsNewPanelImage).FullName);
						writer.PropertyName("image");
						writer.Write(uIWhatsNewPanelImage.m_Uri);
						writer.PropertyName("aspectRatio");
						writer.Write(uIWhatsNewPanelImage.m_AspectRatio);
						writer.PropertyName("width");
						writer.Write(uIWhatsNewPanelImage.m_Width);
						writer.TypeEnd();
					}
					writer.ArrayEnd();
					writer.PropertyName("title");
					if (uIWhatsNewPanelPageItem.m_TitleId != null)
					{
						writer.Write(uIWhatsNewPanelPageItem.m_TitleId);
					}
					else
					{
						writer.WriteNull();
					}
					writer.PropertyName("subtitle");
					if (uIWhatsNewPanelPageItem.m_SubTitleId != null)
					{
						writer.Write(uIWhatsNewPanelPageItem.m_SubTitleId);
					}
					else
					{
						writer.WriteNull();
					}
					writer.PropertyName("paragraphs");
					if (uIWhatsNewPanelPageItem.m_ParagraphsId != null)
					{
						writer.Write(uIWhatsNewPanelPageItem.m_ParagraphsId);
					}
					else
					{
						writer.WriteNull();
					}
					writer.PropertyName("justify");
					writer.Write((int)uIWhatsNewPanelPageItem.m_Justify);
					writer.PropertyName("width");
					writer.Write(uIWhatsNewPanelPageItem.m_Width);
					writer.TypeEnd();
				}
				writer.ArrayEnd();
				writer.TypeEnd();
			}
			writer.ArrayEnd();
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `private GetSortedWhatsNewTabs(Unity.Entities.EntityQuery query) : System.Collections.Generic.List<Game.Prefabs.UIWhatsNewPanelPrefab>`  

```csharp
private List<UIWhatsNewPanelPrefab> GetSortedWhatsNewTabs(EntityQuery query)
	{
		NativeArray<Entity> array = query.ToEntityArray(Allocator.Temp);
		array.Sort(new DlcComparer(base.EntityManager));
		List<UIWhatsNewPanelPrefab> list = new List<UIWhatsNewPanelPrefab>();
		foreach (Entity item in array)
		{
			UIWhatsNewPanelPrefab prefab = m_PrefabSystem.GetPrefab<UIWhatsNewPanelPrefab>(item);
			DlcRequirement component = prefab.GetComponent<DlcRequirement>();
			if (PlatformManager.instance.IsDlcOwned(component.m_Dlc))
			{
				list.Add(prefab);
			}
		}
		return list;
	}
```

- `private OnClose(System.Boolean dismiss) : System.Void`  

```csharp
private void OnClose(bool dismiss)
	{
		m_VisibilityBinding.Update(newValue: false);
		if (!dismiss)
		{
			return;
		}
		NativeArray<Entity> array = m_Query.ToEntityArray(Allocator.Temp);
		array.Sort(new DlcComparer(base.EntityManager));
		foreach (Entity item in array)
		{
			UIWhatsNewPanelPrefab prefab = m_PrefabSystem.GetPrefab<UIWhatsNewPanelPrefab>(item);
			DlcRequirement dlcRequirement = ((prefab == null) ? null : prefab.GetComponent<DlcRequirement>());
			if (!(dlcRequirement == null) && dlcRequirement.CheckRequirement())
			{
				string dlcName = PlatformManager.instance.GetDlcName(dlcRequirement.m_Dlc);
				if (!SharedSettings.instance.userState.seenWhatsNew.Contains(dlcName))
				{
					SharedSettings.instance.userState.seenWhatsNew.Add(dlcName);
				}
			}
		}
		SharedSettings.instance.userInterface.showWhatsNewPanel = false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		AddBinding(m_PanelBinding = new RawValueBinding("whatsnew", "panel", BindPanel));
		AddBinding(m_VisibilityBinding = new ValueBinding<bool>("whatsnew", "visible", initialValue: false));
		AddBinding(m_InitialTabBinding = new ValueBinding<int>("whatsnew", "initialTab", 0));
		AddBinding(new TriggerBinding<bool>("whatsnew", "close", OnClose));
		m_Query = GetEntityQuery(ComponentType.ReadOnly<UIWhatsNewPanelPrefabData>());
	}
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGameLoadingComplete(Purpose purpose, GameMode mode)
	{
		if (mode != GameMode.MainMenu)
		{
			return;
		}
		List<UIWhatsNewPanelPrefab> sortedWhatsNewTabs = GetSortedWhatsNewTabs(m_Query);
		int initialTab = int.MaxValue;
		bool flag = false;
		foreach (UIWhatsNewPanelPrefab item in sortedWhatsNewTabs)
		{
			DlcRequirement dlcRequirement = ((item == null) ? null : item.GetComponent<DlcRequirement>());
			if (!(dlcRequirement == null) && dlcRequirement.CheckRequirement() && !SharedSettings.instance.userState.seenWhatsNew.Contains(PlatformManager.instance.GetDlcName(dlcRequirement.m_Dlc)))
			{
				if (dlcRequirement.m_Dlc.id < initialTab)
				{
					initialTab = dlcRequirement.m_Dlc.id;
				}
				flag = true;
			}
		}
		if (flag)
		{
			int num = sortedWhatsNewTabs.FindIndex((UIWhatsNewPanelPrefab p) => p.GetComponent<DlcRequirement>().m_Dlc.id == initialTab);
			m_InitialTabBinding.Update((num >= 0) ? num : (sortedWhatsNewTabs.Count - 1));
			SharedSettings.instance.userInterface.showWhatsNewPanel = true;
		}
		else
		{
			m_InitialTabBinding.Update(sortedWhatsNewTabs.Count - 1);
		}
		m_PanelBinding.Update();
		m_VisibilityBinding.Update(SharedSettings.instance.userInterface.showWhatsNewPanel);
	}
```


## Nested types

- `Game.UI.Menu.WhatsNewPanelUISystem+DlcComparer`  
- `Game.UI.Menu.WhatsNewPanelUISystem+<>c__DisplayClass8_0`  

