# Game.Debug.Tests.TestScenarioAssetDatabase

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class TestScenarioAssetDatabase : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private readonly Game.Debug.Tests.TestAsset+Data testData;
    private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase;
    private static System.Boolean m_GlobalAssetChanged;
    private static System.Boolean m_LocalAssetChanged;
    private static System.Boolean m_TestAssetCallbackInvoked;
    private static Colossal.IO.AssetDatabase.ChangeType m_ChangeType;
    private static const System.String kSettingsFileName;
    private static const System.String kSettingsName;

    public TestScenarioAssetDatabase();

    private System.Threading.Tasks.Task <>n__0();
    private System.Threading.Tasks.Task <>n__1();
    private System.Void OnAssetChangedInGlobal(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    private System.Void OnAssetChangedInLocal(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Void OnTestAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    public System.Void TestAddMetadataAsset();
    public System.Void TestAddTestAsset();
    public System.Void TestAddTestAssetWithData();
    public System.Void TestAssetDeletion();
    public System.Void TestDatabaseRegistrationAffectsAssetAvailability();
    public System.Void TestGetAssetUsingHash128();
    public System.Void TestGetAssetUsingString();
    public System.Void TestMarkForDeletion();
    public System.Void TestOnAssetChangedEvents();
}
```


## Fields

- `private readonly Game.Debug.Tests.TestAsset+Data testData`  

```csharp
private readonly Game.Debug.Tests.TestAsset+Data testData;
```

- `private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase`  

```csharp
private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase;
```

- `private static System.Boolean m_GlobalAssetChanged`  

```csharp
private static System.Boolean m_GlobalAssetChanged;
```

- `private static System.Boolean m_LocalAssetChanged`  

```csharp
private static System.Boolean m_LocalAssetChanged;
```

- `private static System.Boolean m_TestAssetCallbackInvoked`  

```csharp
private static System.Boolean m_TestAssetCallbackInvoked;
```

- `private static Colossal.IO.AssetDatabase.ChangeType m_ChangeType`  

```csharp
private static Colossal.IO.AssetDatabase.ChangeType m_ChangeType;
```

- `private static const System.String kSettingsFileName`  

```csharp
private static const System.String kSettingsFileName;
```

- `private static const System.String kSettingsName`  

```csharp
private static const System.String kSettingsName;
```


## Constructors

- `public TestScenarioAssetDatabase()`  

```csharp
public TestScenarioAssetDatabase();
```


## Methods

- `private <>n__0() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task <>n__0();
```

- `private <>n__1() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task <>n__1();
```

- `private OnAssetChangedInGlobal(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void OnAssetChangedInGlobal(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `private OnAssetChangedInLocal(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void OnAssetChangedInLocal(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `private OnTestAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void OnTestAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `public TestAddMetadataAsset() : System.Void`  

```csharp
public System.Void TestAddMetadataAsset();
```

- `public TestAddTestAsset() : System.Void`  

```csharp
public System.Void TestAddTestAsset();
```

- `public TestAddTestAssetWithData() : System.Void`  

```csharp
public System.Void TestAddTestAssetWithData();
```

- `public TestAssetDeletion() : System.Void`  

```csharp
public System.Void TestAssetDeletion();
```

- `public TestDatabaseRegistrationAffectsAssetAvailability() : System.Void`  

```csharp
public System.Void TestDatabaseRegistrationAffectsAssetAvailability();
```

- `public TestGetAssetUsingHash128() : System.Void`  

```csharp
public System.Void TestGetAssetUsingHash128();
```

- `public TestGetAssetUsingString() : System.Void`  

```csharp
public System.Void TestGetAssetUsingString();
```

- `public TestMarkForDeletion() : System.Void`  

```csharp
public System.Void TestMarkForDeletion();
```

- `public TestOnAssetChangedEvents() : System.Void`  

```csharp
public System.Void TestOnAssetChangedEvents();
```


## Nested types

- `Game.Debug.Tests.TestScenarioAssetDatabase+TestSettings`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<>c`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<>c__DisplayClass10_0`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<>c__DisplayClass9_0`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<OnCleanup>d__7`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<OnPrepare>d__6`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<TestDatabaseRegistrationAffectsAssetAvailability>d__19`  

