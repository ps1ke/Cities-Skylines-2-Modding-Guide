# Colossal.PSI.Common.IRemoteStorageSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IRemoteStorageSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public System.Boolean isExternallyControlled { get; }

    public abstract System.Boolean Delete(System.String containerName, System.String fileName);
    public abstract System.Boolean Exists(System.String containerName, System.String fileName);
    public abstract System.ValueTuple<System.Int64, System.Int64> GetQuota();
    public abstract System.Boolean IsCloudSupported();
    public abstract System.Int32 Read(System.String containerName, System.String fileName, System.Byte[]& data);
    public abstract System.Void Wipe();
    public abstract System.Boolean Write(System.String containerName, System.String fileName, System.Byte[] data);
}
```


## Properties

- `public System.Boolean isExternallyControlled { get }`  

```csharp
public System.Boolean isExternallyControlled { get; }
```


## Methods

- `public abstract Delete(System.String containerName, System.String fileName) : System.Boolean`  

```csharp
public abstract System.Boolean Delete(System.String containerName, System.String fileName);
```

- `public abstract Exists(System.String containerName, System.String fileName) : System.Boolean`  

```csharp
public abstract System.Boolean Exists(System.String containerName, System.String fileName);
```

- `public abstract GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  

```csharp
public abstract System.ValueTuple<System.Int64, System.Int64> GetQuota();
```

- `public abstract IsCloudSupported() : System.Boolean`  

```csharp
public abstract System.Boolean IsCloudSupported();
```

- `public abstract Read(System.String containerName, System.String fileName, System.Byte[]& data) : System.Int32`  

```csharp
public abstract System.Int32 Read(System.String containerName, System.String fileName, System.Byte[]& data);
```

- `public abstract Wipe() : System.Void`  

```csharp
public abstract System.Void Wipe();
```

- `public abstract Write(System.String containerName, System.String fileName, System.Byte[] data) : System.Boolean`  

```csharp
public abstract System.Boolean Write(System.String containerName, System.String fileName, System.Byte[] data);
```


