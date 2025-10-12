# Game.Debug.Tests.LongFileTestScenario

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.TestFramework.TestScenario`  
**Implements:** `Colossal.TestFramework.ITestStep`  

**Attributes:** `TestDescriptor`  

## Fields

- `private System.String rootTestDir`  
- `private System.String tempTestDir`  
- `private System.String longPathDirectory`  
- `private System.String longPathFilename`  
- `private static const System.String kFilename0`  
- `private static const System.String kFilename1`  
- `private static const System.String kFilename2`  

## Constructors

- `public LongFileTestScenario()`  

## Methods

- `private GetFilePath(System.String filename) : System.String`  
- `private GetFilePath(System.String filename, System.String root) : System.String`  
- `protected virtual OnCleanup() : System.Threading.Tasks.Task`  
- `protected virtual OnPrepare() : System.Threading.Tasks.Task`  
- `private TestAppendAllLines() : System.Void`  
- `private TestAppendAllLinesEncoding() : System.Void`  
- `private TestAppendAllText() : System.Void`  
- `private TestAppendAllTextEncoding() : System.Void`  
- `private TestAppendText() : System.Void`  
- `private TestCleanup() : System.Void`  
- `private TestCopyWithoutOverwrite() : System.Void`  
- `private TestCopyWithoutOverwriteAndExistingFile() : System.Void`  
- `private TestCopyWithOverwrite() : System.Void`  
- `private TestCreate() : System.Void`  
- `private TestCreateText() : System.Void`  
- `private TestCreateWithBufferSize() : System.Void`  
- `private TestCreateWithBuffersizeFileOptions() : System.Void`  
- `private TestCreateWithFileSecurity() : System.Void`  
- `private TestDeleteOnMissingFileDoesNotThrow() : System.Void`  
- `private TestExists() : System.Void`  
- `private TestGetCreationTimeUtc() : System.Void`  
- `private TestGetLastAccessTimeUtc() : System.Void`  
- `private TestGetLastWriteTimeUtc() : System.Void`  
- `private TestMove() : System.Void`  
- `private TestMoveCopy() : System.Void`  
- `private TestOpenExisting() : System.Void`  
- `private TestOpenNonExistent() : System.Void`  
- `private TestOpenRead() : System.Void`  
- `private TestOpenWithAccess() : System.Void`  
- `private TestOpenWithAccessNonExistent() : System.Void`  
- `private TestOpenWrite() : System.Void`  
- `private TestReadAllBytes() : System.Void`  
- `private TestReadAllBytesOnLargeFile() : System.Void`  
- `private TestReadAllLines() : System.Void`  
- `private TestReadAllText() : System.Void`  
- `private TestReadAllTextEncoding() : System.Void`  
- `private TestReadAllTextNewFile() : System.Void`  
- `private TestReadAllTextNullPath() : System.Void`  
- `private TestSetAccessControl() : System.Void`  
- `private TestWriteAllBytes() : System.Void`  
- `private TestWriteAllLines() : System.Void`  
- `private TestWriteAllLinesWithEncoding() : System.Void`  
- `private TestWriteAllText() : System.Void`  
- `private TestWriteAllTextEncoding() : System.Void`  
- `private TestWriteAllTextNullPath() : System.Void`  

## Nested types

- `Game.Debug.Tests.LongFileTestScenario+Utils`  
- `Game.Debug.Tests.LongFileTestScenario+<>c`  
- `Game.Debug.Tests.LongFileTestScenario+<>c__DisplayClass24_0`  
- `Game.Debug.Tests.LongFileTestScenario+<>c__DisplayClass32_0`  
- `Game.Debug.Tests.LongFileTestScenario+<>c__DisplayClass33_0`  
- `Game.Debug.Tests.LongFileTestScenario+<>c__DisplayClass38_0`  

