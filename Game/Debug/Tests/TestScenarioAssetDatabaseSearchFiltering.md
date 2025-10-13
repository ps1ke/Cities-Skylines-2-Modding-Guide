# Game.Debug.Tests.TestScenarioAssetDatabaseSearchFiltering

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class TestScenarioAssetDatabaseSearchFiltering : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase;
    private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_AddedAssets;

    public TestScenarioAssetDatabaseSearchFiltering();

    private System.Threading.Tasks.Task <>n__0();
    private System.Threading.Tasks.Task <>n__1();
    private System.Boolean <TestTryGetAssetWithGuidSearchFilterReturnsFirstMatch>b__11_0(Colossal.IO.AssetDatabase.AssetData asset);
    private System.Void AssertAssetListItem(System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> filteredAssets, System.Int32 index);
    private System.Void BuildTransientDatabase();
    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
    public System.Void TestCombinationFiltering();
    public System.Void TestConditionalFiltering();
    public System.Void TestFilteringByTypeReturnsTypedAssets();
    public System.Void TestGuidFiltering();
    public System.Void TestNoAssetFilteringReturnsAllAssets();
    public System.Void TestStringFiltering();
    public System.Void TestSubclassFiltering();
    public System.Void TestTryGetAssetWithGuidSearchFilterReturnsFirstMatch();
    public System.Void TestTypeCastFilteringReturnsTypedAssets();
}
```


## Fields

- `private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase`  

```csharp
private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_TransientDatabase;
```

- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_AddedAssets`  

```csharp
private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> m_AddedAssets;
```


## Constructors

- `public TestScenarioAssetDatabaseSearchFiltering()`  

```csharp
public TestScenarioAssetDatabaseSearchFiltering();
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

- `private <TestTryGetAssetWithGuidSearchFilterReturnsFirstMatch>b__11_0(Colossal.IO.AssetDatabase.AssetData asset) : System.Boolean`  

```csharp
private System.Boolean <TestTryGetAssetWithGuidSearchFilterReturnsFirstMatch>b__11_0(Colossal.IO.AssetDatabase.AssetData asset);
```

- `private AssertAssetListItem(System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> filteredAssets, System.Int32 index) : System.Void`  

```csharp
private System.Void AssertAssetListItem(System.Collections.Generic.List<Colossal.IO.AssetDatabase.AssetData> filteredAssets, System.Int32 index);
```

- `private BuildTransientDatabase() : System.Void`  

```csharp
private System.Void BuildTransientDatabase();
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `public TestCombinationFiltering() : System.Void`  

```csharp
public System.Void TestCombinationFiltering();
```

- `public TestConditionalFiltering() : System.Void`  

```csharp
public System.Void TestConditionalFiltering();
```

- `public TestFilteringByTypeReturnsTypedAssets() : System.Void`  

```csharp
public System.Void TestFilteringByTypeReturnsTypedAssets();
```

- `public TestGuidFiltering() : System.Void`  

```csharp
public System.Void TestGuidFiltering();
```

- `public TestNoAssetFilteringReturnsAllAssets() : System.Void`  

```csharp
public System.Void TestNoAssetFilteringReturnsAllAssets();
```

- `public TestStringFiltering() : System.Void`  

```csharp
public System.Void TestStringFiltering();
```

- `public TestSubclassFiltering() : System.Void`  

```csharp
public System.Void TestSubclassFiltering();
```

- `public TestTryGetAssetWithGuidSearchFilterReturnsFirstMatch() : System.Void`  

```csharp
public System.Void TestTryGetAssetWithGuidSearchFilterReturnsFirstMatch();
```

- `public TestTypeCastFilteringReturnsTypedAssets() : System.Void`  

```csharp
public System.Void TestTypeCastFilteringReturnsTypedAssets();
```


## Nested types

- `Game.Debug.Tests.TestScenarioAssetDatabaseSearchFiltering+<>c`  
- `Game.Debug.Tests.TestScenarioAssetDatabaseSearchFiltering+<OnCleanup>d__3`  
- `Game.Debug.Tests.TestScenarioAssetDatabaseSearchFiltering+<OnPrepare>d__2`  

