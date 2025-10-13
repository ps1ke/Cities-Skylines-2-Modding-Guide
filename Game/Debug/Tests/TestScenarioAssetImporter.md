# Game.Debug.Tests.TestScenarioAssetImporter

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class TestScenarioAssetImporter : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    protected static const System.String kTestResources;
    protected static const System.String kResourcesGroupName;
    protected static const System.String kTestAssetPath;

    public TestScenarioAssetImporter();

    private System.Threading.Tasks.Task <>n__0();
    private System.Threading.Tasks.Task <>n__1();
    private static System.Void CheckAssetDataEquality(Colossal.IO.AssetDatabase.SurfaceAsset asset);
    private static System.Void CheckAssetDataEquality(Colossal.IO.AssetDatabase.AssetData asset);
    private static System.Int64 CompareStreams(System.IO.Stream stream1, System.IO.Stream stream2);
    public System.Threading.Tasks.Task EU_TestResidentialLowSignature03();
    public System.Threading.Tasks.Task EU_TestResidentialMedium01_L1_2x2();
    public System.Threading.Tasks.Task EU_TestResidentialMedium01_L3_2x2();
    public System.Threading.Tasks.Task EU_TestTrafficLightCar01();
    private System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory> ImportAsset(System.String assetName);
    protected System.IO.Stream OnAddAsset(System.String path);
    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
    public System.Threading.Tasks.Task TestAppleTree01();
    public System.Threading.Tasks.Task TestAutomatedParkingBuilding01();
    public System.Threading.Tasks.Task TestBirchTree();
    public System.Threading.Tasks.Task TestCar01();
    public System.Threading.Tasks.Task TestFerrisWheel01();
    public System.Threading.Tasks.Task TestGasBottle01();
    public System.Threading.Tasks.Task TestInternationalAirport01();
    public System.Threading.Tasks.Task TestParkingHall01();
    public System.Threading.Tasks.Task TestRoadMaintenanceVehicle01();
    private static System.Void ValidateData(System.Collections.Generic.IReadOnlyList<Game.Prefabs.PrefabBase> prefabBases);
    private static System.Void ValidatePrefabBase(Game.Prefabs.PrefabBase prefabBase, System.String name, System.String guid, System.Int32 indexCount, System.Int32 vertexCount, System.Int32 meshCount, System.Boolean hasGeometryAsset, System.Boolean isImpostor);
}
```


## Fields

- `protected static const System.String kTestResources`  

```csharp
protected static const System.String kTestResources;
```

- `protected static const System.String kResourcesGroupName`  

```csharp
protected static const System.String kResourcesGroupName;
```

- `protected static const System.String kTestAssetPath`  

```csharp
protected static const System.String kTestAssetPath;
```


## Constructors

- `public TestScenarioAssetImporter()`  

```csharp
public TestScenarioAssetImporter();
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

- `private static CheckAssetDataEquality(Colossal.IO.AssetDatabase.SurfaceAsset asset) : System.Void`  

```csharp
private static System.Void CheckAssetDataEquality(Colossal.IO.AssetDatabase.SurfaceAsset asset);
```

- `private static CheckAssetDataEquality(Colossal.IO.AssetDatabase.AssetData asset) : System.Void`  

```csharp
private static System.Void CheckAssetDataEquality(Colossal.IO.AssetDatabase.AssetData asset);
```

- `private static CompareStreams(System.IO.Stream stream1, System.IO.Stream stream2) : System.Int64`  

```csharp
private static System.Int64 CompareStreams(System.IO.Stream stream1, System.IO.Stream stream2);
```

- `public EU_TestResidentialLowSignature03() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task EU_TestResidentialLowSignature03();
```

- `public EU_TestResidentialMedium01_L1_2x2() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task EU_TestResidentialMedium01_L1_2x2();
```

- `public EU_TestResidentialMedium01_L3_2x2() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task EU_TestResidentialMedium01_L3_2x2();
```

- `public EU_TestTrafficLightCar01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task EU_TestTrafficLightCar01();
```

- `private ImportAsset(System.String assetName) : System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory>`  

```csharp
private System.Threading.Tasks.Task<Game.UI.Editor.AssetImportPanel+PrefabFactory> ImportAsset(System.String assetName);
```

- `protected OnAddAsset(System.String path) : System.IO.Stream`  

```csharp
protected System.IO.Stream OnAddAsset(System.String path);
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `public TestAppleTree01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestAppleTree01();
```

- `public TestAutomatedParkingBuilding01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestAutomatedParkingBuilding01();
```

- `public TestBirchTree() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestBirchTree();
```

- `public TestCar01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestCar01();
```

- `public TestFerrisWheel01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestFerrisWheel01();
```

- `public TestGasBottle01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestGasBottle01();
```

- `public TestInternationalAirport01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestInternationalAirport01();
```

- `public TestParkingHall01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestParkingHall01();
```

- `public TestRoadMaintenanceVehicle01() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task TestRoadMaintenanceVehicle01();
```

- `private static ValidateData(System.Collections.Generic.IReadOnlyList<Game.Prefabs.PrefabBase> prefabBases) : System.Void`  

```csharp
private static System.Void ValidateData(System.Collections.Generic.IReadOnlyList<Game.Prefabs.PrefabBase> prefabBases);
```

- `private static ValidatePrefabBase(Game.Prefabs.PrefabBase prefabBase, System.String name, System.String guid, System.Int32 indexCount, System.Int32 vertexCount, System.Int32 meshCount, System.Boolean hasGeometryAsset, System.Boolean isImpostor) : System.Void`  

```csharp
private static System.Void ValidatePrefabBase(Game.Prefabs.PrefabBase prefabBase, System.String name, System.String guid, System.Int32 indexCount, System.Int32 vertexCount, System.Int32 meshCount, System.Boolean hasGeometryAsset, System.Boolean isImpostor);
```


## Nested types

- `Game.Debug.Tests.TestScenarioAssetImporter+<EU_TestResidentialLowSignature03>d__12`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<EU_TestResidentialMedium01_L1_2x2>d__13`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<EU_TestResidentialMedium01_L3_2x2>d__14`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<EU_TestTrafficLightCar01>d__15`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<ImportAsset>d__5`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<OnCleanup>d__11`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<OnPrepare>d__3`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestAppleTree01>d__16`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestAutomatedParkingBuilding01>d__17`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestBirchTree>d__18`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestCar01>d__19`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestFerrisWheel01>d__20`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestGasBottle01>d__21`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestInternationalAirport01>d__22`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestParkingHall01>d__23`  
- `Game.Debug.Tests.TestScenarioAssetImporter+<TestRoadMaintenanceVehicle01>d__24`  

