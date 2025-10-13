# PDX.SDK.Contracts.Service.DataStorage.IDataStorageService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.DataStorage`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IDataStorageService
{
    public PDX.SDK.Contracts.Service.DataStorage.CloudSave.ICloudSaveService CloudSave { get; set; }
    public PDX.SDK.Contracts.Service.DataStorage.KeyValue.IKeyValueService KeyValue { get; set; }

}
```


## Properties

- `public PDX.SDK.Contracts.Service.DataStorage.CloudSave.ICloudSaveService CloudSave { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.DataStorage.CloudSave.ICloudSaveService CloudSave { get; set; }
```

- `public PDX.SDK.Contracts.Service.DataStorage.KeyValue.IKeyValueService KeyValue { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.DataStorage.KeyValue.IKeyValueService KeyValue { get; set; }
```


