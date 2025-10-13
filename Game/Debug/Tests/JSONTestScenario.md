# Game.Debug.Tests.JSONTestScenario

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class JSONTestScenario : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private static System.Boolean afterDecodeCallbackFired;
    private static System.Boolean beforeEncodeCallbackFired;
    private static System.Boolean loadCallbackFired;

    public JSONTestScenario();

    protected virtual System.Threading.Tasks.Task OnCleanup();
    private static System.Void SupportTypeForAOT();
    public System.Void TestAOTCompatibility();
    public System.Void TestDumpBool();
    public System.Void TestDumpClass();
    public System.Void TestDumpClassNoTypeHint();
    public System.Void TestDumpClassPrettyPrint();
    public System.Void TestDumpDecimalType();
    public System.Void TestDumpDict();
    public System.Void TestDumpDictWithEnumKeys();
    public System.Void TestDumpEnum();
    public System.Void TestDumpFloatTypes();
    public System.Void TestDumpFloatTypesForGermanCulture();
    public System.Void TestDumpGuid();
    public System.Void TestDumpHash();
    public System.Void TestDumpIntegerTypes();
    public System.Void TestDumpJaggedArray();
    public System.Void TestDumpList();
    public System.Void TestDumpNull();
    public System.Void TestDumpOuterClassWithForcedInnerTypeHint();
    public System.Void TestDumpOuterClassWithNoTypeHintPropagatesToInnerClasses();
    public System.Void TestDumpProxyArray();
    public System.Void TestDumpProxyBoolean();
    public System.Void TestDumpProxyNumber();
    public System.Void TestDumpProxyObject();
    public System.Void TestDumpProxyString();
    public System.Void TestDumpRank1Array();
    public System.Void TestDumpRank2Array();
    public System.Void TestDumpRank3Array();
    public System.Void TestDumpSet();
    public System.Void TestDumpString();
    public System.Void TestDumpStruct();
    public System.Void TestDumpUnityTypes();
    public System.Void TestEncodeWithIgnoreHierarchyOrderEnabled();
    public System.Void TestGuidAndHashInClass();
    public System.Void TestLoadAlias();
    public System.Void TestLoadBool();
    public System.Void TestLoadClass();
    public System.Void TestLoadDict();
    public System.Void TestLoadDictIntoProxy();
    public System.Void TestLoadDictWithEnumKeys();
    public System.Void TestLoadEnum();
    public System.Void TestLoadFloatTypes();
    public System.Void TestLoadGuid();
    public System.Void TestLoadHash();
    public System.Void TestLoadIntegerTypes();
    public System.Void TestLoadJaggedArray();
    public System.Void TestLoadList();
    public System.Void TestLoadNull();
    public System.Void TestLoadOverride();
    public System.Void TestLoadRank1Array();
    public System.Void TestLoadRank2Array();
    public System.Void TestLoadRank3Array();
    public System.Void TestLoadSet();
    public System.Void TestLoadString();
    public System.Void TestLoadStruct();
    public System.Void TestLoadUnityTypes();
}
```


## Fields

- `private static System.Boolean afterDecodeCallbackFired`  

```csharp
private static System.Boolean afterDecodeCallbackFired;
```

- `private static System.Boolean beforeEncodeCallbackFired`  

```csharp
private static System.Boolean beforeEncodeCallbackFired;
```

- `private static System.Boolean loadCallbackFired`  

```csharp
private static System.Boolean loadCallbackFired;
```


## Constructors

- `public JSONTestScenario()`  

```csharp
public JSONTestScenario();
```


## Methods

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `private static SupportTypeForAOT() : System.Void`  

```csharp
private static System.Void SupportTypeForAOT();
```

- `public TestAOTCompatibility() : System.Void`  

```csharp
public System.Void TestAOTCompatibility();
```

- `public TestDumpBool() : System.Void`  

```csharp
public System.Void TestDumpBool();
```

- `public TestDumpClass() : System.Void`  

```csharp
public System.Void TestDumpClass();
```

- `public TestDumpClassNoTypeHint() : System.Void`  

```csharp
public System.Void TestDumpClassNoTypeHint();
```

- `public TestDumpClassPrettyPrint() : System.Void`  

```csharp
public System.Void TestDumpClassPrettyPrint();
```

- `public TestDumpDecimalType() : System.Void`  

```csharp
public System.Void TestDumpDecimalType();
```

- `public TestDumpDict() : System.Void`  

```csharp
public System.Void TestDumpDict();
```

- `public TestDumpDictWithEnumKeys() : System.Void`  

```csharp
public System.Void TestDumpDictWithEnumKeys();
```

- `public TestDumpEnum() : System.Void`  

```csharp
public System.Void TestDumpEnum();
```

- `public TestDumpFloatTypes() : System.Void`  

```csharp
public System.Void TestDumpFloatTypes();
```

- `public TestDumpFloatTypesForGermanCulture() : System.Void`  

```csharp
public System.Void TestDumpFloatTypesForGermanCulture();
```

- `public TestDumpGuid() : System.Void`  

```csharp
public System.Void TestDumpGuid();
```

- `public TestDumpHash() : System.Void`  

```csharp
public System.Void TestDumpHash();
```

- `public TestDumpIntegerTypes() : System.Void`  

```csharp
public System.Void TestDumpIntegerTypes();
```

- `public TestDumpJaggedArray() : System.Void`  

```csharp
public System.Void TestDumpJaggedArray();
```

- `public TestDumpList() : System.Void`  

```csharp
public System.Void TestDumpList();
```

- `public TestDumpNull() : System.Void`  

```csharp
public System.Void TestDumpNull();
```

- `public TestDumpOuterClassWithForcedInnerTypeHint() : System.Void`  

```csharp
public System.Void TestDumpOuterClassWithForcedInnerTypeHint();
```

- `public TestDumpOuterClassWithNoTypeHintPropagatesToInnerClasses() : System.Void`  

```csharp
public System.Void TestDumpOuterClassWithNoTypeHintPropagatesToInnerClasses();
```

- `public TestDumpProxyArray() : System.Void`  

```csharp
public System.Void TestDumpProxyArray();
```

- `public TestDumpProxyBoolean() : System.Void`  

```csharp
public System.Void TestDumpProxyBoolean();
```

- `public TestDumpProxyNumber() : System.Void`  

```csharp
public System.Void TestDumpProxyNumber();
```

- `public TestDumpProxyObject() : System.Void`  

```csharp
public System.Void TestDumpProxyObject();
```

- `public TestDumpProxyString() : System.Void`  

```csharp
public System.Void TestDumpProxyString();
```

- `public TestDumpRank1Array() : System.Void`  

```csharp
public System.Void TestDumpRank1Array();
```

- `public TestDumpRank2Array() : System.Void`  

```csharp
public System.Void TestDumpRank2Array();
```

- `public TestDumpRank3Array() : System.Void`  

```csharp
public System.Void TestDumpRank3Array();
```

- `public TestDumpSet() : System.Void`  

```csharp
public System.Void TestDumpSet();
```

- `public TestDumpString() : System.Void`  

```csharp
public System.Void TestDumpString();
```

- `public TestDumpStruct() : System.Void`  

```csharp
public System.Void TestDumpStruct();
```

- `public TestDumpUnityTypes() : System.Void`  

```csharp
public System.Void TestDumpUnityTypes();
```

- `public TestEncodeWithIgnoreHierarchyOrderEnabled() : System.Void`  

```csharp
public System.Void TestEncodeWithIgnoreHierarchyOrderEnabled();
```

- `public TestGuidAndHashInClass() : System.Void`  

```csharp
public System.Void TestGuidAndHashInClass();
```

- `public TestLoadAlias() : System.Void`  

```csharp
public System.Void TestLoadAlias();
```

- `public TestLoadBool() : System.Void`  

```csharp
public System.Void TestLoadBool();
```

- `public TestLoadClass() : System.Void`  

```csharp
public System.Void TestLoadClass();
```

- `public TestLoadDict() : System.Void`  

```csharp
public System.Void TestLoadDict();
```

- `public TestLoadDictIntoProxy() : System.Void`  

```csharp
public System.Void TestLoadDictIntoProxy();
```

- `public TestLoadDictWithEnumKeys() : System.Void`  

```csharp
public System.Void TestLoadDictWithEnumKeys();
```

- `public TestLoadEnum() : System.Void`  

```csharp
public System.Void TestLoadEnum();
```

- `public TestLoadFloatTypes() : System.Void`  

```csharp
public System.Void TestLoadFloatTypes();
```

- `public TestLoadGuid() : System.Void`  

```csharp
public System.Void TestLoadGuid();
```

- `public TestLoadHash() : System.Void`  

```csharp
public System.Void TestLoadHash();
```

- `public TestLoadIntegerTypes() : System.Void`  

```csharp
public System.Void TestLoadIntegerTypes();
```

- `public TestLoadJaggedArray() : System.Void`  

```csharp
public System.Void TestLoadJaggedArray();
```

- `public TestLoadList() : System.Void`  

```csharp
public System.Void TestLoadList();
```

- `public TestLoadNull() : System.Void`  

```csharp
public System.Void TestLoadNull();
```

- `public TestLoadOverride() : System.Void`  

```csharp
public System.Void TestLoadOverride();
```

- `public TestLoadRank1Array() : System.Void`  

```csharp
public System.Void TestLoadRank1Array();
```

- `public TestLoadRank2Array() : System.Void`  

```csharp
public System.Void TestLoadRank2Array();
```

- `public TestLoadRank3Array() : System.Void`  

```csharp
public System.Void TestLoadRank3Array();
```

- `public TestLoadSet() : System.Void`  

```csharp
public System.Void TestLoadSet();
```

- `public TestLoadString() : System.Void`  

```csharp
public System.Void TestLoadString();
```

- `public TestLoadStruct() : System.Void`  

```csharp
public System.Void TestLoadStruct();
```

- `public TestLoadUnityTypes() : System.Void`  

```csharp
public System.Void TestLoadUnityTypes();
```


## Nested types

- `Game.Debug.Tests.JSONTestScenario+TestClass`  
- `Game.Debug.Tests.JSONTestScenario+InnerClass`  
- `Game.Debug.Tests.JSONTestScenario+OuterClass`  
- `Game.Debug.Tests.JSONTestScenario+OuterClassForceInnerTypeHint`  
- `Game.Debug.Tests.JSONTestScenario+TestOverrideA`  
- `Game.Debug.Tests.JSONTestScenario+TestOverrideB`  
- `Game.Debug.Tests.JSONTestScenario+TestEnum`  
- `Game.Debug.Tests.JSONTestScenario+AliasData`  
- `Game.Debug.Tests.JSONTestScenario+ClassA`  
- `Game.Debug.Tests.JSONTestScenario+ClassB`  
- `Game.Debug.Tests.JSONTestScenario+ClassC`  
- `Game.Debug.Tests.JSONTestScenario+GuidContainer`  
- `Game.Debug.Tests.JSONTestScenario+ValueTypes`  
- `Game.Debug.Tests.JSONTestScenario+UnityTypes`  
- `Game.Debug.Tests.JSONTestScenario+TestStruct`  
- `Game.Debug.Tests.JSONTestScenario+<>c`  
- `Game.Debug.Tests.JSONTestScenario+<>c__DisplayClass61_0`  

