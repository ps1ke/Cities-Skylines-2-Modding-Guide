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
public ProxyBinding(string mapName, string actionName, ActionComponent component, string name, CompositeInstance source)
	{
		m_MapName = mapName;
		m_ActionName = actionName;
		m_Component = component;
		m_Name = name;
		m_Source = source;
		m_Device = InputManager.DeviceType.None;
		m_Path = string.Empty;
		m_Modifiers = Array.Empty<ProxyModifier>();
		m_OriginalPath = null;
		m_OriginalModifiers = null;
		m_Alies = null;
		m_HasConflicts = ConflictType.None;
		m_Conflicts = Array.Empty<ProxyBinding>();
		m_ConflictVersion = -1;
		m_HasConflictVersion = -1;
	}
```

- `public ProxyBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source)`  

```csharp
public ProxyBinding(string mapName, string actionName, ActionComponent component, string name, CompositeInstance source)
	{
		m_MapName = mapName;
		m_ActionName = actionName;
		m_Component = component;
		m_Name = name;
		m_Source = source;
		m_Device = InputManager.DeviceType.None;
		m_Path = string.Empty;
		m_Modifiers = Array.Empty<ProxyModifier>();
		m_OriginalPath = null;
		m_OriginalModifiers = null;
		m_Alies = null;
		m_HasConflicts = ConflictType.None;
		m_Conflicts = Array.Empty<ProxyBinding>();
		m_ConflictVersion = -1;
		m_HasConflictVersion = -1;
	}
```


## Methods

- `public static ConflictsWith(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage) : System.Boolean`  

```csharp
public static bool ConflictsWith(ProxyBinding x, ProxyBinding y, bool checkUsage)
	{
		if (!x.isSet || !y.isSet)
		{
			return false;
		}
		if (x.m_Device != y.m_Device)
		{
			return false;
		}
		if (!((x.allowModifiers && y.allowModifiers) ? pathAndModifiersComparer : onlyPathComparer).Equals(x, y))
		{
			return false;
		}
		if (checkUsage && !Usages.TestAny(x.usages, y.usages))
		{
			return false;
		}
		return true;
	}
```

- `public Copy() : Game.Input.ProxyBinding`  

```csharp
public ProxyBinding Copy()
	{
		return new ProxyBinding
		{
			m_Source = m_Source,
			m_Component = m_Component,
			m_MapName = m_MapName,
			m_ActionName = m_ActionName,
			m_Name = m_Name,
			m_Device = m_Device,
			m_Path = m_Path,
			modifiers = modifiers,
			m_OriginalPath = m_OriginalPath,
			m_OriginalModifiers = m_OriginalModifiers,
			m_Alies = m_Alies,
			m_HasConflicts = m_HasConflicts,
			m_Conflicts = ((m_Conflicts.Count == 0) ? Array.Empty<ProxyBinding>() : m_Conflicts.ToArray()),
			m_ConflictVersion = m_ConflictVersion,
			m_HasConflictVersion = m_HasConflictVersion
		};
	}
```

- `internal CreateWatcher(System.Action<Game.Input.ProxyBinding> onChange = null) : Game.Input.ProxyBinding+Watcher`  

```csharp
internal Watcher CreateWatcher(Action<ProxyBinding> onChange = null)
	{
		return new Watcher(this, onChange);
	}
```

- `public Equals(Game.Input.ProxyBinding other) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is ProxyBinding y)
		{
			return Comparer.defaultComparer.Equals(this, y);
		}
		return false;
	}
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is ProxyBinding y)
		{
			return Comparer.defaultComparer.Equals(this, y);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return Comparer.defaultComparer.GetHashCode(this);
	}
```

- `internal GetOptionsGroup() : System.String`  

```csharp
internal string GetOptionsGroup()
	{
		if (optionGroupOverride == OptionGroupOverride.None)
		{
			return mapName;
		}
		FieldInfo field = typeof(OptionGroupOverride).GetField(optionGroupOverride.ToString());
		if (field == null)
		{
			return mapName;
		}
		DescriptionAttribute descriptionAttribute = field.GetCustomAttributes(inherit: false).OfType<DescriptionAttribute>().FirstOrDefault();
		if (descriptionAttribute == null)
		{
			return mapName;
		}
		return descriptionAttribute.Description;
	}
```

- `public static PathEquals(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y) : System.Boolean`  

```csharp
public static bool PathEquals(ProxyBinding x, ProxyBinding y)
	{
		return ((x.allowModifiers && y.allowModifiers) ? pathAndModifiersComparer : onlyPathComparer).Equals(x, y);
	}
```

- `public ResetConflictCache() : System.Void`  

```csharp
public void ResetConflictCache()
	{
		m_ConflictVersion = -1;
		m_HasConflictVersion = -1;
	}
```

- `private SetModifiers(Game.Input.ProxyModifier[]& field, System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> value) : System.Void`  

```csharp
private void SetModifiers(out ProxyModifier[] field, IReadOnlyList<ProxyModifier> value)
	{
		if (value == null || value.Count == 0)
		{
			field = Array.Empty<ProxyModifier>();
			return;
		}
		if (value.Count == 1)
		{
			field = value.ToArray();
			return;
		}
		field = value.Distinct(ProxyModifier.pathComparer).ToArray();
		Array.Sort(field, ProxyModifier.pathComparer);
	}
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static void SupportValueTypesForAOT()
	{
		JSON.SupportTypeForAOT<ProxyBinding>();
	}
```

- `public ToHumanReadablePath() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
public IEnumerable<string> ToHumanReadablePath()
	{
		if (!string.IsNullOrEmpty(m_Path))
		{
			ProxyModifier[] array = m_Modifiers;
			for (int i = 0; i < array.Length; i++)
			{
				ProxyModifier proxyModifier = array[i];
				yield return ControlPath.ToHumanReadablePath(proxyModifier.m_Path);
			}
			yield return ControlPath.ToHumanReadablePath(m_Path);
		}
	}
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return string.Format("{0}/{1}/{2} - [{3}] ({4})", m_MapName, m_ActionName, m_Name, string.IsNullOrEmpty(m_Path) ? "Not set" : string.Join(" + ", m_Modifiers.Select((ProxyModifier m) => m.m_Path).Append(m_Path)), usages);
	}
```

- `public WithModifiers(System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> newModifiers) : Game.Input.ProxyBinding`  

```csharp
public ProxyBinding WithModifiers(IReadOnlyList<ProxyModifier> newModifiers)
	{
		modifiers = newModifiers;
		return this;
	}
```

- `public WithPath(System.String newPath) : Game.Input.ProxyBinding`  

```csharp
public ProxyBinding WithPath(string newPath)
	{
		path = newPath;
		return this;
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(typeof(ProxyBinding).FullName);
		writer.PropertyName("binding");
		writer.Write(ControlPath.Get(m_Path));
		writer.PropertyName("modifiers");
		writer.Write((IList<ControlPath>)m_Modifiers.Select((ProxyModifier m) => ControlPath.Get(m.m_Path)).ToArray());
		writer.PropertyName("name");
		writer.Write(m_Name);
		writer.PropertyName("map");
		writer.Write(m_MapName);
		writer.PropertyName("action");
		writer.Write(m_ActionName);
		writer.PropertyName("title");
		writer.Write(title);
		writer.PropertyName("optionGroup");
		writer.Write(GetOptionsGroup());
		writer.PropertyName("device");
		writer.Write(device.ToString());
		writer.PropertyName("isBuiltIn");
		writer.Write(isBuiltIn);
		writer.PropertyName("canBeEmpty");
		writer.Write(canBeEmpty);
		writer.PropertyName("isRebindable");
		writer.Write(isRebindable);
		writer.PropertyName("isOriginal");
		writer.Write(isOriginal);
		writer.PropertyName("allowModifiers");
		writer.Write(allowModifiers && isModifiersRebindable);
		writer.PropertyName("hasConflicts");
		writer.Write((int)hasConflicts);
		writer.TypeEnd();
	}
```


## Nested types

- `Game.Input.ProxyBinding+Comparer`  
- `Game.Input.ProxyBinding+ModifiersListComparer`  
- `Game.Input.ProxyBinding+Watcher`  
- `Game.Input.ProxyBinding+ConflictType`  
- `Game.Input.ProxyBinding+<>c`  
- `Game.Input.ProxyBinding+<ToHumanReadablePath>d__98`  

