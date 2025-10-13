# Game.UI.Editor.TypePickerPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.DirectoryPanelBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`, `Game.UI.Editor.SearchField+IAdapter`  

## Code

```csharp
public class TypePickerPanel : Game.UI.Editor.DirectoryPanelBase, Game.UI.Editor.IEditorPanel, Game.UI.Editor.SearchField+IAdapter
{
    private readonly Game.UI.Editor.TypePickerPanel+SelectCallback m_SelectCallback;

    public TypePickerPanel(Game.UI.Localization.LocalizedString panelTitle, Game.UI.Localization.LocalizedString rootDirName, System.Collections.Generic.IEnumerable<Game.UI.Editor.Item> items, Game.UI.Editor.TypePickerPanel+SelectCallback onSelect, System.Action onCancel);

    public static System.Collections.Generic.IEnumerable<System.Type> GetAllConcreteTypesDerivedFrom<T>();
    public virtual System.Void OnSelect(Game.UI.Editor.Item item);
}
```


## Fields

- `private readonly Game.UI.Editor.TypePickerPanel+SelectCallback m_SelectCallback`  

```csharp
private readonly Game.UI.Editor.TypePickerPanel+SelectCallback m_SelectCallback;
```


## Constructors

- `public TypePickerPanel(Game.UI.Localization.LocalizedString panelTitle, Game.UI.Localization.LocalizedString rootDirName, System.Collections.Generic.IEnumerable<Game.UI.Editor.Item> items, Game.UI.Editor.TypePickerPanel+SelectCallback onSelect, System.Action onCancel)`  

```csharp
public TypePickerPanel(LocalizedString panelTitle, LocalizedString rootDirName, IEnumerable<Item> items, SelectCallback onSelect, Action onCancel)
	{
		m_RootDirName = rootDirName;
		m_SelectCallback = onSelect;
		m_Items = new List<Item>(items);
		foreach (Item item in m_Items)
		{
			Assert.IsNotNull(item.type);
			Assert.IsNotNull(item.name);
			Assert.IsFalse(item.directory);
			if (item.displayName.isEmpty)
			{
				item.displayName = item.name;
			}
			if (item.parentDir == null)
			{
				continue;
			}
			string[] array = item.parentDir.Split(new char[1] { '/' }, StringSplitOptions.RemoveEmptyEntries);
			string text = null;
			string[] array2 = array;
			foreach (string text2 in array2)
			{
				string parentDir = text;
				if (text == null)
				{
					text = string.Empty;
				}
				text += text2;
				text += "/";
				if (!m_Directories.ContainsKey(text))
				{
					m_Directories.Add(text, new Item
					{
						displayName = LocalizedString.Value(text2),
						directory = true,
						parentDir = parentDir,
						name = text2,
						fullName = item.relativePath
					});
				}
			}
			if (item.fullName == null)
			{
				item.fullName = text;
			}
			item.parentDir = text;
		}
		m_Items.AddRange(m_Directories.Values);
		base.title = panelTitle;
		base.children = new IWidget[3]
		{
			new SearchField
			{
				adapter = this
			},
			m_PageView = new PageView
			{
				currentPage = 0,
				children = new IWidget[0]
			},
			new Button
			{
				displayName = "Common.CANCEL",
				action = onCancel
			}
		};
		ShowSubDir(null);
	}
```


## Methods

- `public static GetAllConcreteTypesDerivedFrom<T>() : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetAllConcreteTypesDerivedFrom<T>();
```

- `public virtual OnSelect(Game.UI.Editor.Item item) : System.Void`  

```csharp
public override void OnSelect(Item item)
	{
		if (item != null)
		{
			if (item.directory)
			{
				ShowSubDir(item.relativePath + "/");
			}
			else
			{
				m_SelectCallback(item.type);
			}
		}
	}
```


## Nested types

- `Game.UI.Editor.TypePickerPanel+SelectCallback`  
- `Game.UI.Editor.TypePickerPanel+<>c__4<T>`  

