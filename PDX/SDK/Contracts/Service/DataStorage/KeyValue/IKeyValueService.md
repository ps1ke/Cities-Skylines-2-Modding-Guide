# PDX.SDK.Contracts.Service.DataStorage.KeyValue.IKeyValueService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.DataStorage.KeyValue`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IKeyValueService
{
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry entry);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry> entries);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.Collections.Generic.IEnumerable<System.String> keys);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.String[] keys);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.String key);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> DeleteAll();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult> Get(System.Collections.Generic.IEnumerable<System.String> keys);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult> Get(System.String[] keys);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetResult> Get(System.String key);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult> GetAll();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Set(System.Collections.Generic.Dictionary<System.String, System.String> keyValuePairs);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Set(PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry entry);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Set(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry> entries);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Set(System.String key, System.String value);
}
```


## Methods

- `public abstract Delete(PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry entry) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry entry);
```

- `public abstract Delete(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry> entries) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry> entries);
```

- `public abstract Delete(System.Collections.Generic.IEnumerable<System.String> keys) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.Collections.Generic.IEnumerable<System.String> keys);
```

- `public abstract Delete(System.String[] keys) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.String[] keys);
```

- `public abstract Delete(System.String key) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Delete(System.String key);
```

- `public abstract DeleteAll() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> DeleteAll();
```

- `public abstract Get(System.Collections.Generic.IEnumerable<System.String> keys) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult> Get(System.Collections.Generic.IEnumerable<System.String> keys);
```

- `public abstract Get(System.String[] keys) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult> Get(System.String[] keys);
```

- `public abstract Get(System.String key) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetResult> Get(System.String key);
```

- `public abstract GetAll() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Result.GetAllResult> GetAll();
```

- `public abstract Set(System.Collections.Generic.Dictionary<System.String, System.String> keyValuePairs) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Set(System.Collections.Generic.Dictionary<System.String, System.String> keyValuePairs);
```

- `public abstract Set(PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry entry) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Set(PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry entry);
```

- `public abstract Set(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry> entries) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Set(System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry> entries);
```

- `public abstract Set(System.String key, System.String value) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Set(System.String key, System.String value);
```


