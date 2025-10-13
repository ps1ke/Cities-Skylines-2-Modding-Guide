# Game.UI.Editor.EditorHierarchyUISystem+ViewportItem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct ViewportItem : Colossal.UI.Binding.IJsonWritable
{
    public Game.UI.Editor.EditorHierarchyUISystem+ItemId id;
    public System.Byte level;
    public System.Boolean expandable;
    public System.Boolean expanded;
    public Game.UI.Localization.LocalizedString name;
    public System.Boolean selectable;
    public System.Boolean saveable;
    public System.Nullable<Game.UI.Localization.LocalizedString> tooltip;

    public System.Boolean EqualsHierarchy(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem other);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Game.UI.Editor.EditorHierarchyUISystem+ItemId id`  

```csharp
public Game.UI.Editor.EditorHierarchyUISystem+ItemId id;
```

- `public System.Byte level`  

```csharp
public System.Byte level;
```

- `public System.Boolean expandable`  

```csharp
public System.Boolean expandable;
```

- `public System.Boolean expanded`  

```csharp
public System.Boolean expanded;
```

- `public Game.UI.Localization.LocalizedString name`  

```csharp
public Game.UI.Localization.LocalizedString name;
```

- `public System.Boolean selectable`  

```csharp
public System.Boolean selectable;
```

- `public System.Boolean saveable`  

```csharp
public System.Boolean saveable;
```

- `public System.Nullable<Game.UI.Localization.LocalizedString> tooltip`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> tooltip;
```


## Methods

- `public EqualsHierarchy(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem other) : System.Boolean`  

```csharp
public System.Boolean EqualsHierarchy(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem other);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


