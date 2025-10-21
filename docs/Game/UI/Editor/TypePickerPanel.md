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
public TypePickerPanel(Game.UI.Localization.LocalizedString panelTitle, Game.UI.Localization.LocalizedString rootDirName, System.Collections.Generic.IEnumerable<Game.UI.Editor.Item> items, Game.UI.Editor.TypePickerPanel+SelectCallback onSelect, System.Action onCancel);
```


## Methods

- `public static GetAllConcreteTypesDerivedFrom<T>() : System.Collections.Generic.IEnumerable<System.Type>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.Type> GetAllConcreteTypesDerivedFrom<T>();
```

- `public virtual OnSelect(Game.UI.Editor.Item item) : System.Void`  

```csharp
public virtual System.Void OnSelect(Game.UI.Editor.Item item);
```


## Nested types

- `Game.UI.Editor.TypePickerPanel+SelectCallback`  
- `Game.UI.Editor.TypePickerPanel+<>c__4<T>`  

