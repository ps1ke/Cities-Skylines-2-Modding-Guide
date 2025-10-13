# Game.UI.Menu.AutomaticSettings+SettingTabData

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class SettingTabData
{
    private readonly System.String <id>k__BackingField;
    private readonly Game.UI.Menu.AutomaticSettings+SettingPageData <pageData>k__BackingField;
    private readonly System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> m_Items;

    public System.String id { get; }
    public Game.UI.Menu.AutomaticSettings+SettingPageData pageData { get; }
    public System.Collections.Generic.IEnumerable<Game.UI.Menu.AutomaticSettings+SettingItemData> items { get; }

    public SettingTabData(System.String id, Game.UI.Menu.AutomaticSettings+SettingPageData pageData);

    public System.Void AddItem(Game.UI.Menu.AutomaticSettings+SettingItemData item);
    public Game.UI.Menu.OptionsUISystem+Section BuildTab(Game.UI.Menu.OptionsUISystem+Page page);
    public System.Void InsertItem(Game.UI.Menu.AutomaticSettings+SettingItemData item, System.Int32 index);
}
```


## Fields

- `private readonly System.String <id>k__BackingField`  

```csharp
private readonly System.String <id>k__BackingField;
```

- `private readonly Game.UI.Menu.AutomaticSettings+SettingPageData <pageData>k__BackingField`  

```csharp
private readonly Game.UI.Menu.AutomaticSettings+SettingPageData <pageData>k__BackingField;
```

- `private readonly System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> m_Items`  

```csharp
private readonly System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingItemData> m_Items;
```


## Properties

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public Game.UI.Menu.AutomaticSettings+SettingPageData pageData { get }`  

```csharp
public Game.UI.Menu.AutomaticSettings+SettingPageData pageData { get; }
```

- `public System.Collections.Generic.IEnumerable<Game.UI.Menu.AutomaticSettings+SettingItemData> items { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.UI.Menu.AutomaticSettings+SettingItemData> items { get; }
```


## Constructors

- `public SettingTabData(System.String id, Game.UI.Menu.AutomaticSettings+SettingPageData pageData)`  

```csharp
public SettingTabData(System.String id, Game.UI.Menu.AutomaticSettings+SettingPageData pageData);
```


## Methods

- `public AddItem(Game.UI.Menu.AutomaticSettings+SettingItemData item) : System.Void`  

```csharp
public System.Void AddItem(Game.UI.Menu.AutomaticSettings+SettingItemData item);
```

- `public BuildTab(Game.UI.Menu.OptionsUISystem+Page page) : Game.UI.Menu.OptionsUISystem+Section`  

```csharp
public Game.UI.Menu.OptionsUISystem+Section BuildTab(Game.UI.Menu.OptionsUISystem+Page page);
```

- `public InsertItem(Game.UI.Menu.AutomaticSettings+SettingItemData item, System.Int32 index) : System.Void`  

```csharp
public System.Void InsertItem(Game.UI.Menu.AutomaticSettings+SettingItemData item, System.Int32 index);
```


