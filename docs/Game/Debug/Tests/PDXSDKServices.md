# Game.Debug.Tests.TestScenarioPDXSDK+PDXSDKServices

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class PDXSDKServices : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform;
    private System.Boolean m_IsLoggedIn;

    public PDXSDKServices();

    private System.Threading.Tasks.Task AcceptLegalDocuments();
    private System.Threading.Tasks.Task<System.Boolean> Login(System.String username, System.String password);
    private System.Threading.Tasks.Task Logout();
    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
}
```


## Fields

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform;
```

- `private System.Boolean m_IsLoggedIn`  

```csharp
private System.Boolean m_IsLoggedIn;
```


## Constructors

- `public PDXSDKServices()`  

```csharp
public PDXSDKServices();
```


## Methods

- `private AcceptLegalDocuments() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task AcceptLegalDocuments();
```

- `private Login(System.String username, System.String password) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private System.Threading.Tasks.Task<System.Boolean> Login(System.String username, System.String password);
```

- `private Logout() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task Logout();
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```


## Nested types

- `Game.Debug.Tests.TestScenarioPDXSDK+PDXSDKServices+<AcceptLegalDocuments>d__4`  
- `Game.Debug.Tests.TestScenarioPDXSDK+PDXSDKServices+<Login>d__5`  
- `Game.Debug.Tests.TestScenarioPDXSDK+PDXSDKServices+<Logout>d__6`  
- `Game.Debug.Tests.TestScenarioPDXSDK+PDXSDKServices+<OnCleanup>d__3`  
- `Game.Debug.Tests.TestScenarioPDXSDK+PDXSDKServices+<OnPrepare>d__2`  

