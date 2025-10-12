# Game.Input.ProxyBinding

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Input.ProxyBinding>`, `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `private System.String m_MapName`  
- `private System.String m_ActionName`  
- `private Game.Input.ActionComponent m_Component`  
- `private System.String m_Name`  
- `private Game.Input.InputManager+DeviceType m_Device`  
- `private System.String m_Path`  
- `private Game.Input.ProxyModifier[] m_Modifiers`  
- `private System.String m_OriginalPath`  
- `private Game.Input.ProxyModifier[] m_OriginalModifiers`  
- `private Game.Input.CompositeInstance m_Source`  
- `private Game.Input.UIBaseInputAction m_Alies`  
- `private System.Int32 m_HasConflictVersion`  
- `private Game.Input.ProxyBinding+ConflictType m_HasConflicts`  
- `private System.Int32 m_ConflictVersion`  
- `private System.Collections.Generic.IList<Game.Input.ProxyBinding> m_Conflicts`  
- `public static readonly Game.Input.ProxyBinding+Comparer pathAndModifiersComparer`  
- `public static readonly Game.Input.ProxyBinding+Comparer onlyPathComparer`  
- `internal static readonly Game.Input.ProxyBinding+Comparer componentComparer`  

## Properties

- `public static Game.Input.ProxyBinding+Comparer defaultComparer { get }`  
- `public static Game.Input.ProxyBinding+ModifiersListComparer defaultModifiersComparer { get }`  
- `public System.String mapName { get }`  
- `public System.String actionName { get }`  
- `public Game.Input.ActionComponent component { get }`  
- `public System.String name { get }`  
- `internal Game.Input.ProxyAction action { internal get }`  
- `public System.Boolean isBuiltIn { get }`  
- `public System.Boolean isRebindable { get }`  
- `public System.Boolean isModifiersRebindable { get }`  
- `public System.Boolean allowModifiers { get }`  
- `public System.Boolean canBeEmpty { get }`  
- `public System.Boolean developerOnly { get }`  
- `internal System.Boolean isDummy { internal get }`  
- `internal System.Boolean isHidden { internal get }`  
- `internal Game.Input.OptionGroupOverride optionGroupOverride { internal get }`  
- `public Game.Input.Usages usages { get }`  
- `public Game.Input.ProxyBinding original { get }`  
- `public System.Boolean isOriginal { get }`  
- `public Game.Input.ProxyBinding+ConflictType hasConflicts { get }`  
- `public System.Collections.Generic.IList<Game.Input.ProxyBinding> conflicts { get }`  
- `public System.String path { get; set }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> modifiers { get; set }`  
- `public System.String originalPath { get; set }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> originalModifiers { get; set }`  
- `public System.String group { get; set }`  
- `public Game.Input.InputManager+DeviceType device { get; set }`  
- `public System.Boolean isKeyboard { get }`  
- `public System.Boolean isMouse { get }`  
- `public System.Boolean isGamepad { get }`  
- `public System.Boolean isSet { get }`  
- `internal Game.Input.UIBaseInputAction alies { internal get; internal set }`  
- `internal System.Boolean isAlias { internal get }`  
- `public System.String title { get }`  

## Constructors

- `public ProxyBinding(System.String mapName, System.String actionName, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source)`  
- `public ProxyBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ActionComponent component, System.String name, Game.Input.CompositeInstance source)`  

## Methods

- `public static ConflictsWith(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage) : System.Boolean`  
- `public Copy() : Game.Input.ProxyBinding`  
- `internal CreateWatcher(System.Action<Game.Input.ProxyBinding> onChange = null) : Game.Input.ProxyBinding+Watcher`  
- `public Equals(Game.Input.ProxyBinding other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `internal GetOptionsGroup() : System.String`  
- `public static PathEquals(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y) : System.Boolean`  
- `public ResetConflictCache() : System.Void`  
- `private SetModifiers(Game.Input.ProxyModifier[]& field, System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> value) : System.Void`  
- `private static SupportValueTypesForAOT() : System.Void`  
- `public ToHumanReadablePath() : System.Collections.Generic.IEnumerable<System.String>`  
- `public virtual ToString() : System.String`  
- `public WithModifiers(System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier> newModifiers) : Game.Input.ProxyBinding`  
- `public WithPath(System.String newPath) : Game.Input.ProxyBinding`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.Input.ProxyBinding+Comparer`  
- `Game.Input.ProxyBinding+ModifiersListComparer`  
- `Game.Input.ProxyBinding+Watcher`  
- `Game.Input.ProxyBinding+ConflictType`  
- `Game.Input.ProxyBinding+<>c`  
- `Game.Input.ProxyBinding+<ToHumanReadablePath>d__98`  

