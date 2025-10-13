# Colossal.TestFramework.TestScenarioSystem

**Assembly:** `Colossal.TestFramework`  
**Namespace:** `Colossal.TestFramework`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class TestScenarioSystem
{
    private System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> m_Scenarios;
    private System.String m_ActiveScenarioName;
    private Colossal.TestFramework.TestScenario m_ActiveScenario;
    private readonly System.String[] sPreviewBuilds;
    private static Colossal.TestFramework.TestScenarioSystem s_Instance;
    public static Colossal.Logging.ILog log;

    public static Colossal.TestFramework.TestScenarioSystem instance { get; }
    public System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> scenarios { get; }
    public System.Boolean IsRunning { get; }

    private TestScenarioSystem();

    public static System.Threading.Tasks.Task Create(System.String[] cmdLine);
    public static System.Void Destroy();
    private System.Void Dispose();
    private System.Void RegisterScenarios();
    public System.Void RunScenario(System.String name, System.Threading.CancellationToken cts);
    public static System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> SortScenarios(System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> scenarios);
    public System.Void Update();
}
```


## Fields

- `private System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> m_Scenarios`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> m_Scenarios;
```

- `private System.String m_ActiveScenarioName`  

```csharp
private System.String m_ActiveScenarioName;
```

- `private Colossal.TestFramework.TestScenario m_ActiveScenario`  

```csharp
private Colossal.TestFramework.TestScenario m_ActiveScenario;
```

- `private readonly System.String[] sPreviewBuilds`  

```csharp
private readonly System.String[] sPreviewBuilds;
```

- `private static Colossal.TestFramework.TestScenarioSystem s_Instance`  

```csharp
private static Colossal.TestFramework.TestScenarioSystem s_Instance;
```

- `public static Colossal.Logging.ILog log`  

```csharp
public static Colossal.Logging.ILog log;
```


## Properties

- `public static Colossal.TestFramework.TestScenarioSystem instance { get }`  

```csharp
public static Colossal.TestFramework.TestScenarioSystem instance { get; }
```

- `public System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> scenarios { get }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> scenarios { get; }
```

- `public System.Boolean IsRunning { get }`  

```csharp
public System.Boolean IsRunning { get; }
```


## Constructors

- `private TestScenarioSystem()`  

```csharp
private TestScenarioSystem();
```


## Methods

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

- `private RegisterScenarios() : System.Void`  

```csharp
private System.Void RegisterScenarios();
```

- `public RunScenario(System.String name, System.Threading.CancellationToken cts) : System.Void`  

```csharp
public System.Void RunScenario(System.String name, System.Threading.CancellationToken cts);
```

- `public static SortScenarios(System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> scenarios) : System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> SortScenarios(System.Collections.Generic.Dictionary<System.String, Colossal.TestFramework.TestScenarioSystem+Scenario> scenarios);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


## Nested types

- `Colossal.TestFramework.TestScenarioSystem+Scenario`  
- `Colossal.TestFramework.TestScenarioSystem+<>c`  
- `Colossal.TestFramework.TestScenarioSystem+<Create>d__1`  

