# Game.UI.Menu.AutomaticSettings+SettingPageData

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DefaultMember`  

## Fields

- `private readonly System.String <id>k__BackingField`  
- `private readonly System.Boolean <addPrefix>k__BackingField`  
- `private System.Boolean <showAllGroupNames>k__BackingField`  
- `private readonly System.Collections.Generic.HashSet<System.String> <m_GroupToShowName>k__BackingField`  
- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_TabOrder`  
- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupOrder`  
- `private System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingTabData> m_Tabs`  
- `private System.Func<System.Boolean> <warningGetter>k__BackingField`  
- `private System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> <tabWarningGetters>k__BackingField`  

## Properties

- `public System.String id { get }`  
- `public System.Boolean addPrefix { get }`  
- `public System.String prefix { get }`  
- `public System.Boolean showAllGroupNames { get; set }`  
- `private System.Collections.Generic.HashSet<System.String> m_GroupToShowName { private get }`  
- `public System.Collections.Generic.List<Game.UI.Menu.AutomaticSettings+SettingTabData> tabs { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> groupNames { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> groupToShowName { get }`  
- `public System.Func<System.Boolean> warningGetter { get; set }`  
- `public System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> tabWarningGetters { get; set }`  
- `public Game.UI.Menu.AutomaticSettings+SettingTabData Item { get }`  

## Constructors

- `public SettingPageData(System.String id, System.Boolean addPrefix)`  

## Methods

- `private <SortTabs>b__35_0(Game.UI.Menu.AutomaticSettings+SettingTabData a, Game.UI.Menu.AutomaticSettings+SettingTabData b) : System.Int32`  
- `public AddGroup(System.String group) : System.Void`  
- `public AddGroupToShowName(System.String group) : System.Void`  
- `public AddTab(System.String tab) : System.Void`  
- `public BuildPage() : Game.UI.Menu.OptionsUISystem+Page`  
- `public SortTabs() : System.Void`  
- `public TryGetGroupOrder(System.String groupName, System.Int32& index) : System.Boolean`  
- `public TryGetTabOrder(System.String tabName, System.Int32& index) : System.Boolean`  

## Nested types

- `Game.UI.Menu.AutomaticSettings+SettingPageData+<>c`  
- `Game.UI.Menu.AutomaticSettings+SettingPageData+<>c__DisplayClass33_0`  

