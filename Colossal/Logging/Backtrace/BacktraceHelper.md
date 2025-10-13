# Colossal.Logging.Backtrace.BacktraceHelper

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging.Backtrace`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class BacktraceHelper
{
    public static System.Void SendReport(System.Exception exception, System.Collections.Generic.Dictionary<System.String, System.String> attributes, System.String[] fileList);
    public static System.Void SendReport(System.Exception exception, System.String[] fileList);
    public static System.Void SendReport(System.String message, System.String[] fileList);
    public static System.Void SendReport(System.Exception exception, System.Collections.Generic.Dictionary<System.String, System.String> attributes, System.Collections.Generic.List<System.String> attachmentPaths);
    public static System.Void SendReport(System.String message, System.Collections.Generic.Dictionary<System.String, System.String> attributes, System.Collections.Generic.List<System.String> attachmentPaths);
    public static System.Void SetDefaultAttributes(System.Collections.Generic.Dictionary<System.String, System.String> staticAttributes);
}
```


## Methods

- `public static SendReport(System.Exception exception, System.Collections.Generic.Dictionary<System.String, System.String> attributes = null, System.String[] fileList) : System.Void`  

```csharp
public static System.Void SendReport(System.Exception exception, System.Collections.Generic.Dictionary<System.String, System.String> attributes, System.String[] fileList);
```

- `public static SendReport(System.Exception exception, System.String[] fileList) : System.Void`  

```csharp
public static System.Void SendReport(System.Exception exception, System.String[] fileList);
```

- `public static SendReport(System.String message, System.String[] fileList) : System.Void`  

```csharp
public static System.Void SendReport(System.String message, System.String[] fileList);
```

- `public static SendReport(System.Exception exception, System.Collections.Generic.Dictionary<System.String, System.String> attributes = null, System.Collections.Generic.List<System.String> attachmentPaths = null) : System.Void`  

```csharp
public static System.Void SendReport(System.Exception exception, System.Collections.Generic.Dictionary<System.String, System.String> attributes, System.Collections.Generic.List<System.String> attachmentPaths);
```

- `public static SendReport(System.String message, System.Collections.Generic.Dictionary<System.String, System.String> attributes = null, System.Collections.Generic.List<System.String> attachmentPaths = null) : System.Void`  

```csharp
public static System.Void SendReport(System.String message, System.Collections.Generic.Dictionary<System.String, System.String> attributes, System.Collections.Generic.List<System.String> attachmentPaths);
```

- `public static SetDefaultAttributes(System.Collections.Generic.Dictionary<System.String, System.String> staticAttributes = null) : System.Void`  

```csharp
public static System.Void SetDefaultAttributes(System.Collections.Generic.Dictionary<System.String, System.String> staticAttributes);
```


