# Game.Debug.Tests.LongFileTestScenario

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Code

```csharp
public class LongFileTestScenario : Colossal.TestFramework.TestScenario, Colossal.TestFramework.ITestStep
{
    private System.String rootTestDir;
    private System.String tempTestDir;
    private System.String longPathDirectory;
    private System.String longPathFilename;
    private static const System.String kFilename0;
    private static const System.String kFilename1;
    private static const System.String kFilename2;

    public LongFileTestScenario();

    private System.String GetFilePath(System.String filename);
    private System.String GetFilePath(System.String filename, System.String root);
    protected virtual System.Threading.Tasks.Task OnCleanup();
    protected virtual System.Threading.Tasks.Task OnPrepare();
    private System.Void TestAppendAllLines();
    private System.Void TestAppendAllLinesEncoding();
    private System.Void TestAppendAllText();
    private System.Void TestAppendAllTextEncoding();
    private System.Void TestAppendText();
    private System.Void TestCleanup();
    private System.Void TestCopyWithoutOverwrite();
    private System.Void TestCopyWithoutOverwriteAndExistingFile();
    private System.Void TestCopyWithOverwrite();
    private System.Void TestCreate();
    private System.Void TestCreateText();
    private System.Void TestCreateWithBufferSize();
    private System.Void TestCreateWithBuffersizeFileOptions();
    private System.Void TestCreateWithFileSecurity();
    private System.Void TestDeleteOnMissingFileDoesNotThrow();
    private System.Void TestExists();
    private System.Void TestGetCreationTimeUtc();
    private System.Void TestGetLastAccessTimeUtc();
    private System.Void TestGetLastWriteTimeUtc();
    private System.Void TestMove();
    private System.Void TestMoveCopy();
    private System.Void TestOpenExisting();
    private System.Void TestOpenNonExistent();
    private System.Void TestOpenRead();
    private System.Void TestOpenWithAccess();
    private System.Void TestOpenWithAccessNonExistent();
    private System.Void TestOpenWrite();
    private System.Void TestReadAllBytes();
    private System.Void TestReadAllBytesOnLargeFile();
    private System.Void TestReadAllLines();
    private System.Void TestReadAllText();
    private System.Void TestReadAllTextEncoding();
    private System.Void TestReadAllTextNewFile();
    private System.Void TestReadAllTextNullPath();
    private System.Void TestSetAccessControl();
    private System.Void TestWriteAllBytes();
    private System.Void TestWriteAllLines();
    private System.Void TestWriteAllLinesWithEncoding();
    private System.Void TestWriteAllText();
    private System.Void TestWriteAllTextEncoding();
    private System.Void TestWriteAllTextNullPath();
}
```


## Fields

- `private System.String rootTestDir`  

```csharp
private System.String rootTestDir;
```

- `private System.String tempTestDir`  

```csharp
private System.String tempTestDir;
```

- `private System.String longPathDirectory`  

```csharp
private System.String longPathDirectory;
```

- `private System.String longPathFilename`  

```csharp
private System.String longPathFilename;
```

- `private static const System.String kFilename0`  

```csharp
private static const System.String kFilename0;
```

- `private static const System.String kFilename1`  

```csharp
private static const System.String kFilename1;
```

- `private static const System.String kFilename2`  

```csharp
private static const System.String kFilename2;
```


## Constructors

- `public LongFileTestScenario()`  

```csharp
public LongFileTestScenario();
```


## Methods

- `private GetFilePath(System.String filename) : System.String`  

```csharp
private System.String GetFilePath(System.String filename);
```

- `private GetFilePath(System.String filename, System.String root) : System.String`  

```csharp
private System.String GetFilePath(System.String filename, System.String root);
```

- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnCleanup();
```

- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  

```csharp
protected virtual System.Threading.Tasks.Task OnPrepare();
```

- `private TestAppendAllLines() : System.Void`  

```csharp
private System.Void TestAppendAllLines();
```

- `private TestAppendAllLinesEncoding() : System.Void`  

```csharp
private System.Void TestAppendAllLinesEncoding();
```

- `private TestAppendAllText() : System.Void`  

```csharp
private System.Void TestAppendAllText();
```

- `private TestAppendAllTextEncoding() : System.Void`  

```csharp
private System.Void TestAppendAllTextEncoding();
```

- `private TestAppendText() : System.Void`  

```csharp
private System.Void TestAppendText();
```

- `private TestCleanup() : System.Void`  

```csharp
private System.Void TestCleanup();
```

- `private TestCopyWithoutOverwrite() : System.Void`  

```csharp
private System.Void TestCopyWithoutOverwrite();
```

- `private TestCopyWithoutOverwriteAndExistingFile() : System.Void`  

```csharp
private System.Void TestCopyWithoutOverwriteAndExistingFile();
```

- `private TestCopyWithOverwrite() : System.Void`  

```csharp
private System.Void TestCopyWithOverwrite();
```

- `private TestCreate() : System.Void`  

```csharp
private System.Void TestCreate();
```

- `private TestCreateText() : System.Void`  

```csharp
private System.Void TestCreateText();
```

- `private TestCreateWithBufferSize() : System.Void`  

```csharp
private System.Void TestCreateWithBufferSize();
```

- `private TestCreateWithBuffersizeFileOptions() : System.Void`  

```csharp
private System.Void TestCreateWithBuffersizeFileOptions();
```

- `private TestCreateWithFileSecurity() : System.Void`  

```csharp
private System.Void TestCreateWithFileSecurity();
```

- `private TestDeleteOnMissingFileDoesNotThrow() : System.Void`  

```csharp
private System.Void TestDeleteOnMissingFileDoesNotThrow();
```

- `private TestExists() : System.Void`  

```csharp
private System.Void TestExists();
```

- `private TestGetCreationTimeUtc() : System.Void`  

```csharp
private System.Void TestGetCreationTimeUtc();
```

- `private TestGetLastAccessTimeUtc() : System.Void`  

```csharp
private System.Void TestGetLastAccessTimeUtc();
```

- `private TestGetLastWriteTimeUtc() : System.Void`  

```csharp
private System.Void TestGetLastWriteTimeUtc();
```

- `private TestMove() : System.Void`  

```csharp
private System.Void TestMove();
```

- `private TestMoveCopy() : System.Void`  

```csharp
private System.Void TestMoveCopy();
```

- `private TestOpenExisting() : System.Void`  

```csharp
private System.Void TestOpenExisting();
```

- `private TestOpenNonExistent() : System.Void`  

```csharp
private System.Void TestOpenNonExistent();
```

- `private TestOpenRead() : System.Void`  

```csharp
private System.Void TestOpenRead();
```

- `private TestOpenWithAccess() : System.Void`  

```csharp
private System.Void TestOpenWithAccess();
```

- `private TestOpenWithAccessNonExistent() : System.Void`  

```csharp
private System.Void TestOpenWithAccessNonExistent();
```

- `private TestOpenWrite() : System.Void`  

```csharp
private System.Void TestOpenWrite();
```

- `private TestReadAllBytes() : System.Void`  

```csharp
private System.Void TestReadAllBytes();
```

- `private TestReadAllBytesOnLargeFile() : System.Void`  

```csharp
private System.Void TestReadAllBytesOnLargeFile();
```

- `private TestReadAllLines() : System.Void`  

```csharp
private System.Void TestReadAllLines();
```

- `private TestReadAllText() : System.Void`  

```csharp
private System.Void TestReadAllText();
```

- `private TestReadAllTextEncoding() : System.Void`  

```csharp
private System.Void TestReadAllTextEncoding();
```

- `private TestReadAllTextNewFile() : System.Void`  

```csharp
private System.Void TestReadAllTextNewFile();
```

- `private TestReadAllTextNullPath() : System.Void`  

```csharp
private System.Void TestReadAllTextNullPath();
```

- `private TestSetAccessControl() : System.Void`  

```csharp
private System.Void TestSetAccessControl();
```

- `private TestWriteAllBytes() : System.Void`  

```csharp
private System.Void TestWriteAllBytes();
```

- `private TestWriteAllLines() : System.Void`  

```csharp
private System.Void TestWriteAllLines();
```

- `private TestWriteAllLinesWithEncoding() : System.Void`  

```csharp
private System.Void TestWriteAllLinesWithEncoding();
```

- `private TestWriteAllText() : System.Void`  

```csharp
private System.Void TestWriteAllText();
```

- `private TestWriteAllTextEncoding() : System.Void`  

```csharp
private System.Void TestWriteAllTextEncoding();
```

- `private TestWriteAllTextNullPath() : System.Void`  

```csharp
private System.Void TestWriteAllTextNullPath();
```


## Nested types

- `Game.Debug.Tests.LongFileTestScenario+Utils`  
- `Game.Debug.Tests.LongFileTestScenario+<>c`  
- `Game.Debug.Tests.LongFileTestScenario+<>c__DisplayClass24_0`  
- `Game.Debug.Tests.LongFileTestScenario+<>c__DisplayClass32_0`  
- `Game.Debug.Tests.LongFileTestScenario+<>c__DisplayClass33_0`  
- `Game.Debug.Tests.LongFileTestScenario+<>c__DisplayClass38_0`  

