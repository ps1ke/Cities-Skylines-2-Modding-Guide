# Game.Debug.Tests.TestScenarioAssetDatabase

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Fields

- `private readonly Game.Debug.Tests.TestAsset+Data testData`  
- `private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase`  
- `private static System.Boolean m_GlobalAssetChanged`  
- `private static System.Boolean m_LocalAssetChanged`  
- `private static System.Boolean m_TestAssetCallbackInvoked`  
- `private static Colossal.IO.AssetDatabase.ChangeType m_ChangeType`  
- `private static const System.String kSettingsFileName`  
- `private static const System.String kSettingsName`  

## Constructors

- `public TestScenarioAssetDatabase()`  

## Methods

- `private <>n__0() : System.Threading.Tasks.Task`  
- `private <>n__1() : System.Threading.Tasks.Task`  
- `private OnAssetChangedInGlobal(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `private OnAssetChangedInLocal(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  
- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  
- `private OnTestAssetChanged(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `public TestAddMetadataAsset() : System.Void`  
- `public TestAddTestAsset() : System.Void`  
- `public TestAddTestAssetWithData() : System.Void`  
- `public TestAssetDeletion() : System.Void`  
- `public TestDatabaseRegistrationAffectsAssetAvailability() : System.Void`  
- `public TestGetAssetUsingHash128() : System.Void`  
- `public TestGetAssetUsingString() : System.Void`  
- `public TestMarkForDeletion() : System.Void`  
- `public TestOnAssetChangedEvents() : System.Void`  

## Nested types

- `Game.Debug.Tests.TestScenarioAssetDatabase+TestSettings`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<>c`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<>c__DisplayClass10_0`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<>c__DisplayClass9_0`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<OnCleanup>d__7`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<OnPrepare>d__6`  
- `Game.Debug.Tests.TestScenarioAssetDatabase+<TestDatabaseRegistrationAffectsAssetAvailability>d__19`  

