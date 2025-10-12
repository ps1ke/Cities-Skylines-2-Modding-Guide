# Game.Debug.Tests.TestJSONDiff

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Properties

- `private Game.Debug.Tests.TestJSONDiff+BaseTestClass[] SourceObjectArray { private get }`  
- `private Game.Debug.Tests.TestJSONDiff+BaseTestClass[] DefaultObjectArray { private get }`  
- `private System.Collections.Generic.List<Game.Debug.Tests.TestJSONDiff+BaseTestClass> SourceObjectList { private get }`  
- `private System.Collections.Generic.List<Game.Debug.Tests.TestJSONDiff+BaseTestClass> DefaultObjectList { private get }`  
- `private System.Collections.Generic.Dictionary<System.String, Game.Debug.Tests.TestJSONDiff+BaseTestClass> SourceObjectDic { private get }`  
- `private System.Collections.Generic.Dictionary<System.String, Game.Debug.Tests.TestJSONDiff+BaseTestClass> DefaultObjectDic { private get }`  
- `private Game.Debug.Tests.TestJSONDiff+SimpleTestObject SourceObject { private get }`  
- `private Game.Debug.Tests.TestJSONDiff+SimpleTestObject DefaultObject { private get }`  

## Constructors

- `public TestJSONDiff()`  

## Methods

- `private Test<T>(T sourceObject, T defaultObject, System.Func<T, Colossal.Json.Variant> expectedGetter) : System.Void`  
- `private TestBool() : System.Void`  
- `private TestByte() : System.Void`  
- `private TestChar() : System.Void`  
- `private TestDateTime() : System.Void`  
- `private TestDecimal() : System.Void`  
- `private TestDouble() : System.Void`  
- `private TestEnum() : System.Void`  
- `private TestEqual<T>(T value, Colossal.Json.DiffUtility+Options options = None) : System.Void`  
- `private TestFloat() : System.Void`  
- `private TestGUID() : System.Void`  
- `private TestIConvertible(System.IConvertible sourceObject, System.IConvertible defaultObject) : System.Void`  
- `private TestInt() : System.Void`  
- `private TestIntArray() : System.Void`  
- `private TestIntDic() : System.Void`  
- `private TestIntList() : System.Void`  
- `private TestIPAddress() : System.Void`  
- `private TestLevel() : System.Void`  
- `private TestLong() : System.Void`  
- `private TestNotEqual<T>(T sourceObject, T defaultObject, Colossal.Json.Variant expected, Colossal.Json.DiffUtility+Options options = None) : System.Void`  
- `private TestNull<T>(T value, Colossal.Json.Variant expected, Colossal.Json.DiffUtility+Options options = None) : System.Void`  
- `private TestObject() : System.Void`  
- `private TestObjectArray() : System.Void`  
- `private TestObjectArrayWithType() : System.Void`  
- `private TestObjectDic() : System.Void`  
- `private TestObjectDicWithType() : System.Void`  
- `private TestObjectList() : System.Void`  
- `private TestObjectListWithType() : System.Void`  
- `private TestObjectObject() : System.Void`  
- `private TestObjectObjectWithType() : System.Void`  
- `private TestSByte() : System.Void`  
- `private TestShort() : System.Void`  
- `private TestString() : System.Void`  
- `private TestTimeSpan() : System.Void`  
- `private TestUInt() : System.Void`  
- `private TestULong() : System.Void`  
- `private TestUShort() : System.Void`  

## Nested types

- `Game.Debug.Tests.TestJSONDiff+TestClass`  
- `Game.Debug.Tests.TestJSONDiff+SimpleTestObject`  
- `Game.Debug.Tests.TestJSONDiff+BaseTestClass`  
- `Game.Debug.Tests.TestJSONDiff+ATestClass`  
- `Game.Debug.Tests.TestJSONDiff+BTestClass`  
- `Game.Debug.Tests.TestJSONDiff+EnumTest`  
- `Game.Debug.Tests.TestJSONDiff+<>c`  

