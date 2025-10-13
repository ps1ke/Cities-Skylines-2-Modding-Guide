# PDX.SDK.Contracts.Util.IChunkHandler

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Util`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IChunkHandler
{
    public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get; set; }
    public System.Int32 BufferSize { get; }
    public System.IO.Stream Stream { get; }
    public System.String FileAbsolutePath { get; }
    public System.Exception Error { get; }

    public abstract System.Void Done();
    public abstract System.Boolean HandleBytes(System.Byte[] chunk, System.Int32 size);
    public abstract System.Void Initialize();
}
```


## Properties

- `public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get; set }`  

```csharp
public PDX.SDK.Contracts.Network.ITransferStatus TransferStatus { get; set; }
```

- `public System.Int32 BufferSize { get }`  

```csharp
public System.Int32 BufferSize { get; }
```

- `public System.IO.Stream Stream { get }`  

```csharp
public System.IO.Stream Stream { get; }
```

- `public System.String FileAbsolutePath { get }`  

```csharp
public System.String FileAbsolutePath { get; }
```

- `public System.Exception Error { get }`  

```csharp
public System.Exception Error { get; }
```


## Methods

- `public abstract Done() : System.Void`  

```csharp
public abstract System.Void Done();
```

- `public abstract HandleBytes(System.Byte[] chunk, System.Int32 size) : System.Boolean`  

```csharp
public abstract System.Boolean HandleBytes(System.Byte[] chunk, System.Int32 size);
```

- `public abstract Initialize() : System.Void`  

```csharp
public abstract System.Void Initialize();
```


