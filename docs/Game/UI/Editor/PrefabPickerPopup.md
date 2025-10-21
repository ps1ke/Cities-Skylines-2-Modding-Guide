# Game.UI.Editor.PrefabPickerPopup

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IValueFieldPopup<Game.Prefabs.PrefabBase>`  

## Code

```csharp
public class PrefabPickerPopup : Game.UI.Widgets.IValueFieldPopup<Game.Prefabs.PrefabBase>
{
    private Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> m_Accessor;
    private System.Type m_PrefabType;
    private System.Func<Game.Prefabs.PrefabBase, System.Boolean> m_Filter;
    private System.Boolean <nullable>k__BackingField;
    private Game.UI.Editor.PrefabPickerAdapter m_Adapter;
    private readonly System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;

    public System.Boolean nullable { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }

    public PrefabPickerPopup(System.Type prefabType, System.Func<Game.Prefabs.PrefabBase, System.Boolean> filter);

    public System.Void Attach(Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> accessor);
    public System.Void Detach();
    public Game.UI.Localization.LocalizedString GetDisplayValue(Game.Prefabs.PrefabBase value);
    private System.Void OnPrefabSelected(Game.Prefabs.PrefabBase prefab);
    public System.Boolean Update();
}
```


## Fields

- `private Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> m_Accessor`  

```csharp
private Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> m_Accessor;
```

- `private System.Type m_PrefabType`  

```csharp
private System.Type m_PrefabType;
```

- `private System.Func<Game.Prefabs.PrefabBase, System.Boolean> m_Filter`  

```csharp
private System.Func<Game.Prefabs.PrefabBase, System.Boolean> m_Filter;
```

- `private System.Boolean <nullable>k__BackingField`  

```csharp
private System.Boolean <nullable>k__BackingField;
```

- `private Game.UI.Editor.PrefabPickerAdapter m_Adapter`  

```csharp
private Game.UI.Editor.PrefabPickerAdapter m_Adapter;
```

- `private readonly System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

```csharp
private readonly System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;
```


## Properties

- `public System.Boolean nullable { get; set }`  

```csharp
public System.Boolean nullable { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; }
```


## Constructors

- `public PrefabPickerPopup(System.Type prefabType, System.Func<Game.Prefabs.PrefabBase, System.Boolean> filter = null)`  

```csharp
public PrefabPickerPopup(System.Type prefabType, System.Func<Game.Prefabs.PrefabBase, System.Boolean> filter);
```


## Methods

- `public Attach(Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> accessor) : System.Void`  

```csharp
public System.Void Attach(Game.Reflection.ITypedValueAccessor<Game.Prefabs.PrefabBase> accessor);
```

- `public Detach() : System.Void`  

```csharp
public System.Void Detach();
```

- `public GetDisplayValue(Game.Prefabs.PrefabBase value) : Game.UI.Localization.LocalizedString`  

```csharp
public Game.UI.Localization.LocalizedString GetDisplayValue(Game.Prefabs.PrefabBase value);
```

- `private OnPrefabSelected(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void OnPrefabSelected(Game.Prefabs.PrefabBase prefab);
```

- `public Update() : System.Boolean`  

```csharp
public System.Boolean Update();
```


