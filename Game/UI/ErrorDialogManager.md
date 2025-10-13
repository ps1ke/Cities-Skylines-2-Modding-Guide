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
public static void Clear()
	{
		m_ErrorDialogs.Clear();
		m_SimulationSpeed = 0f;
	}
```

- `public static DismissAllErrors() : System.Void`  

```csharp
public static void DismissAllErrors()
	{
		while (m_ErrorDialogs.Count > 0)
		{
			DismissCurrentErrorDialog();
		}
	}
```

- `public static DismissCurrentErrorDialog() : System.Void`  

```csharp
public static void DismissCurrentErrorDialog()
	{
		if (m_ErrorDialogs.Count > 0)
		{
			m_ErrorDialogs.Dequeue();
		}
		RestorePause();
	}
```

- `public static DisplayDebugErrorDialog() : System.Void`  

```csharp
public static void DisplayDebugErrorDialog()
	{
		ShowErrorDialog(new ErrorDialog
		{
			severity = ErrorDialog.Severity.Error,
			localizedMessage = "Debug Error",
			errorDetails = "Debug details",
			actions = GetActions()
		});
	}
```

- `public static Dispose() : System.Void`  

```csharp
public static void Dispose()
	{
		if (m_Initialized)
		{
			Clear();
			UnityLogger.OnException -= OnException;
			UnityLogger.OnWarnOrHigher -= OnWarnOrHigher;
			m_Initialized = false;
		}
	}
```

- `private static GetActions() : Game.UI.ErrorDialog+Actions`  

```csharp
private static ErrorDialog.Actions GetActions()
	{
		if (GameManager.instance == null)
		{
			return ErrorDialog.Actions.Quit;
		}
		if (Platform.PlayStation.IsPlatformSet(Application.platform))
		{
			if (!GameManager.instance.gameMode.IsGameOrEditor())
			{
				return ErrorDialog.Actions.None;
			}
			return ErrorDialog.Actions.SaveAndContinue;
		}
		if (!GameManager.instance.gameMode.IsGameOrEditor())
		{
			return ErrorDialog.Actions.Quit;
		}
		return ErrorDialog.Actions.Default;
	}
```

- `private static GetErrorDetail(System.Exception e, UnityEngine.Object context) : System.String`  

```csharp
private static string GetErrorDetail(Exception e, UnityEngine.Object context)
	{
		StringBuilder stringBuilder = new StringBuilder();
		if (context != null)
		{
			string text = $"{context.name} ({context.GetType()})";
			string text2 = context.ToString();
			stringBuilder.AppendFormat("With object {0}", text);
			stringBuilder.AppendLine();
			if (text != text2)
			{
				stringBuilder.AppendFormat("Additional info: {0}", text2);
				stringBuilder.AppendLine();
			}
			stringBuilder.AppendLine();
		}
		if (e != null)
		{
			StackTraceHelper.ExtractStackTraceFromException(e, stringBuilder);
			return StackTraceHelper.ExtractStackTrace(3, null, stringBuilder);
		}
		return StackTraceHelper.ExtractStackTrace(3, null, stringBuilder);
	}
```

- `private static HandlePause() : System.Void`  

```csharp
private static void HandlePause()
	{
		SimulationSystem simulationSystem = World.DefaultGameObjectInjectionWorld?.GetExistingSystemManaged<SimulationSystem>();
		if (simulationSystem != null)
		{
			if (m_SimulationSpeed == 0f)
			{
				m_SimulationSpeed = simulationSystem.selectedSpeed;
			}
			simulationSystem.selectedSpeed = 0f;
		}
	}
```

- `public static Initialize() : System.Void`  

```csharp
public static void Initialize()
	{
		if (!m_Initialized)
		{
			UnityLogger.OnException += OnException;
			UnityLogger.OnWarnOrHigher += OnWarnOrHigher;
			m_Initialized = true;
		}
	}
```

- `private static OnException(System.Exception e, UnityEngine.Object context) : System.Void`  

```csharp
private static void OnException(Exception e, UnityEngine.Object context)
	{
		ShowErrorDialog(new ErrorDialog
		{
			severity = ErrorDialog.Severity.Error,
			localizedMessage = LocalizedString.Value(e.Message.Replace("\\", "\\\\")),
			errorDetails = GetErrorDetail(e, context),
			actions = GetActions()
		});
	}
```

- `private static OnWarnOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context) : System.Void`  

```csharp
private static void OnWarnOrHigher(ILog log, Level level, string message, Exception e, UnityEngine.Object context)
	{
		if ((log == null || log.showsErrorsInUI) && level >= Level.Error)
		{
			ShowErrorDialog(new ErrorDialog
			{
				severity = ((!(level == Level.Warn)) ? ErrorDialog.Severity.Error : ErrorDialog.Severity.Warning),
				localizedMessage = LocalizedString.Value(message.Replace("\\", "\\\\")),
				errorDetails = GetErrorDetail(e, context),
				actions = GetActions()
			});
		}
	}
```

- `private static RestorePause() : System.Void`  

```csharp
private static void RestorePause()
	{
		if (m_ErrorDialogs.Count == 0)
		{
			SimulationSystem simulationSystem = World.DefaultGameObjectInjectionWorld?.GetExistingSystemManaged<SimulationSystem>();
			if (simulationSystem != null)
			{
				simulationSystem.selectedSpeed = m_SimulationSpeed;
			}
		}
	}
```

- `public static ShowErrorDialog(Game.UI.ErrorDialog e) : System.Void`  

```csharp
public static void ShowErrorDialog(ErrorDialog e)
	{
		if (m_Enabled)
		{
			HandlePause();
			m_ErrorDialogs.Enqueue(e);
		}
	}
```

- `public static TryGetFirstError(System.String& error) : System.Boolean`  

```csharp
public static bool TryGetFirstError(out string error)
	{
		if (m_ErrorDialogs.Count > 0)
		{
			ErrorDialog errorDialog = m_ErrorDialogs.First();
			error = $"{errorDialog.localizedMessage}\n{errorDialog.errorDetails}";
			return true;
		}
		error = null;
		return false;
	}
```


