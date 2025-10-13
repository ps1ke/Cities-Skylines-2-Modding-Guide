# Colossal.FormatUtils

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class FormatUtils
{
    private static readonly System.String[] kTimeStampFormats;

    public static System.String FormatBytes(System.Int64 b);
    public static System.String FormatTime(System.Int32 durationSecs);
    public static System.String FormatTime(System.Double durationSecs);
    public static System.String FormatTimeDebug(System.Double durationMs);
    public static System.String FormatTimeDebug(System.Int32 durationSecs);
    public static System.String FormatTimeMs(System.Double durationSecs);
    public static System.Int32 ParseTimeToSeconds(System.String clock);
}
```


## Fields

- `private static readonly System.String[] kTimeStampFormats`  

```csharp
private static readonly System.String[] kTimeStampFormats;
```


## Methods

- `public static FormatBytes(System.Int64 b) : System.String`  

```csharp
public static System.String FormatBytes(System.Int64 b);
```

- `public static FormatTime(System.Int32 durationSecs) : System.String`  

```csharp
public static System.String FormatTime(System.Int32 durationSecs);
```

- `public static FormatTime(System.Double durationSecs) : System.String`  

```csharp
public static System.String FormatTime(System.Double durationSecs);
```

- `public static FormatTimeDebug(System.Double durationMs) : System.String`  

```csharp
public static System.String FormatTimeDebug(System.Double durationMs);
```

- `public static FormatTimeDebug(System.Int32 durationSecs) : System.String`  

```csharp
public static System.String FormatTimeDebug(System.Int32 durationSecs);
```

- `public static FormatTimeMs(System.Double durationSecs) : System.String`  

```csharp
public static System.String FormatTimeMs(System.Double durationSecs);
```

- `public static ParseTimeToSeconds(System.String clock) : System.Int32`  

```csharp
public static System.Int32 ParseTimeToSeconds(System.String clock);
```


