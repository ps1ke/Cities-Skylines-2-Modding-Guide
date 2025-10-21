# Game.Debug.Tests.MultiPartFileStreamTestScenario

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class MultiPartFileStreamTestScenario : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private System.String m_TestFile;
    private static System.Boolean m_CallbackFired;
    private static const System.String kTestFileName;
    private static const System.Int64 kSmallPartSize;
    private static const System.Int32 kNumEntries;
    private static const System.Int32 kEntrySize;
    private static const System.Int32 kPartSize;

    public MultiPartFileStreamTestScenario();

    public System.Threading.Tasks.Task Concurrency_ReadWrite_Access();
    public System.Void Dispose_CallsCallback();
    private static System.Void DisposeCallback(System.Collections.Generic.IReadOnlyList<System.String> files);
    public System.Void Initialization_WithSmallMaxPartSize_CreatesMultipleParts();
    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Void PrepareTest();
    public System.Void Reading_BeyondTotalLength_ReturnsAvailableData();
    public System.Void Reading_ExactSplitPosition_ReturnsCorrectData();
    public System.Void Reading_FromEmptyStream_ReturnsZero();
    public System.Void Reading_InvalidBufferParameters_ThrowsException();
    public System.Void Seek_InvalidOrigin_ThrowsException();
    public System.Void Seek_SetsCorrectPosition();
    public System.Void Writing_ExactSplitPosition_CreatesMultipleParts();
    public System.Void Writing_InvalidBufferParameters_ThrowsException();
    public System.Void Writing_ReadOnlyStream_ThrowsException();
    public System.Void ZipStressTest();
}
```


## Fields

- `private System.String m_TestFile`  

```csharp
private System.String m_TestFile;
```

- `private static System.Boolean m_CallbackFired`  

```csharp
private static System.Boolean m_CallbackFired;
```

- `private static const System.String kTestFileName`  

```csharp
private static const System.String kTestFileName;
```

- `private static const System.Int64 kSmallPartSize`  

```csharp
private static const System.Int64 kSmallPartSize;
```

- `private static const System.Int32 kNumEntries`  

```csharp
private static const System.Int32 kNumEntries;
```

- `private static const System.Int32 kEntrySize`  

```csharp
private static const System.Int32 kEntrySize;
```

- `private static const System.Int32 kPartSize`  

```csharp
private static const System.Int32 kPartSize;
```


## Constructors

- `public MultiPartFileStreamTestScenario()`  

```csharp
public MultiPartFileStreamTestScenario();
```


## Methods

- `public Concurrency_ReadWrite_Access() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Concurrency_ReadWrite_Access();
```

- `public Dispose_CallsCallback() : System.Void`  

```csharp
public System.Void Dispose_CallsCallback();
```

- `private static DisposeCallback(System.Collections.Generic.IReadOnlyList<System.String> files) : System.Void`  

```csharp
private static System.Void DisposeCallback(System.Collections.Generic.IReadOnlyList<System.String> files);
```

- `public Initialization_WithSmallMaxPartSize_CreatesMultipleParts() : System.Void`  

```csharp
public System.Void Initialization_WithSmallMaxPartSize_CreatesMultipleParts();
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `private PrepareTest() : System.Void`  

```csharp
private System.Void PrepareTest();
```

- `public Reading_BeyondTotalLength_ReturnsAvailableData() : System.Void`  

```csharp
public System.Void Reading_BeyondTotalLength_ReturnsAvailableData();
```

- `public Reading_ExactSplitPosition_ReturnsCorrectData() : System.Void`  

```csharp
public System.Void Reading_ExactSplitPosition_ReturnsCorrectData();
```

- `public Reading_FromEmptyStream_ReturnsZero() : System.Void`  

```csharp
public System.Void Reading_FromEmptyStream_ReturnsZero();
```

- `public Reading_InvalidBufferParameters_ThrowsException() : System.Void`  

```csharp
public System.Void Reading_InvalidBufferParameters_ThrowsException();
```

- `public Seek_InvalidOrigin_ThrowsException() : System.Void`  

```csharp
public System.Void Seek_InvalidOrigin_ThrowsException();
```

- `public Seek_SetsCorrectPosition() : System.Void`  

```csharp
public System.Void Seek_SetsCorrectPosition();
```

- `public Writing_ExactSplitPosition_CreatesMultipleParts() : System.Void`  

```csharp
public System.Void Writing_ExactSplitPosition_CreatesMultipleParts();
```

- `public Writing_InvalidBufferParameters_ThrowsException() : System.Void`  

```csharp
public System.Void Writing_InvalidBufferParameters_ThrowsException();
```

- `public Writing_ReadOnlyStream_ThrowsException() : System.Void`  

```csharp
public System.Void Writing_ReadOnlyStream_ThrowsException();
```

- `public ZipStressTest() : System.Void`  

```csharp
public System.Void ZipStressTest();
```


## Nested types

- `Game.Debug.Tests.MultiPartFileStreamTestScenario+StreamDataSource`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass10_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass11_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass13_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass14_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass15_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass9_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<Concurrency_ReadWrite_Access>d__15`  

