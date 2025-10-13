# Colossal.Logging.Level

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable`, `System.IEquatable<Colossal.Logging.Level>`  

## Code

```csharp
public class Level : System.IComparable, System.IEquatable<Colossal.Logging.Level>
{
    private readonly System.String m_Name;
    private readonly System.Int32 m_Severity;
    public static readonly Colossal.Logging.Level Disabled;
    public static readonly Colossal.Logging.Level Emergency;
    public static readonly Colossal.Logging.Level Fatal;
    public static readonly Colossal.Logging.Level Critical;
    public static readonly Colossal.Logging.Level Error;
    public static readonly Colossal.Logging.Level Warn;
    public static readonly Colossal.Logging.Level Info;
    public static readonly Colossal.Logging.Level Debug;
    public static readonly Colossal.Logging.Level Trace;
    public static readonly Colossal.Logging.Level Verbose;
    public static readonly Colossal.Logging.Level All;
    public static const System.Int32 kDisabledSeverity;
    public static const System.Int32 kEmergencySeverity;
    public static const System.Int32 kFatalSeverity;
    public static const System.Int32 kCriticalSeverity;
    public static const System.Int32 kErrorSeverity;
    public static const System.Int32 kWarnSeverity;
    public static const System.Int32 kInfoSeverity;
    public static const System.Int32 kDebugSeverity;
    public static const System.Int32 kTraceSeverity;
    public static const System.Int32 kVerboseSeverity;
    public static const System.Int32 kAllSeverity;

    public System.String name { get; }
    public System.Int32 severity { get; }

    public Level(System.String name, System.Int32 severity);

    public static System.Int32 Compare(Colossal.Logging.Level l, Colossal.Logging.Level r);
    public System.Int32 CompareTo(System.Object obj);
    public virtual System.Boolean Equals(System.Object o);
    public System.Boolean Equals(Colossal.Logging.Level otherLevel);
    public virtual System.Int32 GetHashCode();
    public static Colossal.Logging.Level GetLevel(System.Int32 severity);
    public static Colossal.Logging.Level GetLevel(System.String severity);
    public static System.Collections.Generic.IEnumerable<Colossal.Logging.Level> GetLevels();
    public virtual System.String ToString();
}
```


## Fields

- `private readonly System.String m_Name`  

```csharp
private readonly System.String m_Name;
```

- `private readonly System.Int32 m_Severity`  

```csharp
private readonly System.Int32 m_Severity;
```

- `public static readonly Colossal.Logging.Level Disabled`  

```csharp
public static readonly Colossal.Logging.Level Disabled;
```

- `public static readonly Colossal.Logging.Level Emergency`  

```csharp
public static readonly Colossal.Logging.Level Emergency;
```

- `public static readonly Colossal.Logging.Level Fatal`  

```csharp
public static readonly Colossal.Logging.Level Fatal;
```

- `public static readonly Colossal.Logging.Level Critical`  

```csharp
public static readonly Colossal.Logging.Level Critical;
```

- `public static readonly Colossal.Logging.Level Error`  

```csharp
public static readonly Colossal.Logging.Level Error;
```

- `public static readonly Colossal.Logging.Level Warn`  

```csharp
public static readonly Colossal.Logging.Level Warn;
```

- `public static readonly Colossal.Logging.Level Info`  

```csharp
public static readonly Colossal.Logging.Level Info;
```

- `public static readonly Colossal.Logging.Level Debug`  

```csharp
public static readonly Colossal.Logging.Level Debug;
```

- `public static readonly Colossal.Logging.Level Trace`  

```csharp
public static readonly Colossal.Logging.Level Trace;
```

- `public static readonly Colossal.Logging.Level Verbose`  

```csharp
public static readonly Colossal.Logging.Level Verbose;
```

- `public static readonly Colossal.Logging.Level All`  

```csharp
public static readonly Colossal.Logging.Level All;
```

- `public static const System.Int32 kDisabledSeverity`  

```csharp
public static const System.Int32 kDisabledSeverity;
```

- `public static const System.Int32 kEmergencySeverity`  

```csharp
public static const System.Int32 kEmergencySeverity;
```

- `public static const System.Int32 kFatalSeverity`  

```csharp
public static const System.Int32 kFatalSeverity;
```

- `public static const System.Int32 kCriticalSeverity`  

```csharp
public static const System.Int32 kCriticalSeverity;
```

- `public static const System.Int32 kErrorSeverity`  

```csharp
public static const System.Int32 kErrorSeverity;
```

- `public static const System.Int32 kWarnSeverity`  

```csharp
public static const System.Int32 kWarnSeverity;
```

- `public static const System.Int32 kInfoSeverity`  

```csharp
public static const System.Int32 kInfoSeverity;
```

- `public static const System.Int32 kDebugSeverity`  

```csharp
public static const System.Int32 kDebugSeverity;
```

- `public static const System.Int32 kTraceSeverity`  

```csharp
public static const System.Int32 kTraceSeverity;
```

- `public static const System.Int32 kVerboseSeverity`  

```csharp
public static const System.Int32 kVerboseSeverity;
```

- `public static const System.Int32 kAllSeverity`  

```csharp
public static const System.Int32 kAllSeverity;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Int32 severity { get }`  

```csharp
public System.Int32 severity { get; }
```


## Constructors

- `public Level(System.String name, System.Int32 severity)`  

```csharp
public Level(System.String name, System.Int32 severity);
```


## Methods

- `public static Compare(Colossal.Logging.Level l, Colossal.Logging.Level r) : System.Int32`  

```csharp
public static System.Int32 Compare(Colossal.Logging.Level l, Colossal.Logging.Level r);
```

- `public CompareTo(System.Object obj) : System.Int32`  

```csharp
public System.Int32 CompareTo(System.Object obj);
```

- `public virtual Equals(System.Object o) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object o);
```

- `public Equals(Colossal.Logging.Level otherLevel) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Logging.Level otherLevel);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public static GetLevel(System.Int32 severity) : Colossal.Logging.Level`  

```csharp
public static Colossal.Logging.Level GetLevel(System.Int32 severity);
```

- `public static GetLevel(System.String severity) : Colossal.Logging.Level`  

```csharp
public static Colossal.Logging.Level GetLevel(System.String severity);
```

- `public static GetLevels() : System.Collections.Generic.IEnumerable<Colossal.Logging.Level>`  

```csharp
public static System.Collections.Generic.IEnumerable<Colossal.Logging.Level> GetLevels();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


## Nested types

- `Colossal.Logging.Level+<GetLevels>d__22`  

