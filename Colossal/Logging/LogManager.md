# Colossal.Logging.LogManager

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class LogManager
{
    public static readonly System.String kDefaultLogPath;
    private static System.Collections.Generic.Dictionary<System.String, Colossal.Logging.ILog> m_Loggers;
    private static Colossal.Logging.ILog <Default>k__BackingField;
    private static Colossal.Logging.ILog <FileSystem>k__BackingField;
    private static Colossal.Logging.Level <defaultEffectiveness>k__BackingField;
    private static System.Boolean <stdOutActive>k__BackingField;
    private static Colossal.Logging.ILogSettingsProvider s_LogProvider;
    public static const System.String kDefault;
    public static const System.String kFileSystem;

    public static Colossal.Logging.ILog Default { get; private set; }
    public static Colossal.Logging.ILog FileSystem { get; private set; }
    public static Colossal.Logging.Level defaultEffectiveness { get; private set; }
    public static System.Boolean stdOutActive { get; set; }

    private static System.Void AddBuiltinLoggers();
    public static System.Void AddLogger(Colossal.Logging.ILog logger);
    public static System.Collections.Generic.IReadOnlyCollection<Colossal.Logging.ILog> GetAllLoggers();
    public static Colossal.Logging.ILog GetLogger(System.String name);
    public static System.Void RefreshSettings();
    public static System.Void ReleaseResources();
    public static System.Void SetDefaultEffectiveness(Colossal.Logging.Level effectiveness);
    public static System.Void SetSettingsProvider(Colossal.Logging.ILogSettingsProvider provider);
}
```


## Fields

- `public static readonly System.String kDefaultLogPath`  

```csharp
public static readonly System.String kDefaultLogPath;
```

- `private static System.Collections.Generic.Dictionary<System.String, Colossal.Logging.ILog> m_Loggers`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, Colossal.Logging.ILog> m_Loggers;
```

- `private static Colossal.Logging.ILog <Default>k__BackingField`  

```csharp
private static Colossal.Logging.ILog <Default>k__BackingField;
```

- `private static Colossal.Logging.ILog <FileSystem>k__BackingField`  

```csharp
private static Colossal.Logging.ILog <FileSystem>k__BackingField;
```

- `private static Colossal.Logging.Level <defaultEffectiveness>k__BackingField`  

```csharp
private static Colossal.Logging.Level <defaultEffectiveness>k__BackingField;
```

- `private static System.Boolean <stdOutActive>k__BackingField`  

```csharp
private static System.Boolean <stdOutActive>k__BackingField;
```

- `private static Colossal.Logging.ILogSettingsProvider s_LogProvider`  

```csharp
private static Colossal.Logging.ILogSettingsProvider s_LogProvider;
```

- `public static const System.String kDefault`  

```csharp
public static const System.String kDefault;
```

- `public static const System.String kFileSystem`  

```csharp
public static const System.String kFileSystem;
```


## Properties

- `public static Colossal.Logging.ILog Default { get; private set }`  

```csharp
public static Colossal.Logging.ILog Default { get; private set; }
```

- `public static Colossal.Logging.ILog FileSystem { get; private set }`  

```csharp
public static Colossal.Logging.ILog FileSystem { get; private set; }
```

- `public static Colossal.Logging.Level defaultEffectiveness { get; private set }`  

```csharp
public static Colossal.Logging.Level defaultEffectiveness { get; private set; }
```

- `public static System.Boolean stdOutActive { get; set }`  

```csharp
public static System.Boolean stdOutActive { get; set; }
```


## Methods

- `private static AddBuiltinLoggers() : System.Void`  

```csharp
private static System.Void AddBuiltinLoggers();
```

- `public static AddLogger(Colossal.Logging.ILog logger) : System.Void`  

```csharp
public static System.Void AddLogger(Colossal.Logging.ILog logger);
```

- `public static GetAllLoggers() : System.Collections.Generic.IReadOnlyCollection<Colossal.Logging.ILog>`  

```csharp
public static System.Collections.Generic.IReadOnlyCollection<Colossal.Logging.ILog> GetAllLoggers();
```

- `public static GetLogger(System.String name) : Colossal.Logging.ILog`  

```csharp
public static Colossal.Logging.ILog GetLogger(System.String name);
```

- `public static RefreshSettings() : System.Void`  

```csharp
public static System.Void RefreshSettings();
```

- `public static ReleaseResources() : System.Void`  

```csharp
public static System.Void ReleaseResources();
```

- `public static SetDefaultEffectiveness(Colossal.Logging.Level effectiveness) : System.Void`  

```csharp
public static System.Void SetDefaultEffectiveness(Colossal.Logging.Level effectiveness);
```

- `public static SetSettingsProvider(Colossal.Logging.ILogSettingsProvider provider) : System.Void`  

```csharp
public static System.Void SetSettingsProvider(Colossal.Logging.ILogSettingsProvider provider);
```


