# Colossal.TestFramework.TestScenario

**Assembly:** `Colossal.TestFramework`  
**Namespace:** `Colossal.TestFramework`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.TestFramework.ITestStep`  

## Code

```csharp
public abstract class TestScenario : Colossal.TestFramework.ITestStep
{
    private System.Int32 m_ScenarioExceptionCount;
    private System.Int32 m_ScenarioErrorCount;
    protected System.Collections.Generic.List<System.String> m_ExceptionsDetected;
    protected System.Collections.Generic.List<System.String> m_ErrorsDetected;
    private System.Exception <Exception>k__BackingField;
    private System.Boolean <IgnoreLogForTestResult>k__BackingField;
    private System.Boolean <IsFinished>k__BackingField;
    private System.Boolean <disabled>k__BackingField;
    private readonly System.String m_Description;
    private static Colossal.Logging.ILog <log>k__BackingField;

    public System.Int32 exceptionCount { get; }
    public System.Int32 errorCount { get; }
    protected static Colossal.Logging.ILog log { protected get; private set; }
    public System.Exception Exception { get; protected set; }
    public System.Boolean IgnoreLogForTestResult { get; set; }
    public System.Boolean IsFinished { get; private set; }
    public Unity.Entities.World World { get; }
    public System.Boolean disabled { get; set; }

    public TestScenario();

    private System.Void CheckForErrorsAtStart();
    private System.Threading.Tasks.Task CleanupAndDismissErrors();
    private System.Void CleanupScenarioData();
    private System.Void CleanupTestScenario();
    private System.Void CollectTestMethods(System.Reflection.MethodInfo& testPrepareMethod, System.Collections.Generic.IEnumerable`1[[System.Reflection.MethodInfo, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& testMethods, System.Reflection.MethodInfo& testCleanupMethod);
    protected System.Void HandleException(System.Exception e);
    private System.Void InitializeTestScenario();
    private System.Void LogAfterTestMetrics();
    protected virtual System.Threading.Tasks.Task OnCleanup();
    private System.Void OnErrorOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context);
    private System.Void OnException(System.Exception e, UnityEngine.Object context);
    protected virtual System.Threading.Tasks.Task OnPrepare();
    public System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>> RequestCredentials(Colossal.TestFramework.AutomationClientSystem+BackendService platform);
    public System.Threading.Tasks.Task Run(System.Threading.CancellationToken cts);
    protected virtual System.Threading.Tasks.Task RunTestMethods(System.Threading.CancellationToken cts);
    public System.Void SendScreenshotRequest(System.String name);
    public System.Void SendStatisticValue(System.String key, System.Int64 value);
    public System.Void SendStatisticValue(System.String key, System.Double value);
    public System.Threading.Tasks.Task SyncResources(System.String resourcePath, System.String resourceGroupName, System.Func<System.String, System.IO.Stream> onAddAsset);
    private System.Void TestStepHitException(System.Exception e);
    public virtual System.String ToString();
    protected System.Threading.Tasks.Task WaitFrames(System.Int32 frameCount);
}
```


## Fields

- `private System.Int32 m_ScenarioExceptionCount`  

```csharp
private System.Int32 m_ScenarioExceptionCount;
```

- `private System.Int32 m_ScenarioErrorCount`  

```csharp
private System.Int32 m_ScenarioErrorCount;
```

- `protected System.Collections.Generic.List<System.String> m_ExceptionsDetected`  

```csharp
protected System.Collections.Generic.List<System.String> m_ExceptionsDetected;
```

- `protected System.Collections.Generic.List<System.String> m_ErrorsDetected`  

```csharp
protected System.Collections.Generic.List<System.String> m_ErrorsDetected;
```

- `private System.Exception <Exception>k__BackingField`  

```csharp
private System.Exception <Exception>k__BackingField;
```

- `private System.Boolean <IgnoreLogForTestResult>k__BackingField`  

```csharp
private System.Boolean <IgnoreLogForTestResult>k__BackingField;
```

- `private System.Boolean <IsFinished>k__BackingField`  

```csharp
private System.Boolean <IsFinished>k__BackingField;
```

- `private System.Boolean <disabled>k__BackingField`  

```csharp
private System.Boolean <disabled>k__BackingField;
```

- `private readonly System.String m_Description`  

```csharp
private readonly System.String m_Description;
```

- `private static Colossal.Logging.ILog <log>k__BackingField`  

```csharp
private static Colossal.Logging.ILog <log>k__BackingField;
```


## Properties

- `public System.Int32 exceptionCount { get }`  

```csharp
public System.Int32 exceptionCount { get; }
```

- `public System.Int32 errorCount { get }`  

```csharp
public System.Int32 errorCount { get; }
```

- `protected static Colossal.Logging.ILog log { protected get; private set }`  

```csharp
protected static Colossal.Logging.ILog log { protected get; private set; }
```

- `public System.Exception Exception { get; protected set }`  

```csharp
public System.Exception Exception { get; protected set; }
```

- `public System.Boolean IgnoreLogForTestResult { get; set }`  

```csharp
public System.Boolean IgnoreLogForTestResult { get; set; }
```

- `public System.Boolean IsFinished { get; private set }`  

```csharp
public System.Boolean IsFinished { get; private set; }
```

- `public Unity.Entities.World World { get }`  

```csharp
public Unity.Entities.World World { get; }
```

- `public System.Boolean disabled { get; set }`  

```csharp
public System.Boolean disabled { get; set; }
```


## Constructors

- `public TestScenario()`  

```csharp
public TestScenario();
```


## Methods

- `private CheckForErrorsAtStart() : System.Void`  

```csharp
private System.Void CheckForErrorsAtStart();
```

- `private CleanupAndDismissErrors() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task CleanupAndDismissErrors();
```

- `private CleanupScenarioData() : System.Void`  

```csharp
private System.Void CleanupScenarioData();
```

- `private CleanupTestScenario() : System.Void`  

```csharp
private System.Void CleanupTestScenario();
```

- `private CollectTestMethods(System.Reflection.MethodInfo& testPrepareMethod, System.Collections.Generic.IEnumerable`1[[System.Reflection.MethodInfo, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& testMethods, System.Reflection.MethodInfo& testCleanupMethod) : System.Void`  

```csharp
private System.Void CollectTestMethods(System.Reflection.MethodInfo& testPrepareMethod, System.Collections.Generic.IEnumerable`1[[System.Reflection.MethodInfo, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& testMethods, System.Reflection.MethodInfo& testCleanupMethod);
```

- `protected HandleException(System.Exception e) : System.Void`  

```csharp
protected System.Void HandleException(System.Exception e);
```

- `private InitializeTestScenario() : System.Void`  

```csharp
private System.Void InitializeTestScenario();
```

- `private LogAfterTestMetrics() : System.Void`  

```csharp
private System.Void LogAfterTestMetrics();
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `private OnErrorOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context) : System.Void`  

```csharp
private System.Void OnErrorOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context);
```

- `private OnException(System.Exception e, UnityEngine.Object context) : System.Void`  

```csharp
private System.Void OnException(System.Exception e, UnityEngine.Object context);
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `public RequestCredentials(Colossal.TestFramework.AutomationClientSystem+BackendService platform) : System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>>`  

```csharp
public System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>> RequestCredentials(Colossal.TestFramework.AutomationClientSystem+BackendService platform);
```

- `public Run(System.Threading.CancellationToken cts) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Run(System.Threading.CancellationToken cts);
```

- `protected virtual RunTestMethods(System.Threading.CancellationToken cts) : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task RunTestMethods(System.Threading.CancellationToken cts);
```

- `public SendScreenshotRequest(System.String name) : System.Void`  

```csharp
public System.Void SendScreenshotRequest(System.String name);
```

- `public SendStatisticValue(System.String key, System.Int64 value) : System.Void`  

```csharp
public System.Void SendStatisticValue(System.String key, System.Int64 value);
```

- `public SendStatisticValue(System.String key, System.Double value) : System.Void`  

```csharp
public System.Void SendStatisticValue(System.String key, System.Double value);
```

- `public SyncResources(System.String resourcePath, System.String resourceGroupName, System.Func<System.String, System.IO.Stream> onAddAsset) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SyncResources(System.String resourcePath, System.String resourceGroupName, System.Func<System.String, System.IO.Stream> onAddAsset);
```

- `private TestStepHitException(System.Exception e) : System.Void`  

```csharp
private System.Void TestStepHitException(System.Exception e);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `protected WaitFrames(System.Int32 frameCount = 30) : System.Threading.Tasks.Task`  

```csharp
protected System.Threading.Tasks.Task WaitFrames(System.Int32 frameCount);
```


## Nested types

- `Colossal.TestFramework.TestScenario+TestScenarioException`  
- `Colossal.TestFramework.TestScenario+<CleanupAndDismissErrors>d__46`  
- `Colossal.TestFramework.TestScenario+<RequestCredentials>d__53`  
- `Colossal.TestFramework.TestScenario+<Run>d__36`  
- `Colossal.TestFramework.TestScenario+<RunTestMethods>d__40`  
- `Colossal.TestFramework.TestScenario+<WaitFrames>d__47`  

