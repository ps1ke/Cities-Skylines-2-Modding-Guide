# Colossal.PSI.Environment.EnvPath

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Environment`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly Colossal.Logging.ILog log`  
- `public static readonly System.String kUserDataPath`  
- `public static readonly System.String kGameDataPath`  
- `public static readonly System.String kTempDataPath`  
- `public static readonly System.String kConsoleLogPath`  
- `public static readonly System.String kCacheDataPath`  
- `public static readonly System.String kContentPath`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.ValueTuple<System.Func<System.String>, System.String>> s_SpecialPaths`  
- `public static readonly System.String kVTSubPath`  
- `public static const System.String kAssetDataPathName`  
- `public static const System.String kVTPathName`  
- `public static const System.String kCachePathName`  
- `public static const System.String kContent`  

## Methods

- `public static GetSpecialPath<T>() : System.String`  
- `public static GetSpecialPath(System.Type type) : System.String`  
- `private static Log() : System.Void`  
- `public static RegisterSpecialPath<T>(System.Func<System.String> resolveFunc) : System.Void`  
- `public static UpdateSpecialPathCache() : System.Void`  
- `public static WipeTempPath() : System.Threading.Tasks.Task`  

## Nested types

- `Colossal.PSI.Environment.EnvPath+<>c`  
- `Colossal.PSI.Environment.EnvPath+<WipeTempPath>d__18`  

