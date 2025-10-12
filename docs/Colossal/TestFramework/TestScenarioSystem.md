# Colossal.TestFramework.TestScenarioSystem

**Assembly:** `Colossal.TestFramework`  
**Namespace:** `Colossal.TestFramework`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> m_Scenarios`  
- `private System.String m_ActiveScenarioName`  
- `private Colossal.TestFramework.TestScenario m_ActiveScenario`  
- `private readonly System.String[] sPreviewBuilds`  
- `private static Colossal.TestFramework.TestScenarioSystem s_Instance`  
- `public static Colossal.Logging.ILog log`  

## Properties

- `public static Colossal.TestFramework.TestScenarioSystem instance { get }`  
- `public System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> scenarios { get }`  
- `public System.Boolean IsRunning { get }`  

## Constructors

- `private TestScenarioSystem()`  

## Methods

- `public static Create(System.String[] cmdLine) : System.Threading.Tasks.Task`  
- `public static Destroy() : System.Void`  
- `private Dispose() : System.Void`  
- `private RegisterScenarios() : System.Void`  
- `public RunScenario(System.String name, System.Threading.CancellationToken cts) : System.Void`  
- `public static SortScenarios(System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> scenarios) : System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario>`  
- `public Update() : System.Void`  

## Nested types

- `Colossal.TestFramework.TestScenarioSystem+Scenario`  
- `Colossal.TestFramework.TestScenarioSystem+<>c`  
- `Colossal.TestFramework.TestScenarioSystem+<Create>d__1`  

