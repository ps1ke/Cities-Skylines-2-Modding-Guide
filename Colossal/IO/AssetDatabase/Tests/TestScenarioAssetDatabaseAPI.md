# Colossal.IO.AssetDatabase.Tests.TestScenarioAssetDatabaseAPI

**Assembly:** `AssetDatabase.TestScenarios`  
**Namespace:** `Colossal.IO.AssetDatabase.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class TestScenarioAssetDatabaseAPI : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    public TestScenarioAssetDatabaseAPI();

    public System.Void TestGetAsset_GlobalUri();
    public System.Void TestGetAsset_GlobalUri_Guid();
    public System.Void TestGetAsset_LocalUri();
    public System.Void TestGetAsset_LocalUri_Guid();
    public System.Void TestGetAsset_LocalUri_Packaged();
    public System.Void TestGetAsset_RelativeUri();
    public System.Void TestGetAsset_Uri();
    private System.Void TestGetAssetFailure<TAssetData, TException>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db);
    private System.Void TestGetAssetFailure<TAssetData>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db);
    private System.Void TestGetAssetFailure<TAssetData>(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetDatabase db);
    private System.Void TestGetAssetSuccess<TAssetData>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db);
    private System.Void TestGetAssetSuccess<TAssetData>(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetDatabase db);
    public System.Void TestTryGetAsset();
}
```


## Constructors

- `public TestScenarioAssetDatabaseAPI()`  

```csharp
public TestScenarioAssetDatabaseAPI();
```


## Methods

- `public TestGetAsset_GlobalUri() : System.Void`  

```csharp
public System.Void TestGetAsset_GlobalUri();
```

- `public TestGetAsset_GlobalUri_Guid() : System.Void`  

```csharp
public System.Void TestGetAsset_GlobalUri_Guid();
```

- `public TestGetAsset_LocalUri() : System.Void`  

```csharp
public System.Void TestGetAsset_LocalUri();
```

- `public TestGetAsset_LocalUri_Guid() : System.Void`  

```csharp
public System.Void TestGetAsset_LocalUri_Guid();
```

- `public TestGetAsset_LocalUri_Packaged() : System.Void`  

```csharp
public System.Void TestGetAsset_LocalUri_Packaged();
```

- `public TestGetAsset_RelativeUri() : System.Void`  

```csharp
public System.Void TestGetAsset_RelativeUri();
```

- `public TestGetAsset_Uri() : System.Void`  

```csharp
public System.Void TestGetAsset_Uri();
```

- `private TestGetAssetFailure<TAssetData, TException>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db) : System.Void`  

```csharp
private System.Void TestGetAssetFailure<TAssetData, TException>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `private TestGetAssetFailure<TAssetData>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db) : System.Void`  

```csharp
private System.Void TestGetAssetFailure<TAssetData>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `private TestGetAssetFailure<TAssetData>(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetDatabase db) : System.Void`  

```csharp
private System.Void TestGetAssetFailure<TAssetData>(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `private TestGetAssetSuccess<TAssetData>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db) : System.Void`  

```csharp
private System.Void TestGetAssetSuccess<TAssetData>(System.String uri, Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `private TestGetAssetSuccess<TAssetData>(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetDatabase db) : System.Void`  

```csharp
private System.Void TestGetAssetSuccess<TAssetData>(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `public TestTryGetAsset() : System.Void`  

```csharp
public System.Void TestTryGetAsset();
```


## Nested types

- `Colossal.IO.AssetDatabase.Tests.TestScenarioAssetDatabaseAPI+<>c__DisplayClass1_0<TAssetData, TException>`  
- `Colossal.IO.AssetDatabase.Tests.TestScenarioAssetDatabaseAPI+<>c__DisplayClass4_0<TAssetData>`  

