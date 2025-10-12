# Game.UI.ErrorDialogManager

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static System.Boolean m_Initialized`  
- `private static System.Boolean m_Enabled`  
- `private static System.Collections.Generic.Queue<Game.UI.ErrorDialog> m_ErrorDialogs`  
- `private static System.Single m_SimulationSpeed`  

## Properties

- `public static System.Boolean enabled { get; set }`  
- `public static Game.UI.ErrorDialog currentErrorDialog { get }`  

## Methods

- `public static Clear() : System.Void`  
- `public static DismissAllErrors() : System.Void`  
- `public static DismissCurrentErrorDialog() : System.Void`  
- `public static DisplayDebugErrorDialog() : System.Void`  
- `public static Dispose() : System.Void`  
- `private static GetActions() : Game.UI.ErrorDialog+Actions`  
- `private static GetErrorDetail(System.Exception e, UnityEngine.Object context) : System.String`  
- `private static HandlePause() : System.Void`  
- `public static Initialize() : System.Void`  
- `private static OnException(System.Exception e, UnityEngine.Object context) : System.Void`  
- `private static OnWarnOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context) : System.Void`  
- `private static RestorePause() : System.Void`  
- `public static ShowErrorDialog(Game.UI.ErrorDialog e) : System.Void`  
- `public static TryGetFirstError(System.String& error) : System.Boolean`  

