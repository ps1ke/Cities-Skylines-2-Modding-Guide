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
public Usages(int length = 0, bool readOnly = true)
	{
		m_Value = ((length == 0) ? Array.Empty<ulong>() : new ulong[length]);
		m_ReadOnly = readOnly;
	}
```

- `public Usages(System.Boolean readOnly = True, System.Int32[] values)`  

```csharp
public Usages(int length = 0, bool readOnly = true)
	{
		m_Value = ((length == 0) ? Array.Empty<ulong>() : new ulong[length]);
		m_ReadOnly = readOnly;
	}
```

- `public Usages(Game.Input.BuiltInUsages usages, System.Boolean readOnly = True)`  

```csharp
public Usages(int length = 0, bool readOnly = true)
	{
		m_Value = ((length == 0) ? Array.Empty<ulong>() : new ulong[length]);
		m_ReadOnly = readOnly;
	}
```

- `internal Usages(System.Boolean readOnly = True, System.String[] customUsages)`  

```csharp
public Usages(int length = 0, bool readOnly = true)
	{
		m_Value = ((length == 0) ? Array.Empty<ulong>() : new ulong[length]);
		m_ReadOnly = readOnly;
	}
```


## Methods

- `internal static AddOrGetUsage(System.String usageName) : System.Int32`  

```csharp
internal static int AddOrGetUsage(string usageName)
	{
		if (!usagesMap.TryGetValue(usageName, out var value))
		{
			value = usagesMap.Count;
			usagesMap[usageName] = value;
		}
		return value;
	}
```

- `public static Combine(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly = True) : Game.Input.Usages`  

```csharp
public static Usages Combine(Usages usages1, Usages usages2, bool readOnly = true)
	{
		ulong[] array = usages1.m_Value ?? Array.Empty<ulong>();
		ulong[] array2 = usages2.m_Value ?? Array.Empty<ulong>();
		int num = Math.Max(array.Length, array2.Length);
		Usages result = new Usages(num, readOnly);
		for (int i = 0; i < num; i++)
		{
			result.m_Value[i] = ((i < array.Length) ? array[i] : 0) | ((i < array2.Length) ? array2[i] : 0);
		}
		return result;
	}
```

- `public Copy(System.Boolean readOnly = True) : Game.Input.Usages`  

```csharp
public Usages Copy(bool readOnly = true)
	{
		if (m_ReadOnly && readOnly)
		{
			return this;
		}
		Usages result = new Usages(m_Value.Length, readOnly);
		Array.Copy(m_Value, result.m_Value, m_Value.Length);
		return result;
	}
```

- `private Enumerate() : System.Collections.Generic.IEnumerable<System.Int32>`  

```csharp
private IEnumerable<int> Enumerate()
	{
		if (m_Value == null)
		{
			yield break;
		}
		for (int i = 0; i < m_Value.Length; i++)
		{
			for (int j = 0; j < 64; j++)
			{
				if ((m_Value[i] & (ulong)(1L << j)) != 0L)
				{
					yield return (i << 6) + j;
				}
			}
		}
	}
```

- `public Equals(Game.Input.Usages other) : System.Boolean`  

```csharp
public bool Equals(Usages other)
	{
		return Comparer.defaultComparer.Equals(this, other);
	}
```

- `public GetEnumerator() : System.Collections.IEnumerator`  

```csharp
public IEnumerator GetEnumerator()
	{
		return Enumerate().GetEnumerator();
	}
```

- `public static Intersect(Game.Input.Usages usages1, Game.Input.Usages usages2, System.Boolean readOnly = True) : Game.Input.Usages`  

```csharp
public static Usages Intersect(Usages usages1, Usages usages2, bool readOnly = true)
	{
		ulong[] array = usages1.m_Value ?? Array.Empty<ulong>();
		ulong[] array2 = usages2.m_Value ?? Array.Empty<ulong>();
		int num = Math.Max(array.Length, array2.Length);
		Usages result = new Usages(num, readOnly);
		for (int i = 0; i < num; i++)
		{
			result.m_Value[i] = ((i < array.Length) ? array[i] : 0) & ((i < array2.Length) ? array2[i] : 0);
		}
		return result;
	}
```

- `internal MakeEditable() : System.Void`  

```csharp
internal void MakeEditable()
	{
		m_ReadOnly = false;
	}
```

- `internal MakeReadOnly() : System.Void`  

```csharp
internal void MakeReadOnly()
	{
		m_ReadOnly = true;
	}
```

- `public SetFrom(Game.Input.Usages source) : System.Void`  

```csharp
public void SetFrom(Usages source)
	{
		if (m_ReadOnly)
		{
			throw new InvalidOperationException("Value is readonly");
		}
		if (m_Value == null)
		{
			if (source.m_Value == null || source.m_Value.Length == 0)
			{
				m_Value = Array.Empty<ulong>();
				return;
			}
			Array.Resize(ref m_Value, source.m_Value.Length);
		}
		Array.Copy(source.m_Value, m_Value, m_Value.Length);
	}
```

- `private System.Collections.Generic.IEnumerable<System.Int32>.GetEnumerator() : System.Collections.Generic.IEnumerator<System.Int32>`  

```csharp
public IEnumerator GetEnumerator()
	{
		return Enumerate().GetEnumerator();
	}
```

- `public static TestAll(Game.Input.Usages usages1, Game.Input.Usages usages2) : System.Boolean`  

```csharp
public static bool TestAll(Usages usages1, Usages usages2)
	{
		ulong[] array = usages1.m_Value ?? Array.Empty<ulong>();
		ulong[] array2 = usages2.m_Value ?? Array.Empty<ulong>();
		int num = Math.Max(array.Length, array2.Length);
		for (int i = 0; i < num; i++)
		{
			if (((i < array.Length) ? array[i] : 0) != ((i < array2.Length) ? array2[i] : 0))
			{
				return false;
			}
		}
		return true;
	}
```

- `public static TestAny(Game.Input.Usages usages1, Game.Input.Usages usages2) : System.Boolean`  

```csharp
public static bool TestAny(Usages usages1, Usages usages2)
	{
		ulong[] array = usages1.m_Value ?? Array.Empty<ulong>();
		ulong[] array2 = usages2.m_Value ?? Array.Empty<ulong>();
		int num = Math.Max(array.Length, array2.Length);
		for (int i = 0; i < num; i++)
		{
			if ((((i < array.Length) ? array[i] : 0) & ((i < array2.Length) ? array2[i] : 0)) != 0L)
			{
				return true;
			}
		}
		return false;
	}
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		if (m_Value != null)
		{
			return string.Join('|', this);
		}
		return "Empty";
	}
```


## Nested types

- `Game.Input.Usages+Comparer`  
- `Game.Input.Usages+<>c`  
- `Game.Input.Usages+<Enumerate>d__49`  

