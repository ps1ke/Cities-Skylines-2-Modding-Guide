# Game.Input.Usages

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IEnumerable<System.Int32>`, `System.Collections.IEnumerable`, `System.IEquatable<Game.Input.Usages>`  

**Attributes:** `DefaultMember`  

## Fields

- `private System.UInt64[] m_Value`  
- `private System.Boolean m_ReadOnly`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Int32> <usagesMap>k__BackingField`  
- `private static readonly Game.Input.Usages <defaultUsages>k__BackingField`  
- `public static const System.String kMenuUsage`  
- `public static const System.String kDefaultUsage`  
- `public static const System.String kOverlayUsage`  
- `public static const System.String kToolUsage`  
- `public static const System.String kCancelableToolUsage`  
- `public static const System.String kDebugUsage`  
- `public static const System.String kEditorUsage`  
- `public static const System.String kPhotoModeUsage`  
- `public static const System.String kOptionsUsage`  
- `public static const System.String kTutorialUsage`  
- `public static const System.String kDiscardableToolUsage`  

## Properties

- `internal static System.Collections.Generic.Dictionary<System.String, System.Int32> usagesMap { internal get }`  
- `public static Game.Input.Usages defaultUsages { get }`  
- `public static Game.Input.Usages empty { get }`  
- `public System.Boolean Item { get; set }`  
- `public System.Boolean Item { get; set }`  
- `public System.Boolean isReadOnly { get }`  
- `public System.Boolean isNone { get }`  
- `public UnityEngine.InputSystem.Utilities.NameAndParameters parameters { get; set }`  

## Constructors

- `public Usages(System.Int32 length = 0, System.Boolean readOnly = True)`  
- `public Usages(System.Boolean readOnly = True, System.Int32[] values)`  
- `public Usages(Game.Input.BuiltInUsages usages, System.Boolean readOnly = True)`  
- `internal Usages(System.Boolean readOnly = True, System.String[] customUsages)`  

## Methods

- `internal static AddOrGetUsage(System.String usageName) : System.Int32`  
- `public static Combine(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly = True) : Game.Input.Usages`  
- `public Copy(System.Boolean readOnly = True) : Game.Input.Usages`  
- `private Enumerate() : System.Collections.Generic.IEnumerable<System.Int32>`  
- `public Equals(Game.Input.Usages other) : System.Boolean`  
- `public GetEnumerator() : System.Collections.IEnumerator`  
- `public static Intersect(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly = True) : Game.Input.Usages`  
- `internal MakeEditable() : System.Void`  
- `internal MakeReadOnly() : System.Void`  
- `public SetFrom(Game.Input.Usages source) : System.Void`  
- `private System.Collections.Generic.IEnumerable<System.Int32>.GetEnumerator() : System.Collections.Generic.IEnumerator<System.Int32>`  
- `public static TestAll(Game.Input.Usages usages1, Game.Input.Usages usages2) : System.Boolean`  
- `public static TestAny(Game.Input.Usages usages1, Game.Input.Usages usages2) : System.Boolean`  
- `public virtual ToString() : System.String`  

## Nested types

- `Game.Input.Usages+Comparer`  
- `Game.Input.Usages+<>c`  
- `Game.Input.Usages+<Enumerate>d__49`  

