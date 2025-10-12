# Colossal.Logging.Level

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable`, `System.IEquatable<Colossal.Logging.Level>`  

## Fields

- `private readonly System.String m_Name`  
- `private readonly System.Int32 m_Severity`  
- `public static readonly Colossal.Logging.Level Disabled`  
- `public static readonly Colossal.Logging.Level Emergency`  
- `public static readonly Colossal.Logging.Level Fatal`  
- `public static readonly Colossal.Logging.Level Critical`  
- `public static readonly Colossal.Logging.Level Error`  
- `public static readonly Colossal.Logging.Level Warn`  
- `public static readonly Colossal.Logging.Level Info`  
- `public static readonly Colossal.Logging.Level Debug`  
- `public static readonly Colossal.Logging.Level Trace`  
- `public static readonly Colossal.Logging.Level Verbose`  
- `public static readonly Colossal.Logging.Level All`  
- `public static const System.Int32 kDisabledSeverity`  
- `public static const System.Int32 kEmergencySeverity`  
- `public static const System.Int32 kFatalSeverity`  
- `public static const System.Int32 kCriticalSeverity`  
- `public static const System.Int32 kErrorSeverity`  
- `public static const System.Int32 kWarnSeverity`  
- `public static const System.Int32 kInfoSeverity`  
- `public static const System.Int32 kDebugSeverity`  
- `public static const System.Int32 kTraceSeverity`  
- `public static const System.Int32 kVerboseSeverity`  
- `public static const System.Int32 kAllSeverity`  

## Properties

- `public System.String name { get }`  
- `public System.Int32 severity { get }`  

## Constructors

- `public Level(System.String name, System.Int32 severity)`  

## Methods

- `public static Compare(Colossal.Logging.Level l, Colossal.Logging.Level r) : System.Int32`  
- `public CompareTo(System.Object obj) : System.Int32`  
- `public virtual Equals(System.Object o) : System.Boolean`  
- `public Equals(Colossal.Logging.Level otherLevel) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public static GetLevel(System.Int32 severity) : Colossal.Logging.Level`  
- `public static GetLevel(System.String severity) : Colossal.Logging.Level`  
- `public static GetLevels() : System.Collections.Generic.IEnumerable<Colossal.Logging.Level>`  
- `public virtual ToString() : System.String`  

## Nested types

- `Colossal.Logging.Level+<GetLevels>d__22`  

