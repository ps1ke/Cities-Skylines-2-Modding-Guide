# Colossal.Logging.Diagnostics.StackTraceHelper

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging.Diagnostics`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class StackTraceHelper
{
    private static System.Void ExtractFormattedStackTrace(System.IO.StreamWriter writer, System.Diagnostics.StackTrace stackTrace);
    private static System.Void ExtractFormattedStackTrace(System.Text.StringBuilder sb, System.Type startAfter, System.Diagnostics.StackTrace stackTrace);
    internal static System.Void ExtractStackTrace(System.IO.StreamWriter writer, System.Int32 skipFrames);
    public static System.String ExtractStackTrace(System.Int32 skipFrames, System.Type startAfter, System.Text.StringBuilder sb);
    public static System.Void ExtractStackTraceFromException(System.Exception exception, System.IO.StreamWriter writer);
    public static System.String ExtractStackTraceFromException(System.Exception exception, System.Text.StringBuilder sb);
}
```


## Methods

- `private static ExtractFormattedStackTrace(System.IO.StreamWriter writer, System.Diagnostics.StackTrace stackTrace) : System.Void`  

```csharp
private static System.Void ExtractFormattedStackTrace(System.IO.StreamWriter writer, System.Diagnostics.StackTrace stackTrace);
```

- `private static ExtractFormattedStackTrace(System.Text.StringBuilder sb, System.Type startAfter, System.Diagnostics.StackTrace stackTrace) : System.Void`  

```csharp
private static System.Void ExtractFormattedStackTrace(System.Text.StringBuilder sb, System.Type startAfter, System.Diagnostics.StackTrace stackTrace);
```

- `internal static ExtractStackTrace(System.IO.StreamWriter writer, System.Int32 skipFrames = 7) : System.Void`  

```csharp
internal static System.Void ExtractStackTrace(System.IO.StreamWriter writer, System.Int32 skipFrames);
```

- `public static ExtractStackTrace(System.Int32 skipFrames, System.Type startAfter = null, System.Text.StringBuilder sb = null) : System.String`  

```csharp
public static System.String ExtractStackTrace(System.Int32 skipFrames, System.Type startAfter, System.Text.StringBuilder sb);
```

- `public static ExtractStackTraceFromException(System.Exception exception, System.IO.StreamWriter writer) : System.Void`  

```csharp
public static System.Void ExtractStackTraceFromException(System.Exception exception, System.IO.StreamWriter writer);
```

- `public static ExtractStackTraceFromException(System.Exception exception, System.Text.StringBuilder sb = null) : System.String`  

```csharp
public static System.String ExtractStackTraceFromException(System.Exception exception, System.Text.StringBuilder sb);
```


