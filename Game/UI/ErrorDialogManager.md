# Game.UI.ErrorDialogManager

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ErrorDialogManager
{
    private static System.Boolean m_Initialized;
    private static System.Boolean m_Enabled;
    private static System.Collections.Generic.Queue<Game.UI.ErrorDialog> m_ErrorDialogs;
    private static System.Single m_SimulationSpeed;

    public static System.Boolean enabled { get; set; }
    public static Game.UI.ErrorDialog currentErrorDialog { get; }

    public static System.Void Clear();
    public static System.Void DismissAllErrors();
    public static System.Void DismissCurrentErrorDialog();
    public static System.Void DisplayDebugErrorDialog();
    public static System.Void Dispose();
    private static Game.UI.ErrorDialog+Actions GetActions();
    private static System.String GetErrorDetail(System.Exception e, UnityEngine.Object context);
    private static System.Void HandlePause();
    public static System.Void Initialize();
    private static System.Void OnException(System.Exception e, UnityEngine.Object context);
    private static System.Void OnWarnOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context);
    private static System.Void RestorePause();
    public static System.Void ShowErrorDialog(Game.UI.ErrorDialog e);
    public static System.Boolean TryGetFirstError(System.String& error);
}
```


## Fields

- `private static System.Boolean m_Initialized`  

```csharp
private static System.Boolean m_Initialized;
```

- `private static System.Boolean m_Enabled`  

```csharp
private static System.Boolean m_Enabled;
```

- `private static System.Collections.Generic.Queue<Game.UI.ErrorDialog> m_ErrorDialogs`  

```csharp
private static System.Collections.Generic.Queue<Game.UI.ErrorDialog> m_ErrorDialogs;
```

- `private static System.Single m_SimulationSpeed`  

```csharp
private static System.Single m_SimulationSpeed;
```


## Properties

- `public static System.Boolean enabled { get; set }`  

```csharp
public static System.Boolean enabled { get; set; }
```

- `public static Game.UI.ErrorDialog currentErrorDialog { get }`  

```csharp
public static Game.UI.ErrorDialog currentErrorDialog { get; }
```


## Methods

- `public static Clear() : System.Void`  

```csharp
public static System.Void Clear();
```

- `public static DismissAllErrors() : System.Void`  

```csharp
public static System.Void DismissAllErrors();
```

- `public static DismissCurrentErrorDialog() : System.Void`  

```csharp
public static System.Void DismissCurrentErrorDialog();
```

- `public static DisplayDebugErrorDialog() : System.Void`  

```csharp
public static System.Void DisplayDebugErrorDialog();
```

- `public static Dispose() : System.Void`  

```csharp
public static System.Void Dispose();
```

- `private static GetActions() : Game.UI.ErrorDialog+Actions`  

```csharp
private static Game.UI.ErrorDialog+Actions GetActions();
```

- `private static GetErrorDetail(System.Exception e, UnityEngine.Object context) : System.String`  

```csharp
private static System.String GetErrorDetail(System.Exception e, UnityEngine.Object context);
```

- `private static HandlePause() : System.Void`  

```csharp
private static System.Void HandlePause();
```

- `public static Initialize() : System.Void`  

```csharp
public static System.Void Initialize();
```

- `private static OnException(System.Exception e, UnityEngine.Object context) : System.Void`  

```csharp
private static System.Void OnException(System.Exception e, UnityEngine.Object context);
```

- `private static OnWarnOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context) : System.Void`  

```csharp
private static System.Void OnWarnOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context);
```

- `private static RestorePause() : System.Void`  

```csharp
private static System.Void RestorePause();
```

- `public static ShowErrorDialog(Game.UI.ErrorDialog e) : System.Void`  

```csharp
public static System.Void ShowErrorDialog(Game.UI.ErrorDialog e);
```

- `public static TryGetFirstError(System.String& error) : System.Boolean`  

```csharp
public static System.Boolean TryGetFirstError(System.String& error);
```


