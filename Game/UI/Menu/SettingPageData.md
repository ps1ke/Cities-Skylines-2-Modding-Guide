# Game.UI.Menu.AutomaticSettings+SettingPageData

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public class SettingPageData
{
    private readonly System.String <id>k__BackingField;
    private readonly System.Boolean <addPrefix>k__BackingField;
    private System.Boolean <showAllGroupNames>k__BackingField;
    private readonly System.Collections.Generic.HashSet<System.String> <m_GroupToShowName>k__BackingField;
    private System.Collections.Generic.Dictionary<System.String, System.Int32> m_TabOrder;
    private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupOrder;
    private System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingTabData> m_Tabs;
    private System.Func<System.Boolean> <warningGetter>k__BackingField;
    private System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> <tabWarningGetters>k__BackingField;

    public System.String id { get; }
    public System.Boolean addPrefix { get; }
    public System.String prefix { get; }
    public System.Boolean showAllGroupNames { get; set; }
    private System.Collections.Generic.HashSet<System.String> m_GroupToShowName { private get; }
    public System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingTabData> tabs { get; }
    public System.Collections.Generic.IEnumerable<System.String> groupNames { get; }
    public System.Collections.Generic.IEnumerable<System.String> groupToShowName { get; }
    public System.Func<System.Boolean> warningGetter { get; set; }
    public System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> tabWarningGetters { get; set; }
    public Game.UI.Menu.AutomaticSettings+SettingTabData Item { get; }

    public SettingPageData(System.String id, System.Boolean addPrefix);

    private System.Int32 <SortTabs>b__35_0(Game.UI.Menu.AutomaticSettings+SettingTabData a, Game.UI.Menu.AutomaticSettings+SettingTabData b);
    public System.Void AddGroup(System.String group);
    public System.Void AddGroupToShowName(System.String group);
    public System.Void AddTab(System.String tab);
    public Game.UI.Menu.OptionsUISystem+Page BuildPage();
    public System.Void SortTabs();
    public System.Boolean TryGetGroupOrder(System.String groupName, System.Int32& index);
    public System.Boolean TryGetTabOrder(System.String tabName, System.Int32& index);
}
```


## Fields

- `private readonly System.String <id>k__BackingField`  

```csharp
private readonly System.String <id>k__BackingField;
```

- `private readonly System.Boolean <addPrefix>k__BackingField`  

```csharp
private readonly System.Boolean <addPrefix>k__BackingField;
```

- `private System.Boolean <showAllGroupNames>k__BackingField`  

```csharp
private System.Boolean <showAllGroupNames>k__BackingField;
```

- `private readonly System.Collections.Generic.HashSet<System.String> <m_GroupToShowName>k__BackingField`  

```csharp
private readonly System.Collections.Generic.HashSet<System.String> <m_GroupToShowName>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_TabOrder`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Int32> m_TabOrder;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupOrder`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupOrder;
```

- `private System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingTabData> m_Tabs`  

```csharp
private System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingTabData> m_Tabs;
```

- `private System.Func<System.Boolean> <warningGetter>k__BackingField`  

```csharp
private System.Func<System.Boolean> <warningGetter>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> <tabWarningGetters>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> <tabWarningGetters>k__BackingField;
```


## Properties

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public System.Boolean addPrefix { get }`  

```csharp
public System.Boolean addPrefix { get; }
```

- `public System.String prefix { get }`  

```csharp
public System.String prefix { get; }
```

- `public System.Boolean showAllGroupNames { get; set }`  

```csharp
public System.Boolean showAllGroupNames { get; set; }
```

- `private System.Collections.Generic.HashSet<System.String> m_GroupToShowName { private get }`  

```csharp
private System.Collections.Generic.HashSet<System.String> m_GroupToShowName { private get; }
```

- `public System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingTabData> tabs { get }`  

```csharp
public System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingTabData> tabs { get; }
```

- `public System.Collections.Generic.IEnumerable<System.String> groupNames { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> groupNames { get; }
```

- `public System.Collections.Generic.IEnumerable<System.String> groupToShowName { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> groupToShowName { get; }
```

- `public System.Func<System.Boolean> warningGetter { get; set }`  

```csharp
public System.Func<System.Boolean> warningGetter { get; set; }
```

- `public System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> tabWarningGetters { get; set }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> tabWarningGetters { get; set; }
```

- `public Game.UI.Menu.AutomaticSettings+SettingTabData Item { get }`  

```csharp
public Game.UI.Menu.AutomaticSettings+SettingTabData Item { get; }
```


## Constructors

- `public SettingPageData(System.String id, System.Boolean addPrefix)`  

```csharp
public SettingPageData(System.String id, System.Boolean addPrefix);
```


## Methods

- `private <SortTabs>b__35_0(Game.UI.Menu.AutomaticSettings+SettingTabData a, Game.UI.Menu.AutomaticSettings+SettingTabData b) : System.Int32`  

```csharp
private System.Int32 <SortTabs>b__35_0(Game.UI.Menu.AutomaticSettings+SettingTabData a, Game.UI.Menu.AutomaticSettings+SettingTabData b);
```

- `public AddGroup(System.String group) : System.Void`  

```csharp
public System.Void AddGroup(System.String group);
```

- `public AddGroupToShowName(System.String group) : System.Void`  

```csharp
public System.Void AddGroupToShowName(System.String group);
```

- `public AddTab(System.String tab) : System.Void`  

```csharp
public System.Void AddTab(System.String tab);
```

- `public BuildPage() : Game.UI.Menu.OptionsUISystem+Page`  

```csharp
public Game.UI.Menu.OptionsUISystem+Page BuildPage();
```

- `public SortTabs() : System.Void`  

```csharp
public System.Void SortTabs();
```

- `public TryGetGroupOrder(System.String groupName, System.Int32& index) : System.Boolean`  

```csharp
public System.Boolean TryGetGroupOrder(System.String groupName, System.Int32& index);
```

- `public TryGetTabOrder(System.String tabName, System.Int32& index) : System.Boolean`  

```csharp
public System.Boolean TryGetTabOrder(System.String tabName, System.Int32& index);
```


## Nested types

- `Game.UI.Menu.AutomaticSettings+SettingPageData+<>c`  
- `Game.UI.Menu.AutomaticSettings+SettingPageData+<>c__DisplayClass33_0`  

