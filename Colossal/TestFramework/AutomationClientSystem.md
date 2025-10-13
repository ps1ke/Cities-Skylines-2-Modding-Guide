# Colossal.TestFramework.AutomationClientSystem

**Assembly:** `Colossal.TestFramework`  
**Namespace:** `Colossal.TestFramework`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AutomationClientSystem
{
    private Colossal.TestFramework.AutomationClientSystem+DryDockProcess m_DryDockServer;
    private Colossal.TestFramework.Category m_CategoryFilter;
    private DryDock.Client m_Client;
    private System.Boolean m_NeedsConnectivity;
    private System.Int32 m_MainMenuLoadCount;
    private System.Single m_FirstMainMenuHangTimeRemaining;
    private Colossal.TestFramework.AutomationClientSystem+State m_State;
    private System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> m_CurrScenario;
    private System.Threading.CancellationTokenSource m_Cts;
    private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_IsConnectedTask;
    private static Colossal.TestFramework.AutomationClientSystem s_Instance;
    internal static Colossal.Logging.ILog log;
    private static readonly System.Char[] kCmdSeparators;
    private static const System.Single kFirstMainMenuHangTime;
    private static const System.String kAutomationPrefix;
    private static const System.String kCategoryFilterPrefix;

    public static Colossal.TestFramework.AutomationClientSystem instance { get; }
    public System.Boolean IsConnected { get; }

    private AutomationClientSystem(System.String[] cmdLine);

    private System.Threading.Tasks.Task CheckForConnectivity();
    private System.Boolean Configure(System.String[] cmdLine, Colossal.TestFramework.AutomationClientSystem+ServerSettings settings);
    public static System.Threading.Tasks.Task Create(System.String[] cmdLine);
    public static System.Void Destroy();
    private System.Void Dispose();
    private System.Void DryDockCloseConnection();
    private System.Void DryDockInitializeConnection(Colossal.TestFramework.AutomationClientSystem+ServerSettings settings);
    private System.Void DryDockOnUpdate();
    private System.Void LogHandler(DryDock.LogLevel level, System.String message);
    private System.Void OnDryDockServerShuttingDown();
    public System.Void OnMainMenuReached();
    public System.Void OnScreenshotRequest(System.String name);
    public System.Void OnStatisticValue(System.String key, System.Int64 value);
    public System.Void OnStatisticValue(System.String key, System.Double value);
    public System.Void OnTestFailed(System.String name, System.String message);
    public System.Void OnTestFinished(System.String name);
    public System.Void OnTestStarted(System.String name);
    public System.Void OnTestSuiteFailed(System.String name, System.String message);
    public System.Void OnTestSuiteFinished(System.String name);
    public System.Void OnTestSuiteStarted(System.String name);
    private static Colossal.TestFramework.Category ParseCategoryFilter(System.String value);
    private static System.Boolean ParseCommandLine(System.Collections.Generic.IEnumerable<System.String> args, Colossal.TestFramework.AutomationClientSystem+ServerSettings settings);
    private static System.ValueTuple<System.Net.IPAddress, System.Int32, System.Boolean> ParseIPPort(System.String value);
    public System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>> RequestCredentials(Colossal.TestFramework.AutomationClientSystem+BackendService platform);
    private System.Void SendMessage(DryDock.MessageID messageID, System.Object payload);
    public System.Threading.Tasks.Task SyncResources(System.String resourcePath, System.String resourceGroupName, System.Func<System.String, System.IO.Stream> onAddAsset);
    public System.Void Update();
}
```


## Fields

- `private Colossal.TestFramework.AutomationClientSystem+DryDockProcess m_DryDockServer`  

```csharp
private Colossal.TestFramework.AutomationClientSystem+DryDockProcess m_DryDockServer;
```

- `private Colossal.TestFramework.Category m_CategoryFilter`  

```csharp
private Colossal.TestFramework.Category m_CategoryFilter;
```

- `private DryDock.Client m_Client`  

```csharp
private DryDock.Client m_Client;
```

- `private System.Boolean m_NeedsConnectivity`  

```csharp
private System.Boolean m_NeedsConnectivity;
```

- `private System.Int32 m_MainMenuLoadCount`  

```csharp
private System.Int32 m_MainMenuLoadCount;
```

- `private System.Single m_FirstMainMenuHangTimeRemaining`  

```csharp
private System.Single m_FirstMainMenuHangTimeRemaining;
```

- `private Colossal.TestFramework.AutomationClientSystem+State m_State`  

```csharp
private Colossal.TestFramework.AutomationClientSystem+State m_State;
```

- `private System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> m_CurrScenario`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> m_CurrScenario;
```

- `private System.Threading.CancellationTokenSource m_Cts`  

```csharp
private System.Threading.CancellationTokenSource m_Cts;
```

- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_IsConnectedTask`  

```csharp
private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_IsConnectedTask;
```

- `private static Colossal.TestFramework.AutomationClientSystem s_Instance`  

```csharp
private static Colossal.TestFramework.AutomationClientSystem s_Instance;
```

- `internal static Colossal.Logging.ILog log`  

```csharp
internal static Colossal.Logging.ILog log;
```

- `private static readonly System.Char[] kCmdSeparators`  

```csharp
private static readonly System.Char[] kCmdSeparators;
```

- `private static const System.Single kFirstMainMenuHangTime`  

```csharp
private static const System.Single kFirstMainMenuHangTime;
```

- `private static const System.String kAutomationPrefix`  

```csharp
private static const System.String kAutomationPrefix;
```

- `private static const System.String kCategoryFilterPrefix`  

```csharp
private static const System.String kCategoryFilterPrefix;
```


## Properties

- `public static Colossal.TestFramework.AutomationClientSystem instance { get }`  

```csharp
public static Colossal.TestFramework.AutomationClientSystem instance { get; }
```

- `public System.Boolean IsConnected { get }`  

```csharp
public System.Boolean IsConnected { get; }
```


## Constructors

- `private AutomationClientSystem(System.String[] cmdLine)`  

```csharp
private AutomationClientSystem(System.String[] cmdLine);
```


## Methods

- `private CheckForConnectivity() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task CheckForConnectivity();
```

- `private Configure(System.String[] cmdLine, Colossal.TestFramework.AutomationClientSystem+ServerSettings settings) : System.Boolean`  

```csharp
private System.Boolean Configure(System.String[] cmdLine, Colossal.TestFramework.AutomationClientSystem+ServerSettings settings);
```

- `public static Create(System.String[] cmdLine) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task Create(System.String[] cmdLine);
```

- `public static Destroy() : System.Void`  

```csharp
public static System.Void Destroy();
```

- `private Dispose() : System.Void`  

```csharp
private System.Void Dispose();
```

- `private DryDockCloseConnection() : System.Void`  

```csharp
private System.Void DryDockCloseConnection();
```

- `private DryDockInitializeConnection(Colossal.TestFramework.AutomationClientSystem+ServerSettings settings) : System.Void`  

```csharp
private System.Void DryDockInitializeConnection(Colossal.TestFramework.AutomationClientSystem+ServerSettings settings);
```

- `private DryDockOnUpdate() : System.Void`  

```csharp
private System.Void DryDockOnUpdate();
```

- `private LogHandler(DryDock.LogLevel level, System.String message) : System.Void`  

```csharp
private System.Void LogHandler(DryDock.LogLevel level, System.String message);
```

- `private OnDryDockServerShuttingDown() : System.Void`  

```csharp
private System.Void OnDryDockServerShuttingDown();
```

- `public OnMainMenuReached() : System.Void`  

```csharp
public System.Void OnMainMenuReached();
```

- `public OnScreenshotRequest(System.String name) : System.Void`  

```csharp
public System.Void OnScreenshotRequest(System.String name);
```

- `public OnStatisticValue(System.String key, System.Int64 value) : System.Void`  

```csharp
public System.Void OnStatisticValue(System.String key, System.Int64 value);
```

- `public OnStatisticValue(System.String key, System.Double value) : System.Void`  

```csharp
public System.Void OnStatisticValue(System.String key, System.Double value);
```

- `public OnTestFailed(System.String name, System.String message) : System.Void`  

```csharp
public System.Void OnTestFailed(System.String name, System.String message);
```

- `public OnTestFinished(System.String name) : System.Void`  

```csharp
public System.Void OnTestFinished(System.String name);
```

- `public OnTestStarted(System.String name) : System.Void`  

```csharp
public System.Void OnTestStarted(System.String name);
```

- `public OnTestSuiteFailed(System.String name, System.String message) : System.Void`  

```csharp
public System.Void OnTestSuiteFailed(System.String name, System.String message);
```

- `public OnTestSuiteFinished(System.String name) : System.Void`  

```csharp
public System.Void OnTestSuiteFinished(System.String name);
```

- `public OnTestSuiteStarted(System.String name) : System.Void`  

```csharp
public System.Void OnTestSuiteStarted(System.String name);
```

- `private static ParseCategoryFilter(System.String value) : Colossal.TestFramework.Category`  

```csharp
private static Colossal.TestFramework.Category ParseCategoryFilter(System.String value);
```

- `private static ParseCommandLine(System.Collections.Generic.IEnumerable<System.String> args, Colossal.TestFramework.AutomationClientSystem+ServerSettings settings) : System.Boolean`  

```csharp
private static System.Boolean ParseCommandLine(System.Collections.Generic.IEnumerable<System.String> args, Colossal.TestFramework.AutomationClientSystem+ServerSettings settings);
```

- `private static ParseIPPort(System.String value) : System.ValueTuple<System.Net.IPAddress, System.Int32, System.Boolean>`  

```csharp
private static System.ValueTuple<System.Net.IPAddress, System.Int32, System.Boolean> ParseIPPort(System.String value);
```

- `public RequestCredentials(Colossal.TestFramework.AutomationClientSystem+BackendService platform) : System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>> RequestCredentials(Colossal.TestFramework.AutomationClientSystem+BackendService platform);
```

- `private SendMessage(DryDock.MessageID messageID, System.Object payload = null) : System.Void`  

```csharp
private System.Void SendMessage(DryDock.MessageID messageID, System.Object payload);
```

- `public SyncResources(System.String resourcePath, System.String resourceGroupName, System.Func<System.String, System.IO.Stream> onAddAsset) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SyncResources(System.String resourcePath, System.String resourceGroupName, System.Func<System.String, System.IO.Stream> onAddAsset);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


## Nested types

- `Colossal.TestFramework.AutomationClientSystem+ServerSettings`  
- `Colossal.TestFramework.AutomationClientSystem+DryDockProcess`  
- `Colossal.TestFramework.AutomationClientSystem+State`  
- `Colossal.TestFramework.AutomationClientSystem+BackendService`  
- `Colossal.TestFramework.AutomationClientSystem+<>c__DisplayClass29_0`  
- `Colossal.TestFramework.AutomationClientSystem+<>c__DisplayClass29_1`  
- `Colossal.TestFramework.AutomationClientSystem+<>c__DisplayClass50_0`  
- `Colossal.TestFramework.AutomationClientSystem+<>c__DisplayClass51_0`  
- `Colossal.TestFramework.AutomationClientSystem+<DryDockInitializeConnection>d__32`  
- `Colossal.TestFramework.AutomationClientSystem+<RequestCredentials>d__50`  
- `Colossal.TestFramework.AutomationClientSystem+<SyncResources>d__51`  

