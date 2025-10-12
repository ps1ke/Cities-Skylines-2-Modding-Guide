# Colossal.TestFramework.AutomationClientSystem

**Assembly:** `Colossal.TestFramework`  
**Namespace:** `Colossal.TestFramework`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.TestFramework.AutomationClientSystem+DryDockProcess m_DryDockServer`  
- `private Colossal.TestFramework.Category m_CategoryFilter`  
- `private DryDock.Client m_Client`  
- `private System.Boolean m_NeedsConnectivity`  
- `private System.Int32 m_MainMenuLoadCount`  
- `private System.Single m_FirstMainMenuHangTimeRemaining`  
- `private Colossal.TestFramework.AutomationClientSystem+State m_State`  
- `private System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> m_CurrScenario`  
- `private System.Threading.CancellationTokenSource m_Cts`  
- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_IsConnectedTask`  
- `private static Colossal.TestFramework.AutomationClientSystem s_Instance`  
- `internal static Colossal.Logging.ILog log`  
- `private static readonly System.Char[] kCmdSeparators`  
- `private static const System.Single kFirstMainMenuHangTime`  
- `private static const System.String kAutomationPrefix`  
- `private static const System.String kCategoryFilterPrefix`  

## Properties

- `public static Colossal.TestFramework.AutomationClientSystem instance { get }`  
- `public System.Boolean IsConnected { get }`  

## Constructors

- `private AutomationClientSystem(System.String[] cmdLine)`  

## Methods

- `private CheckForConnectivity() : System.Threading.Tasks.Task`  
- `private Configure(System.String[] cmdLine, Colossal.TestFramework.AutomationClientSystem+ServerSettings settings) : System.Boolean`  
- `public static Create(System.String[] cmdLine) : System.Threading.Tasks.Task`  
- `public static Destroy() : System.Void`  
- `private Dispose() : System.Void`  
- `private DryDockCloseConnection() : System.Void`  
- `private DryDockInitializeConnection(Colossal.TestFramework.AutomationClientSystem+ServerSettings settings) : System.Void`  
- `private DryDockOnUpdate() : System.Void`  
- `private LogHandler(DryDock.LogLevel level, System.String message) : System.Void`  
- `private OnDryDockServerShuttingDown() : System.Void`  
- `public OnMainMenuReached() : System.Void`  
- `public OnScreenshotRequest(System.String name) : System.Void`  
- `public OnStatisticValue(System.String key, System.Int64 value) : System.Void`  
- `public OnStatisticValue(System.String key, System.Double value) : System.Void`  
- `public OnTestFailed(System.String name, System.String message) : System.Void`  
- `public OnTestFinished(System.String name) : System.Void`  
- `public OnTestStarted(System.String name) : System.Void`  
- `public OnTestSuiteFailed(System.String name, System.String message) : System.Void`  
- `public OnTestSuiteFinished(System.String name) : System.Void`  
- `public OnTestSuiteStarted(System.String name) : System.Void`  
- `private static ParseCategoryFilter(System.String value) : Colossal.TestFramework.Category`  
- `private static ParseCommandLine(System.Collections.Generic.IEnumerable<System.String> args, Colossal.TestFramework.AutomationClientSystem+ServerSettings settings) : System.Boolean`  
- `private static ParseIPPort(System.String value) : System.ValueTuple<System.Net.IPAddress, System.Int32, System.Boolean>`  
- `public RequestCredentials(Colossal.TestFramework.AutomationClientSystem+BackendService platform) : System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>>`  
- `private SendMessage(DryDock.MessageID messageID, System.Object payload = null) : System.Void`  
- `public SyncResources(System.String resourcePath, System.String resourceGroupName, System.Func<System.String, System.IO.Stream> onAddAsset) : System.Threading.Tasks.Task`  
- `public Update() : System.Void`  

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

