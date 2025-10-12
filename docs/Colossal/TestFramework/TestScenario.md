# Colossal.TestFramework.TestScenario

**Assembly:** `Colossal.TestFramework`  
**Namespace:** `Colossal.TestFramework`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.TestFramework.ITestStep`  

## Fields

- `private System.Int32 m_ScenarioExceptionCount`  
- `private System.Int32 m_ScenarioErrorCount`  
- `protected System.Collections.Generic.List<System.String> m_ExceptionsDetected`  
- `protected System.Collections.Generic.List<System.String> m_ErrorsDetected`  
- `private System.Exception <Exception>k__BackingField`  
- `private System.Boolean <IgnoreLogForTestResult>k__BackingField`  
- `private System.Boolean <IsFinished>k__BackingField`  
- `private System.Boolean <disabled>k__BackingField`  
- `private readonly System.String m_Description`  
- `private static Colossal.Logging.ILog <log>k__BackingField`  

## Properties

- `public System.Int32 exceptionCount { get }`  
- `public System.Int32 errorCount { get }`  
- `protected static Colossal.Logging.ILog log { protected get; private set }`  
- `public System.Exception Exception { get; protected set }`  
- `public System.Boolean IgnoreLogForTestResult { get; set }`  
- `public System.Boolean IsFinished { get; private set }`  
- `public Unity.Entities.World World { get }`  
- `public System.Boolean disabled { get; set }`  

## Constructors

- `public TestScenario()`  

## Methods

- `private CheckForErrorsAtStart() : System.Void`  
- `private CleanupAndDismissErrors() : System.Threading.Tasks.Task`  
- `private CleanupScenarioData() : System.Void`  
- `private CleanupTestScenario() : System.Void`  
- `private CollectTestMethods(System.Reflection.MethodInfo& testPrepareMethod, System.Collections.Generic.IEnumerable`1[[System.Reflection.MethodInfo, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& testMethods, System.Reflection.MethodInfo& testCleanupMethod) : System.Void`  
- `protected HandleException(System.Exception e) : System.Void`  
- `private InitializeTestScenario() : System.Void`  
- `private LogAfterTestMetrics() : System.Void`  
- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  
- `private OnErrorOrHigher(Colossal.Logging.ILog log, Colossal.Logging.Level level, System.String message, System.Exception e, UnityEngine.Object context) : System.Void`  
- `private OnException(System.Exception e, UnityEngine.Object context) : System.Void`  
- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  
- `public RequestCredentials(Colossal.TestFramework.AutomationClientSystem+BackendService platform) : System.Threading.Tasks.Task<System.ValueTuple<System.String, System.String>>`  
- `public Run(System.Threading.CancellationToken cts) : System.Threading.Tasks.Task`  
- `protected virtual RunTestMethods(System.Threading.CancellationToken cts) : System.Threading.Tasks.Task`  
- `public SendScreenshotRequest(System.String name) : System.Void`  
- `public SendStatisticValue(System.String key, System.Int64 value) : System.Void`  
- `public SendStatisticValue(System.String key, System.Double value) : System.Void`  
- `public SyncResources(System.String resourcePath, System.String resourceGroupName, System.Func<System.String, System.IO.Stream> onAddAsset) : System.Threading.Tasks.Task`  
- `private TestStepHitException(System.Exception e) : System.Void`  
- `public virtual ToString() : System.String`  
- `protected WaitFrames(System.Int32 frameCount = 30) : System.Threading.Tasks.Task`  

## Nested types

- `Colossal.TestFramework.TestScenario+TestScenarioException`  
- `Colossal.TestFramework.TestScenario+<CleanupAndDismissErrors>d__46`  
- `Colossal.TestFramework.TestScenario+<RequestCredentials>d__53`  
- `Colossal.TestFramework.TestScenario+<Run>d__36`  
- `Colossal.TestFramework.TestScenario+<RunTestMethods>d__40`  
- `Colossal.TestFramework.TestScenario+<WaitFrames>d__47`  

