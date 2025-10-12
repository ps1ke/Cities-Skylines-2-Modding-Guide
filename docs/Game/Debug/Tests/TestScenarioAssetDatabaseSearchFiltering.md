# Game.Debug.Tests.TestScenarioAssetDatabaseSearchFiltering

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Fields

- `private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase`  
- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_AddedAssets`  

## Constructors

- `public TestScenarioAssetDatabaseSearchFiltering()`  

## Methods

- `private <>n__0() : System.Threading.Tasks.Task`  
- `private <>n__1() : System.Threading.Tasks.Task`  
- `private <TestTryGetAssetWithGuidSearchFilterReturnsFirstMatch>b__11_0(Colossal.IO.AssetDatabase.AssetData asset) : System.Boolean`  
- `private AssertAssetListItem(System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> filteredAssets, System.Int32 index) : System.Void`  
- `private BuildTransientDatabase() : System.Void`  
- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  
- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  
- `public TestCombinationFiltering() : System.Void`  
- `public TestConditionalFiltering() : System.Void`  
- `public TestFilteringByTypeReturnsTypedAssets() : System.Void`  
- `public TestGuidFiltering() : System.Void`  
- `public TestNoAssetFilteringReturnsAllAssets() : System.Void`  
- `public TestStringFiltering() : System.Void`  
- `public TestSubclassFiltering() : System.Void`  
- `public TestTryGetAssetWithGuidSearchFilterReturnsFirstMatch() : System.Void`  
- `public TestTypeCastFilteringReturnsTypedAssets() : System.Void`  

## Nested types

- `Game.Debug.Tests.TestScenarioAssetDatabaseSearchFiltering+<>c`  
- `Game.Debug.Tests.TestScenarioAssetDatabaseSearchFiltering+<OnCleanup>d__3`  
- `Game.Debug.Tests.TestScenarioAssetDatabaseSearchFiltering+<OnPrepare>d__2`  

