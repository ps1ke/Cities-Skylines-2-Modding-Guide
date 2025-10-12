# Game.Debug.Tests.MultiPartFileStreamTestScenario

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Fields

- `private System.String m_TestFile`  
- `private static System.Boolean m_CallbackFired`  
- `private static const System.String kTestFileName`  
- `private static const System.Int64 kSmallPartSize`  
- `private static const System.Int32 kNumEntries`  
- `private static const System.Int32 kEntrySize`  
- `private static const System.Int32 kPartSize`  

## Constructors

- `public MultiPartFileStreamTestScenario()`  

## Methods

- `public Concurrency_ReadWrite_Access() : System.Threading.Tasks.Task`  
- `public Dispose_CallsCallback() : System.Void`  
- `private static DisposeCallback(System.Collections.Generic.IReadOnlyList<System.String> files) : System.Void`  
- `public Initialization_WithSmallMaxPartSize_CreatesMultipleParts() : System.Void`  
- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  
- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  
- `private PrepareTest() : System.Void`  
- `public Reading_BeyondTotalLength_ReturnsAvailableData() : System.Void`  
- `public Reading_ExactSplitPosition_ReturnsCorrectData() : System.Void`  
- `public Reading_FromEmptyStream_ReturnsZero() : System.Void`  
- `public Reading_InvalidBufferParameters_ThrowsException() : System.Void`  
- `public Seek_InvalidOrigin_ThrowsException() : System.Void`  
- `public Seek_SetsCorrectPosition() : System.Void`  
- `public Writing_ExactSplitPosition_CreatesMultipleParts() : System.Void`  
- `public Writing_InvalidBufferParameters_ThrowsException() : System.Void`  
- `public Writing_ReadOnlyStream_ThrowsException() : System.Void`  
- `public ZipStressTest() : System.Void`  

## Nested types

- `Game.Debug.Tests.MultiPartFileStreamTestScenario+StreamDataSource`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass10_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass11_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass13_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass14_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass15_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<>c__DisplayClass9_0`  
- `Game.Debug.Tests.MultiPartFileStreamTestScenario+<Concurrency_ReadWrite_Access>d__15`  

