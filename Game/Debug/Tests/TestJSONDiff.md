# Game.Debug.Tests.TestJSONDiff

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class TestJSONDiff : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private Game.Debug.Tests.TestJSONDiff+BaseTestClass[] SourceObjectArray { private get; }
    private Game.Debug.Tests.TestJSONDiff+BaseTestClass[] DefaultObjectArray { private get; }
    private System.Collections.Generic.List<Game.Debug.Tests.TestJSONDiff+BaseTestClass> SourceObjectList { private get; }
    private System.Collections.Generic.List<Game.Debug.Tests.TestJSONDiff+BaseTestClass> DefaultObjectList { private get; }
    private System.Collections.Generic.Dictionary<System.String, Game.Debug.Tests.TestJSONDiff+BaseTestClass> SourceObjectDic { private get; }
    private System.Collections.Generic.Dictionary<System.String, Game.Debug.Tests.TestJSONDiff+BaseTestClass> DefaultObjectDic { private get; }
    private Game.Debug.Tests.TestJSONDiff+SimpleTestObject SourceObject { private get; }
    private Game.Debug.Tests.TestJSONDiff+SimpleTestObject DefaultObject { private get; }

    public TestJSONDiff();

    private System.Void Test<T>(T sourceObject, T defaultObject, System.Func<T, Colossal.Json.Variant> expectedGetter);
    private System.Void TestBool();
    private System.Void TestByte();
    private System.Void TestChar();
    private System.Void TestDateTime();
    private System.Void TestDecimal();
    private System.Void TestDouble();
    private System.Void TestEnum();
    private System.Void TestEqual<T>(T value, Colossal.Json.DiffUtility+Options options);
    private System.Void TestFloat();
    private System.Void TestGUID();
    private System.Void TestIConvertible(System.IConvertible sourceObject, System.IConvertible defaultObject);
    private System.Void TestInt();
    private System.Void TestIntArray();
    private System.Void TestIntDic();
    private System.Void TestIntList();
    private System.Void TestIPAddress();
    private System.Void TestLevel();
    private System.Void TestLong();
    private System.Void TestNotEqual<T>(T sourceObject, T defaultObject, Colossal.Json.Variant expected, Colossal.Json.DiffUtility+Options options);
    private System.Void TestNull<T>(T value, Colossal.Json.Variant expected, Colossal.Json.DiffUtility+Options options);
    private System.Void TestObject();
    private System.Void TestObjectArray();
    private System.Void TestObjectArrayWithType();
    private System.Void TestObjectDic();
    private System.Void TestObjectDicWithType();
    private System.Void TestObjectList();
    private System.Void TestObjectListWithType();
    private System.Void TestObjectObject();
    private System.Void TestObjectObjectWithType();
    private System.Void TestSByte();
    private System.Void TestShort();
    private System.Void TestString();
    private System.Void TestTimeSpan();
    private System.Void TestUInt();
    private System.Void TestULong();
    private System.Void TestUShort();
}
```


## Properties

- `private Game.Debug.Tests.TestJSONDiff+BaseTestClass[] SourceObjectArray { private get }`  

```csharp
private Game.Debug.Tests.TestJSONDiff+BaseTestClass[] SourceObjectArray { private get; }
```

- `private Game.Debug.Tests.TestJSONDiff+BaseTestClass[] DefaultObjectArray { private get }`  

```csharp
private Game.Debug.Tests.TestJSONDiff+BaseTestClass[] DefaultObjectArray { private get; }
```

- `private System.Collections.Generic.List<Game.Debug.Tests.TestJSONDiff+BaseTestClass> SourceObjectList { private get }`  

```csharp
private System.Collections.Generic.List<Game.Debug.Tests.TestJSONDiff+BaseTestClass> SourceObjectList { private get; }
```

- `private System.Collections.Generic.List<Game.Debug.Tests.TestJSONDiff+BaseTestClass> DefaultObjectList { private get }`  

```csharp
private System.Collections.Generic.List<Game.Debug.Tests.TestJSONDiff+BaseTestClass> DefaultObjectList { private get; }
```

- `private System.Collections.Generic.Dictionary<System.String, Game.Debug.Tests.TestJSONDiff+BaseTestClass> SourceObjectDic { private get }`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.Debug.Tests.TestJSONDiff+BaseTestClass> SourceObjectDic { private get; }
```

- `private System.Collections.Generic.Dictionary<System.String, Game.Debug.Tests.TestJSONDiff+BaseTestClass> DefaultObjectDic { private get }`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.Debug.Tests.TestJSONDiff+BaseTestClass> DefaultObjectDic { private get; }
```

- `private Game.Debug.Tests.TestJSONDiff+SimpleTestObject SourceObject { private get }`  

```csharp
private Game.Debug.Tests.TestJSONDiff+SimpleTestObject SourceObject { private get; }
```

- `private Game.Debug.Tests.TestJSONDiff+SimpleTestObject DefaultObject { private get }`  

```csharp
private Game.Debug.Tests.TestJSONDiff+SimpleTestObject DefaultObject { private get; }
```


## Constructors

- `public TestJSONDiff()`  

```csharp
public TestJSONDiff();
```


## Methods

- `private Test<T>(T sourceObject, T defaultObject, System.Func<T, Colossal.Json.Variant> expectedGetter) : System.Void`  

```csharp
private System.Void Test<T>(T sourceObject, T defaultObject, System.Func<T, Colossal.Json.Variant> expectedGetter);
```

- `private TestBool() : System.Void`  

```csharp
private System.Void TestBool();
```

- `private TestByte() : System.Void`  

```csharp
private System.Void TestByte();
```

- `private TestChar() : System.Void`  

```csharp
private System.Void TestChar();
```

- `private TestDateTime() : System.Void`  

```csharp
private System.Void TestDateTime();
```

- `private TestDecimal() : System.Void`  

```csharp
private System.Void TestDecimal();
```

- `private TestDouble() : System.Void`  

```csharp
private System.Void TestDouble();
```

- `private TestEnum() : System.Void`  

```csharp
private System.Void TestEnum();
```

- `private TestEqual<T>(T value, Colossal.Json.DiffUtility+Options options = None) : System.Void`  

```csharp
private System.Void TestEqual<T>(T value, Colossal.Json.DiffUtility+Options options);
```

- `private TestFloat() : System.Void`  

```csharp
private System.Void TestFloat();
```

- `private TestGUID() : System.Void`  

```csharp
private System.Void TestGUID();
```

- `private TestIConvertible(System.IConvertible sourceObject, System.IConvertible defaultObject) : System.Void`  

```csharp
private System.Void TestIConvertible(System.IConvertible sourceObject, System.IConvertible defaultObject);
```

- `private TestInt() : System.Void`  

```csharp
private System.Void TestInt();
```

- `private TestIntArray() : System.Void`  

```csharp
private System.Void TestIntArray();
```

- `private TestIntDic() : System.Void`  

```csharp
private System.Void TestIntDic();
```

- `private TestIntList() : System.Void`  

```csharp
private System.Void TestIntList();
```

- `private TestIPAddress() : System.Void`  

```csharp
private System.Void TestIPAddress();
```

- `private TestLevel() : System.Void`  

```csharp
private System.Void TestLevel();
```

- `private TestLong() : System.Void`  

```csharp
private System.Void TestLong();
```

- `private TestNotEqual<T>(T sourceObject, T defaultObject, Colossal.Json.Variant expected, Colossal.Json.DiffUtility+Options options = None) : System.Void`  

```csharp
private System.Void TestNotEqual<T>(T sourceObject, T defaultObject, Colossal.Json.Variant expected, Colossal.Json.DiffUtility+Options options);
```

- `private TestNull<T>(T value, Colossal.Json.Variant expected, Colossal.Json.DiffUtility+Options options = None) : System.Void`  

```csharp
private System.Void TestNull<T>(T value, Colossal.Json.Variant expected, Colossal.Json.DiffUtility+Options options);
```

- `private TestObject() : System.Void`  

```csharp
private System.Void TestObject();
```

- `private TestObjectArray() : System.Void`  

```csharp
private System.Void TestObjectArray();
```

- `private TestObjectArrayWithType() : System.Void`  

```csharp
private System.Void TestObjectArrayWithType();
```

- `private TestObjectDic() : System.Void`  

```csharp
private System.Void TestObjectDic();
```

- `private TestObjectDicWithType() : System.Void`  

```csharp
private System.Void TestObjectDicWithType();
```

- `private TestObjectList() : System.Void`  

```csharp
private System.Void TestObjectList();
```

- `private TestObjectListWithType() : System.Void`  

```csharp
private System.Void TestObjectListWithType();
```

- `private TestObjectObject() : System.Void`  

```csharp
private System.Void TestObjectObject();
```

- `private TestObjectObjectWithType() : System.Void`  

```csharp
private System.Void TestObjectObjectWithType();
```

- `private TestSByte() : System.Void`  

```csharp
private System.Void TestSByte();
```

- `private TestShort() : System.Void`  

```csharp
private System.Void TestShort();
```

- `private TestString() : System.Void`  

```csharp
private System.Void TestString();
```

- `private TestTimeSpan() : System.Void`  

```csharp
private System.Void TestTimeSpan();
```

- `private TestUInt() : System.Void`  

```csharp
private System.Void TestUInt();
```

- `private TestULong() : System.Void`  

```csharp
private System.Void TestULong();
```

- `private TestUShort() : System.Void`  

```csharp
private System.Void TestUShort();
```


## Nested types

- `Game.Debug.Tests.TestJSONDiff+TestClass`  
- `Game.Debug.Tests.TestJSONDiff+SimpleTestObject`  
- `Game.Debug.Tests.TestJSONDiff+BaseTestClass`  
- `Game.Debug.Tests.TestJSONDiff+ATestClass`  
- `Game.Debug.Tests.TestJSONDiff+BTestClass`  
- `Game.Debug.Tests.TestJSONDiff+EnumTest`  
- `Game.Debug.Tests.TestJSONDiff+<>c`  

