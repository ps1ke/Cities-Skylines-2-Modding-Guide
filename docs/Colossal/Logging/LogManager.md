# Colossal.Logging.LogManager

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static readonly System.String kDefaultLogPath`  
- `private static System.Collections.Generic.Dictionary<System.String, Colossal.Logging.ILog> m_Loggers`  
- `private static Colossal.Logging.ILog <Default>k__BackingField`  
- `private static Colossal.Logging.ILog <FileSystem>k__BackingField`  
- `private static Colossal.Logging.Level <defaultEffectiveness>k__BackingField`  
- `private static System.Boolean <stdOutActive>k__BackingField`  
- `private static Colossal.Logging.ILogSettingsProvider s_LogProvider`  
- `public static const System.String kDefault`  
- `public static const System.String kFileSystem`  

## Properties

- `public static Colossal.Logging.ILog Default { get; private set }`  
- `public static Colossal.Logging.ILog FileSystem { get; private set }`  
- `public static Colossal.Logging.Level defaultEffectiveness { get; private set }`  
- `public static System.Boolean stdOutActive { get; set }`  

## Methods

- `private static AddBuiltinLoggers() : System.Void`  
- `public static AddLogger(Colossal.Logging.ILog logger) : System.Void`  
- `public static GetAllLoggers() : System.Collections.Generic.IReadOnlyCollection<Colossal.Logging.ILog>`  
- `public static GetLogger(System.String name) : Colossal.Logging.ILog`  
- `public static RefreshSettings() : System.Void`  
- `public static ReleaseResources() : System.Void`  
- `public static SetDefaultEffectiveness(Colossal.Logging.Level effectiveness) : System.Void`  
- `public static SetSettingsProvider(Colossal.Logging.ILogSettingsProvider provider) : System.Void`  

