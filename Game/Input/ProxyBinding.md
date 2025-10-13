# Game.Input.ProxyBinding

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Input.ProxyBinding>`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct ProxyBinding : System.IEquatable<Game.Input.ProxyBinding>, Colossal.UI.Binding.IJsonWritable
{
    private System.String m_MapName;
    private System.String m_ActionName;
    private Game.Input.ActionComponent m_Component;
    private System.String m_Name;
    private Game.Input.InputManager+DeviceType m_Device;
    private System.String m_Path;
    private Game.Input.ProxyModifier[] m_Modifiers;
    private System.String m_OriginalPath;
    private Game.Input.ProxyModifier[] m_OriginalModifiers;
    private Game.Input.CompositeInstance m_Source;
    private Game.Input.UIBaseInputAction m_Alies;
    private System.Int32 m_HasConflictVersion;
    private Game.Input.ProxyBinding+ConflictType m_HasConflicts;
    private System.Int32 m_ConflictVersion;
    private System.Collections.Generic.IList<Game.Input.ProxyBinding> m_Conflicts;
    public static readonly Game.Input.ProxyBinding+Comparer pathAndModifiersComparer;
    public static readonly Game.Input.ProxyBinding+Comparer onlyPathComparer;
    internal static readonly Game.Input.ProxyBinding+Comparer componentComparer;

    public static Game.Input.ProxyBinding+Comparer defaultComparer { get; }
    public static Game.Input.ProxyBinding+ModifiersListComparer defaultModifiersComparer { get; }
    public System.String mapName { get; }
    public System.String actionName { get; }
    public Game.Input.ActionComponent component { get; }
    public System.String name { get; }
    internal Game.Input.ProxyAction action { internal get; }
    public System.Boolean isBuiltIn { get; }
    public System.Boolean isRebindable { get; }
    public System.Boolean isModifiersRebindable { get; }
    public System.Boolean allowModifiers { get; }
    public System.Boolean canBeEmpty { get; }
    public System.Boolean developerOnly { get; }
    internal System.Boolean isDummy { internal get; }
    internal System.Boolean isHidden { internal get; }
    internal Game.Input.OptionGroupOverride optionGroupOverride { internal get; }
    public Game.Input.Usages usages { get; }
    public Game.Input.ProxyBinding original { get; }
    public System.Boolean isOriginal { get; }
    public Game.Input.ProxyBinding+ConflictType hasConflicts { get; }
    public System.Collections.Generic.IList<Game.Input.ProxyBinding> conflicts { get; }
    public System.String path { get; set; }
    public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> modifiers { get; set; }
    public System.String originalPath { get; set; }
    public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> originalModifiers { get; set; }
    public System.String group { get; set; }
    public Game.Input.InputManager+DeviceType device { get; set; }
    public System.Boolean isKeyboard { get; }
    public System.Boolean isMouse { get; }
    public System.Boolean isGamepad { get; }
    public System.Boolean isSet { get; }
    internal Game.Input.UIBaseInputAction alies { internal get; internal set; }
    internal System.Boolean isAlias { internal get; }
    public System.String title { get; }

    public ProxyBinding(System.String mapName, System.String actionName, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source);
    public ProxyBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source);

    public static System.Boolean ConflictsWith(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage);
    public Game.Input.ProxyBinding Copy();
    internal Game.Input.ProxyBinding+Watcher CreateWatcher(System.Action<Game.Input.ProxyBinding> onChange);
    public System.Boolean Equals(Game.Input.ProxyBinding other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    internal System.String GetOptionsGroup();
    public static System.Boolean PathEquals(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y);
    public System.Void ResetConflictCache();
    private System.Void SetModifiers(Game.Input.ProxyModifier[]& field, System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> value);
    private static System.Void SupportValueTypesForAOT();
    public System.Collections.Generic.IEnumerable<System.String> ToHumanReadablePath();
    public virtual System.String ToString();
    public Game.Input.ProxyBinding WithModifiers(System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> newModifiers);
    public Game.Input.ProxyBinding WithPath(System.String newPath);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String m_MapName`  

```csharp
private System.String m_MapName;
```

- `private System.String m_ActionName`  

```csharp
private System.String m_ActionName;
```

- `private Game.Input.ActionComponent m_Component`  

```csharp
private Game.Input.ActionComponent m_Component;
```

- `private System.String m_Name`  

```csharp
private System.String m_Name;
```

- `private Game.Input.InputManager+DeviceType m_Device`  

```csharp
private Game.Input.InputManager+DeviceType m_Device;
```

- `private System.String m_Path`  

```csharp
private System.String m_Path;
```

- `private Game.Input.ProxyModifier[] m_Modifiers`  

```csharp
private Game.Input.ProxyModifier[] m_Modifiers;
```

- `private System.String m_OriginalPath`  

```csharp
private System.String m_OriginalPath;
```

- `private Game.Input.ProxyModifier[] m_OriginalModifiers`  

```csharp
private Game.Input.ProxyModifier[] m_OriginalModifiers;
```

- `private Game.Input.CompositeInstance m_Source`  

```csharp
private Game.Input.CompositeInstance m_Source;
```

- `private Game.Input.UIBaseInputAction m_Alies`  

```csharp
private Game.Input.UIBaseInputAction m_Alies;
```

- `private System.Int32 m_HasConflictVersion`  

```csharp
private System.Int32 m_HasConflictVersion;
```

- `private Game.Input.ProxyBinding+ConflictType m_HasConflicts`  

```csharp
private Game.Input.ProxyBinding+ConflictType m_HasConflicts;
```

- `private System.Int32 m_ConflictVersion`  

```csharp
private System.Int32 m_ConflictVersion;
```

- `private System.Collections.Generic.IList<Game.Input.ProxyBinding> m_Conflicts`  

```csharp
private System.Collections.Generic.IList<Game.Input.ProxyBinding> m_Conflicts;
```

- `public static readonly Game.Input.ProxyBinding+Comparer pathAndModifiersComparer`  

```csharp
public static readonly Game.Input.ProxyBinding+Comparer pathAndModifiersComparer;
```

- `public static readonly Game.Input.ProxyBinding+Comparer onlyPathComparer`  

```csharp
public static readonly Game.Input.ProxyBinding+Comparer onlyPathComparer;
```

- `internal static readonly Game.Input.ProxyBinding+Comparer componentComparer`  

```csharp
internal static readonly Game.Input.ProxyBinding+Comparer componentComparer;
```


## Properties

- `public static Game.Input.ProxyBinding+Comparer defaultComparer { get }`  

```csharp
public static Game.Input.ProxyBinding+Comparer defaultComparer { get; }
```

- `public static Game.Input.ProxyBinding+ModifiersListComparer defaultModifiersComparer { get }`  

```csharp
public static Game.Input.ProxyBinding+ModifiersListComparer defaultModifiersComparer { get; }
```

- `public System.String mapName { get }`  

```csharp
public System.String mapName { get; }
```

- `public System.String actionName { get }`  

```csharp
public System.String actionName { get; }
```

- `public Game.Input.ActionComponent component { get }`  

```csharp
public Game.Input.ActionComponent component { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `internal Game.Input.ProxyAction action { internal get }`  

```csharp
internal Game.Input.ProxyAction action { internal get; }
```

- `public System.Boolean isBuiltIn { get }`  

```csharp
public System.Boolean isBuiltIn { get; }
```

- `public System.Boolean isRebindable { get }`  

```csharp
public System.Boolean isRebindable { get; }
```

- `public System.Boolean isModifiersRebindable { get }`  

```csharp
public System.Boolean isModifiersRebindable { get; }
```

- `public System.Boolean allowModifiers { get }`  

```csharp
public System.Boolean allowModifiers { get; }
```

- `public System.Boolean canBeEmpty { get }`  

```csharp
public System.Boolean canBeEmpty { get; }
```

- `public System.Boolean developerOnly { get }`  

```csharp
public System.Boolean developerOnly { get; }
```

- `internal System.Boolean isDummy { internal get }`  

```csharp
internal System.Boolean isDummy { internal get; }
```

- `internal System.Boolean isHidden { internal get }`  

```csharp
internal System.Boolean isHidden { internal get; }
```

- `internal Game.Input.OptionGroupOverride optionGroupOverride { internal get }`  

```csharp
internal Game.Input.OptionGroupOverride optionGroupOverride { internal get; }
```

- `public Game.Input.Usages usages { get }`  

```csharp
public Game.Input.Usages usages { get; }
```

- `public Game.Input.ProxyBinding original { get }`  

```csharp
public Game.Input.ProxyBinding original { get; }
```

- `public System.Boolean isOriginal { get }`  

```csharp
public System.Boolean isOriginal { get; }
```

- `public Game.Input.ProxyBinding+ConflictType hasConflicts { get }`  

```csharp
public Game.Input.ProxyBinding+ConflictType hasConflicts { get; }
```

- `public System.Collections.Generic.IList<Game.Input.ProxyBinding> conflicts { get }`  

```csharp
public System.Collections.Generic.IList<Game.Input.ProxyBinding> conflicts { get; }
```

- `public System.String path { get; set }`  

```csharp
public System.String path { get; set; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> modifiers { get; set }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> modifiers { get; set; }
```

- `public System.String originalPath { get; set }`  

```csharp
public System.String originalPath { get; set; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> originalModifiers { get; set }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> originalModifiers { get; set; }
```

- `public System.String group { get; set }`  

```csharp
public System.String group { get; set; }
```

- `public Game.Input.InputManager+DeviceType device { get; set }`  

```csharp
public Game.Input.InputManager+DeviceType device { get; set; }
```

- `public System.Boolean isKeyboard { get }`  

```csharp
public System.Boolean isKeyboard { get; }
```

- `public System.Boolean isMouse { get }`  

```csharp
public System.Boolean isMouse { get; }
```

- `public System.Boolean isGamepad { get }`  

```csharp
public System.Boolean isGamepad { get; }
```

- `public System.Boolean isSet { get }`  

```csharp
public System.Boolean isSet { get; }
```

- `internal Game.Input.UIBaseInputAction alies { internal get; internal set }`  

```csharp
internal Game.Input.UIBaseInputAction alies { internal get; internal set; }
```

- `internal System.Boolean isAlias { internal get }`  

```csharp
internal System.Boolean isAlias { internal get; }
```

- `public System.String title { get }`  

```csharp
public System.String title { get; }
```


## Constructors

- `public ProxyBinding(System.String mapName, System.String actionName, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source)`  

```csharp
public ProxyBinding(System.String mapName, System.String actionName, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source);
```

- `public ProxyBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source)`  

```csharp
public ProxyBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source);
```


## Methods

- `public static ConflictsWith(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage) : System.Boolean`  

```csharp
public static System.Boolean ConflictsWith(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage);
```

- `public Copy() : Game.Input.ProxyBinding`  

```csharp
public Game.Input.ProxyBinding Copy();
```

- `internal CreateWatcher(System.Action<Game.Input.ProxyBinding> onChange = null) : Game.Input.ProxyBinding+Watcher`  

```csharp
internal Game.Input.ProxyBinding+Watcher CreateWatcher(System.Action<Game.Input.ProxyBinding> onChange);
```

- `public Equals(Game.Input.ProxyBinding other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Input.ProxyBinding other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `internal GetOptionsGroup() : System.String`  

```csharp
internal System.String GetOptionsGroup();
```

- `public static PathEquals(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y) : System.Boolean`  

```csharp
public static System.Boolean PathEquals(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y);
```

- `public ResetConflictCache() : System.Void`  

```csharp
public System.Void ResetConflictCache();
```

- `private SetModifiers(Game.Input.ProxyModifier[]& field, System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> value) : System.Void`  

```csharp
private System.Void SetModifiers(Game.Input.ProxyModifier[]& field, System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> value);
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static System.Void SupportValueTypesForAOT();
```

- `public ToHumanReadablePath() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> ToHumanReadablePath();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public WithModifiers(System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> newModifiers) : Game.Input.ProxyBinding`  

```csharp
public Game.Input.ProxyBinding WithModifiers(System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> newModifiers);
```

- `public WithPath(System.String newPath) : Game.Input.ProxyBinding`  

```csharp
public Game.Input.ProxyBinding WithPath(System.String newPath);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.Input.ProxyBinding+Comparer`  
- `Game.Input.ProxyBinding+ModifiersListComparer`  
- `Game.Input.ProxyBinding+Watcher`  
- `Game.Input.ProxyBinding+ConflictType`  
- `Game.Input.ProxyBinding+<>c`  
- `Game.Input.ProxyBinding+<ToHumanReadablePath>d__98`  

