# Colossal.PSI.Environment.EnvPath

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Environment`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class EnvPath
{
    private static readonly Colossal.Logging.ILog log;
    public static readonly System.String kUserDataPath;
    public static readonly System.String kGameDataPath;
    public static readonly System.String kTempDataPath;
    public static readonly System.String kConsoleLogPath;
    public static readonly System.String kCacheDataPath;
    public static readonly System.String kContentPath;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.ValueTuple<System.Func<System.String>, System.String>> s_SpecialPaths;
    public static readonly System.String kVTSubPath;
    public static const System.String kAssetDataPathName;
    public static const System.String kVTPathName;
    public static const System.String kCachePathName;
    public static const System.String kContent;

    public static System.String GetSpecialPath<T>();
    public static System.String GetSpecialPath(System.Type type);
    private static System.Void Log();
    public static System.Void RegisterSpecialPath<T>(System.Func<System.String> resolveFunc);
    public static System.Void UpdateSpecialPathCache();
    public static System.Threading.Tasks.Task WipeTempPath();
}
```


## Fields

- `private static readonly Colossal.Logging.ILog log`  

```csharp
private static readonly Colossal.Logging.ILog log;
```

- `public static readonly System.String kUserDataPath`  

```csharp
public static readonly System.String kUserDataPath;
```

- `public static readonly System.String kGameDataPath`  

```csharp
public static readonly System.String kGameDataPath;
```

- `public static readonly System.String kTempDataPath`  

```csharp
public static readonly System.String kTempDataPath;
```

- `public static readonly System.String kConsoleLogPath`  

```csharp
public static readonly System.String kConsoleLogPath;
```

- `public static readonly System.String kCacheDataPath`  

```csharp
public static readonly System.String kCacheDataPath;
```

- `public static readonly System.String kContentPath`  

```csharp
public static readonly System.String kContentPath;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.ValueTuple<System.Func<System.String>, System.String>> s_SpecialPaths`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.ValueTuple<System.Func<System.String>, System.String>> s_SpecialPaths;
```

- `public static readonly System.String kVTSubPath`  

```csharp
public static readonly System.String kVTSubPath;
```

- `public static const System.String kAssetDataPathName`  

```csharp
public static const System.String kAssetDataPathName;
```

- `public static const System.String kVTPathName`  

```csharp
public static const System.String kVTPathName;
```

- `public static const System.String kCachePathName`  

```csharp
public static const System.String kCachePathName;
```

- `public static const System.String kContent`  

```csharp
public static const System.String kContent;
```


## Methods

- `public static GetSpecialPath<T>() : System.String`  

```csharp
public static System.String GetSpecialPath<T>();
```

- `public static GetSpecialPath(System.Type type) : System.String`  

```csharp
public static System.String GetSpecialPath(System.Type type);
```

- `private static Log() : System.Void`  

```csharp
private static System.Void Log();
```

- `public static RegisterSpecialPath<T>(System.Func<System.String> resolveFunc) : System.Void`  

```csharp
public static System.Void RegisterSpecialPath<T>(System.Func<System.String> resolveFunc);
```

- `public static UpdateSpecialPathCache() : System.Void`  

```csharp
public static System.Void UpdateSpecialPathCache();
```

- `public static WipeTempPath() : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task WipeTempPath();
```


## Nested types

- `Colossal.PSI.Environment.EnvPath+<>c`  
- `Colossal.PSI.Environment.EnvPath+<WipeTempPath>d__18`  

