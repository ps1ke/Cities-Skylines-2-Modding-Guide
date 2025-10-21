# Game.Input.Usages

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IEnumerable<System.Int32>`, `System.Collections.IEnumerable`, `System.IEquatable<Game.Input.Usages>`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public sealed struct Usages : System.Collections.Generic.IEnumerable<System.Int32>, System.Collections.IEnumerable, System.IEquatable<Game.Input.Usages>
{
    private System.UInt64[] m_Value;
    private System.Boolean m_ReadOnly;
    private static readonly System.Collections.Generic.Dictionary<System.String, System.Int32> <usagesMap>k__BackingField;
    private static readonly Game.Input.Usages <defaultUsages>k__BackingField;
    public static const System.String kMenuUsage;
    public static const System.String kDefaultUsage;
    public static const System.String kOverlayUsage;
    public static const System.String kToolUsage;
    public static const System.String kCancelableToolUsage;
    public static const System.String kDebugUsage;
    public static const System.String kEditorUsage;
    public static const System.String kPhotoModeUsage;
    public static const System.String kOptionsUsage;
    public static const System.String kTutorialUsage;
    public static const System.String kDiscardableToolUsage;

    internal static System.Collections.Generic.Dictionary<System.String, System.Int32> usagesMap { internal get; }
    public static Game.Input.Usages defaultUsages { get; }
    public static Game.Input.Usages empty { get; }
    public System.Boolean Item { get; set; }
    public System.Boolean Item { get; set; }
    public System.Boolean isReadOnly { get; }
    public System.Boolean isNone { get; }
    public UnityEngine.InputSystem.Utilities.NameAndParameters parameters { get; set; }

    public Usages(System.Int32 length, System.Boolean readOnly);
    public Usages(System.Boolean readOnly, System.Int32[] values);
    public Usages(Game.Input.BuiltInUsages usages, System.Boolean readOnly);
    internal Usages(System.Boolean readOnly, System.String[] customUsages);

    internal static System.Int32 AddOrGetUsage(System.String usageName);
    public static Game.Input.Usages Combine(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly);
    public Game.Input.Usages Copy(System.Boolean readOnly);
    private System.Collections.Generic.IEnumerable<System.Int32> Enumerate();
    public System.Boolean Equals(Game.Input.Usages other);
    public System.Collections.IEnumerator GetEnumerator();
    public static Game.Input.Usages Intersect(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly);
    internal System.Void MakeEditable();
    internal System.Void MakeReadOnly();
    public System.Void SetFrom(Game.Input.Usages source);
    private System.Collections.Generic.IEnumerator<System.Int32> System.Collections.Generic.IEnumerable<System.Int32>.GetEnumerator();
    public static System.Boolean TestAll(Game.Input.Usages usages1, Game.Input.Usages usages2);
    public static System.Boolean TestAny(Game.Input.Usages usages1, Game.Input.Usages usages2);
    public virtual System.String ToString();
}
```


## Fields

- `private System.UInt64[] m_Value`  

```csharp
private System.UInt64[] m_Value;
```

- `private System.Boolean m_ReadOnly`  

```csharp
private System.Boolean m_ReadOnly;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, System.Int32> <usagesMap>k__BackingField`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, System.Int32> <usagesMap>k__BackingField;
```

- `private static readonly Game.Input.Usages <defaultUsages>k__BackingField`  

```csharp
private static readonly Game.Input.Usages <defaultUsages>k__BackingField;
```

- `public static const System.String kMenuUsage`  

```csharp
public static const System.String kMenuUsage;
```

- `public static const System.String kDefaultUsage`  

```csharp
public static const System.String kDefaultUsage;
```

- `public static const System.String kOverlayUsage`  

```csharp
public static const System.String kOverlayUsage;
```

- `public static const System.String kToolUsage`  

```csharp
public static const System.String kToolUsage;
```

- `public static const System.String kCancelableToolUsage`  

```csharp
public static const System.String kCancelableToolUsage;
```

- `public static const System.String kDebugUsage`  

```csharp
public static const System.String kDebugUsage;
```

- `public static const System.String kEditorUsage`  

```csharp
public static const System.String kEditorUsage;
```

- `public static const System.String kPhotoModeUsage`  

```csharp
public static const System.String kPhotoModeUsage;
```

- `public static const System.String kOptionsUsage`  

```csharp
public static const System.String kOptionsUsage;
```

- `public static const System.String kTutorialUsage`  

```csharp
public static const System.String kTutorialUsage;
```

- `public static const System.String kDiscardableToolUsage`  

```csharp
public static const System.String kDiscardableToolUsage;
```


## Properties

- `internal static System.Collections.Generic.Dictionary<System.String, System.Int32> usagesMap { internal get }`  

```csharp
internal static System.Collections.Generic.Dictionary<System.String, System.Int32> usagesMap { internal get; }
```

- `public static Game.Input.Usages defaultUsages { get }`  

```csharp
public static Game.Input.Usages defaultUsages { get; }
```

- `public static Game.Input.Usages empty { get }`  

```csharp
public static Game.Input.Usages empty { get; }
```

- `public System.Boolean Item { get; set }`  

```csharp
public System.Boolean Item { get; set; }
```

- `public System.Boolean Item { get; set }`  

```csharp
public System.Boolean Item { get; set; }
```

- `public System.Boolean isReadOnly { get }`  

```csharp
public System.Boolean isReadOnly { get; }
```

- `public System.Boolean isNone { get }`  

```csharp
public System.Boolean isNone { get; }
```

- `public UnityEngine.InputSystem.Utilities.NameAndParameters parameters { get; set }`  

```csharp
public UnityEngine.InputSystem.Utilities.NameAndParameters parameters { get; set; }
```


## Constructors

- `public Usages(System.Int32 length = 0, System.Boolean readOnly = True)`  

```csharp
public Usages(System.Int32 length, System.Boolean readOnly);
```

- `public Usages(System.Boolean readOnly = True, System.Int32[] values)`  

```csharp
public Usages(System.Boolean readOnly, System.Int32[] values);
```

- `public Usages(Game.Input.BuiltInUsages usages, System.Boolean readOnly = True)`  

```csharp
public Usages(Game.Input.BuiltInUsages usages, System.Boolean readOnly);
```

- `internal Usages(System.Boolean readOnly = True, System.String[] customUsages)`  

```csharp
internal Usages(System.Boolean readOnly, System.String[] customUsages);
```


## Methods

- `internal static AddOrGetUsage(System.String usageName) : System.Int32`  

```csharp
internal static System.Int32 AddOrGetUsage(System.String usageName);
```

- `public static Combine(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly = True) : Game.Input.Usages`  

```csharp
public static Game.Input.Usages Combine(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly);
```

- `public Copy(System.Boolean readOnly = True) : Game.Input.Usages`  

```csharp
public Game.Input.Usages Copy(System.Boolean readOnly);
```

- `private Enumerate() : System.Collections.Generic.IEnumerable<System.Int32>`  

```csharp
private System.Collections.Generic.IEnumerable<System.Int32> Enumerate();
```

- `public Equals(Game.Input.Usages other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Input.Usages other);
```

- `public GetEnumerator() : System.Collections.IEnumerator`  

```csharp
public System.Collections.IEnumerator GetEnumerator();
```

- `public static Intersect(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly = True) : Game.Input.Usages`  

```csharp
public static Game.Input.Usages Intersect(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly);
```

- `internal MakeEditable() : System.Void`  

```csharp
internal System.Void MakeEditable();
```

- `internal MakeReadOnly() : System.Void`  

```csharp
internal System.Void MakeReadOnly();
```

- `public SetFrom(Game.Input.Usages source) : System.Void`  

```csharp
public System.Void SetFrom(Game.Input.Usages source);
```

- `private System.Collections.Generic.IEnumerable<System.Int32>.GetEnumerator() : System.Collections.Generic.IEnumerator<System.Int32>`  

```csharp
private System.Collections.Generic.IEnumerator<System.Int32> System.Collections.Generic.IEnumerable<System.Int32>.GetEnumerator();
```

- `public static TestAll(Game.Input.Usages usages1, Game.Input.Usages usages2) : System.Boolean`  

```csharp
public static System.Boolean TestAll(Game.Input.Usages usages1, Game.Input.Usages usages2);
```

- `public static TestAny(Game.Input.Usages usages1, Game.Input.Usages usages2) : System.Boolean`  

```csharp
public static System.Boolean TestAny(Game.Input.Usages usages1, Game.Input.Usages usages2);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


## Nested types

- `Game.Input.Usages+Comparer`  
- `Game.Input.Usages+<>c`  
- `Game.Input.Usages+<Enumerate>d__49`  

