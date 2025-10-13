# Colossal.Assertions.Assert

**Assembly:** `Colossal.TestFramework`  
**Namespace:** `Colossal.Assertions`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class Assert
{
    public static System.Void AreApproximatelyEqual(System.Single expected, System.Single actual, System.String message);
    public static System.Void AreApproximatelyEqual(System.Double expected, System.Double actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double2 expected, Unity.Mathematics.double2 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double3 expected, Unity.Mathematics.double3 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double4 expected, Unity.Mathematics.double4 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double2x2 expected, Unity.Mathematics.double2x2 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double2x3 expected, Unity.Mathematics.double2x3 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double2x4 expected, Unity.Mathematics.double2x4 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double3x2 expected, Unity.Mathematics.double3x2 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double3x3 expected, Unity.Mathematics.double3x3 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double3x4 expected, Unity.Mathematics.double3x4 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double4x2 expected, Unity.Mathematics.double4x2 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double4x3 expected, Unity.Mathematics.double4x3 actual, System.Double tolerance, System.String message);
    public static System.Void AreApproximatelyEqual(Unity.Mathematics.double4x4 expected, Unity.Mathematics.double4x4 actual, System.Double tolerance, System.String message);
    public static System.Void AreEqual<T>(Unity.Collections.NativeArray<T> expected, Unity.Collections.NativeArray<T> actual, System.String message);
    public static System.Void AreEqual<T>(T expected, T actual, System.String message);
    public static System.Void AreEqual<T>(T expected, T actual, System.Collections.Generic.IEqualityComparer<T> comparer, System.String message);
    public static System.Void AreNotApproximatelyEqual(System.Single expected, System.Single actual, System.String message);
    public static System.Void AreNotApproximatelyEqual(System.Double expected, System.Double actual, System.Double tolerance, System.String message);
    public static System.Void AreNotEqual<T>(T expected, T actual, System.String message);
    public static System.Void Contains(System.String s, System.String c, System.String message);
    public static System.Void DoesNotThrow(System.Action action);
    public static System.Void IsFalse(System.Boolean condition, System.String message);
    public static System.Void IsNotNull<T>(T condition, System.String message);
    public static System.Void IsNull<T>(T condition, System.String message);
    public static System.Void IsTrue(System.Boolean condition, System.String message);
    public static T LogContains<T>(System.Func<T> action, Colossal.Logging.Level expectedLevel, System.Collections.Generic.List<System.String> containsInExpectedOrder);
    public static System.Void Logs<T>(System.Action action, Colossal.Logging.Level expectedLevel, System.String expectedMessage);
    public static System.Void NotContains(System.String s, System.String c, System.String message);
    public static System.Void SequenceEqual<T>(System.Collections.Generic.IEnumerable<T> expected, System.Collections.Generic.IEnumerable<T> actual, System.String message);
    public static T Throws<T>(System.Action action, System.String message);
}
```


## Methods

- `public static AreApproximatelyEqual(System.Single expected, System.Single actual, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(System.Single expected, System.Single actual, System.String message);
```

- `public static AreApproximatelyEqual(System.Double expected, System.Double actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(System.Double expected, System.Double actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double2 expected, Unity.Mathematics.double2 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double2 expected, Unity.Mathematics.double2 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double3 expected, Unity.Mathematics.double3 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double3 expected, Unity.Mathematics.double3 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double4 expected, Unity.Mathematics.double4 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double4 expected, Unity.Mathematics.double4 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double2x2 expected, Unity.Mathematics.double2x2 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double2x2 expected, Unity.Mathematics.double2x2 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double2x3 expected, Unity.Mathematics.double2x3 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double2x3 expected, Unity.Mathematics.double2x3 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double2x4 expected, Unity.Mathematics.double2x4 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double2x4 expected, Unity.Mathematics.double2x4 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double3x2 expected, Unity.Mathematics.double3x2 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double3x2 expected, Unity.Mathematics.double3x2 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double3x3 expected, Unity.Mathematics.double3x3 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double3x3 expected, Unity.Mathematics.double3x3 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double3x4 expected, Unity.Mathematics.double3x4 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double3x4 expected, Unity.Mathematics.double3x4 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double4x2 expected, Unity.Mathematics.double4x2 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double4x2 expected, Unity.Mathematics.double4x2 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double4x3 expected, Unity.Mathematics.double4x3 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double4x3 expected, Unity.Mathematics.double4x3 actual, System.Double tolerance, System.String message);
```

- `public static AreApproximatelyEqual(Unity.Mathematics.double4x4 expected, Unity.Mathematics.double4x4 actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreApproximatelyEqual(Unity.Mathematics.double4x4 expected, Unity.Mathematics.double4x4 actual, System.Double tolerance, System.String message);
```

- `public static AreEqual<T>(Unity.Collections.NativeArray<T> expected, Unity.Collections.NativeArray<T> actual, System.String message = null) : System.Void`  

```csharp
public static System.Void AreEqual<T>(Unity.Collections.NativeArray<T> expected, Unity.Collections.NativeArray<T> actual, System.String message);
```

- `public static AreEqual<T>(T expected, T actual, System.String message = null) : System.Void`  

```csharp
public static System.Void AreEqual<T>(T expected, T actual, System.String message);
```

- `public static AreEqual<T>(T expected, T actual, System.Collections.Generic.IEqualityComparer<T> comparer, System.String message = null) : System.Void`  

```csharp
public static System.Void AreEqual<T>(T expected, T actual, System.Collections.Generic.IEqualityComparer<T> comparer, System.String message);
```

- `public static AreNotApproximatelyEqual(System.Single expected, System.Single actual, System.String message = null) : System.Void`  

```csharp
public static System.Void AreNotApproximatelyEqual(System.Single expected, System.Single actual, System.String message);
```

- `public static AreNotApproximatelyEqual(System.Double expected, System.Double actual, System.Double tolerance = 1E-13, System.String message = null) : System.Void`  

```csharp
public static System.Void AreNotApproximatelyEqual(System.Double expected, System.Double actual, System.Double tolerance, System.String message);
```

- `public static AreNotEqual<T>(T expected, T actual, System.String message = null) : System.Void`  

```csharp
public static System.Void AreNotEqual<T>(T expected, T actual, System.String message);
```

- `public static Contains(System.String s, System.String c, System.String message = null) : System.Void`  

```csharp
public static System.Void Contains(System.String s, System.String c, System.String message);
```

- `public static DoesNotThrow(System.Action action) : System.Void`  

```csharp
public static System.Void DoesNotThrow(System.Action action);
```

- `public static IsFalse(System.Boolean condition, System.String message = null) : System.Void`  

```csharp
public static System.Void IsFalse(System.Boolean condition, System.String message);
```

- `public static IsNotNull<T>(T condition, System.String message = null) : System.Void`  

```csharp
public static System.Void IsNotNull<T>(T condition, System.String message);
```

- `public static IsNull<T>(T condition, System.String message = null) : System.Void`  

```csharp
public static System.Void IsNull<T>(T condition, System.String message);
```

- `public static IsTrue(System.Boolean condition, System.String message = null) : System.Void`  

```csharp
public static System.Void IsTrue(System.Boolean condition, System.String message);
```

- `public static LogContains<T>(System.Func<T> action, Colossal.Logging.Level expectedLevel, System.Collections.Generic.List<System.String> containsInExpectedOrder = null) : T`  

```csharp
public static T LogContains<T>(System.Func<T> action, Colossal.Logging.Level expectedLevel, System.Collections.Generic.List<System.String> containsInExpectedOrder);
```

- `public static Logs<T>(System.Action action, Colossal.Logging.Level expectedLevel, System.String expectedMessage = null) : System.Void`  

```csharp
public static System.Void Logs<T>(System.Action action, Colossal.Logging.Level expectedLevel, System.String expectedMessage);
```

- `public static NotContains(System.String s, System.String c, System.String message = null) : System.Void`  

```csharp
public static System.Void NotContains(System.String s, System.String c, System.String message);
```

- `public static SequenceEqual<T>(System.Collections.Generic.IEnumerable<T> expected, System.Collections.Generic.IEnumerable<T> actual, System.String message = null) : System.Void`  

```csharp
public static System.Void SequenceEqual<T>(System.Collections.Generic.IEnumerable<T> expected, System.Collections.Generic.IEnumerable<T> actual, System.String message);
```

- `public static Throws<T>(System.Action action, System.String message = null) : T`  

```csharp
public static T Throws<T>(System.Action action, System.String message);
```


## Nested types

- `Colossal.Assertions.Assert+<>c__DisplayClass29_0<T>`  
- `Colossal.Assertions.Assert+<>c__DisplayClass30_0<T>`  

