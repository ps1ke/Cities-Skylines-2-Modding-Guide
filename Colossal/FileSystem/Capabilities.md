# Colossal.FileSystem.Capabilities

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Capabilities
{
    private static Colossal.FileSystem.WatcherCapabilities s_Capabilities;
    private static System.Boolean m_CanDetectDirectoryCreate;
    private static System.Boolean m_CanDetectDirectoryDelete;
    private static System.Boolean m_CanDetectFileCreate;
    private static System.Boolean m_CanDetectFileChange;
    private static System.Boolean m_CanDetectFileDelete;

    public Capabilities();

    public static System.Threading.Tasks.Task CacheCapabilities();
    public static Colossal.FileSystem.WatcherCapabilities Get();
    private static System.Double timeSince(System.DateTime startTime);
}
```


## Fields

- `private static Colossal.FileSystem.WatcherCapabilities s_Capabilities`  

```csharp
private static Colossal.FileSystem.WatcherCapabilities s_Capabilities;
```

- `private static System.Boolean m_CanDetectDirectoryCreate`  

```csharp
private static System.Boolean m_CanDetectDirectoryCreate;
```

- `private static System.Boolean m_CanDetectDirectoryDelete`  

```csharp
private static System.Boolean m_CanDetectDirectoryDelete;
```

- `private static System.Boolean m_CanDetectFileCreate`  

```csharp
private static System.Boolean m_CanDetectFileCreate;
```

- `private static System.Boolean m_CanDetectFileChange`  

```csharp
private static System.Boolean m_CanDetectFileChange;
```

- `private static System.Boolean m_CanDetectFileDelete`  

```csharp
private static System.Boolean m_CanDetectFileDelete;
```


## Constructors

- `public Capabilities()`  

```csharp
public Capabilities();
```


## Methods

- `public static CacheCapabilities() : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task CacheCapabilities();
```

- `public static Get() : Colossal.FileSystem.WatcherCapabilities`  

```csharp
public static Colossal.FileSystem.WatcherCapabilities Get();
```

- `private static timeSince(System.DateTime startTime) : System.Double`  

```csharp
private static System.Double timeSince(System.DateTime startTime);
```


## Nested types

- `Colossal.FileSystem.Capabilities+<>c`  
- `Colossal.FileSystem.Capabilities+<>c__DisplayClass7_0`  
- `Colossal.FileSystem.Capabilities+<>c__DisplayClass7_1`  
- `Colossal.FileSystem.Capabilities+<CacheCapabilities>d__7`  

