# PDX.SDK.Internal.Util.FileLocks

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Util`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class FileLocks
{
    private static System.Object AccessList;
    private static System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Util.AsyncReaderWriterLock> FileLockList;

    public FileLocks();

    public PDX.SDK.Internal.Util.AsyncReaderWriterLock FetchLock(System.String absolutePath);
}
```


## Fields

- `private static System.Object AccessList`  

```csharp
private static System.Object AccessList;
```

- `private static System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Util.AsyncReaderWriterLock> FileLockList`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Util.AsyncReaderWriterLock> FileLockList;
```


## Constructors

- `public FileLocks()`  

```csharp
public FileLocks();
```


## Methods

- `public FetchLock(System.String absolutePath) : PDX.SDK.Internal.Util.AsyncReaderWriterLock`  

```csharp
public PDX.SDK.Internal.Util.AsyncReaderWriterLock FetchLock(System.String absolutePath);
```


