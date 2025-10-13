# PDX.SDK.Contracts.Service.DataStorage.CloudSave.ICloudSaveService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.DataStorage.CloudSave`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ICloudSaveService
{
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry entry);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry> entries);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.String[] remotePaths);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.String remotePath);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.DownloadResult> Download(System.String remotePath, System.String relativePath, System.String etag);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.ListEntriesResult> ListEntries();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.UploadResult> Upload(System.String relativePath, System.String remotePath, System.Boolean public);
}
```


## Methods

- `public abstract Delete(PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry entry) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry entry);
```

- `public abstract Delete(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry> entries) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Models.Entry> entries);
```

- `public abstract Delete(System.String[] remotePaths) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.String[] remotePaths);
```

- `public abstract Delete(System.String remotePath) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.String remotePath);
```

- `public abstract Download(System.String remotePath, System.String relativePath, System.String etag = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.DownloadResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.DownloadResult> Download(System.String remotePath, System.String relativePath, System.String etag);
```

- `public abstract ListEntries() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.ListEntriesResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.ListEntriesResult> ListEntries();
```

- `public abstract Upload(System.String relativePath, System.String remotePath, System.Boolean public = False) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.UploadResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.CloudSave.Result.UploadResult> Upload(System.String relativePath, System.String remotePath, System.Boolean public);
```


