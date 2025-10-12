# Colossal.PSI.Common.IRemoteStorageSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Properties

- `public System.Boolean isExternallyControlled { get }`  

## Methods

- `public abstract Delete(System.String containerName, System.String fileName) : System.Boolean`  
- `public abstract Exists(System.String containerName, System.String fileName) : System.Boolean`  
- `public abstract GetQuota() : System.ValueTuple<System.Int64, System.Int64>`  
- `public abstract IsCloudSupported() : System.Boolean`  
- `public abstract Read(System.String containerName, System.String fileName, System.Byte[]& data) : System.Int32`  
- `public abstract Wipe() : System.Void`  
- `public abstract Write(System.String containerName, System.String fileName, System.Byte[] data) : System.Boolean`  

