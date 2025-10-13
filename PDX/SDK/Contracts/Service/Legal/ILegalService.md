# PDX.SDK.Contracts.Service.Legal.ILegalService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Legal`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ILegalService
{
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult> DownloadDocument(System.String title, System.String type, System.Nullable<PDX.SDK.Contracts.Enums.Language> lang);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult> GetEula(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetAllDocumentResult> GetNotices(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult> GetPrivacy(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.ListUnviewedResult> ListUnviewed();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> MarkAsViewed(PDX.SDK.Contracts.Service.Legal.Models.Document document);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> MarkAsViewed(System.String title, System.String type);
}
```


## Methods

- `public abstract DownloadDocument(System.String title, System.String type, System.Nullable<PDX.SDK.Contracts.Enums.Language> lang = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult> DownloadDocument(System.String title, System.String type, System.Nullable<PDX.SDK.Contracts.Enums.Language> lang);
```

- `public abstract GetEula(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult> GetEula(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang);
```

- `public abstract GetNotices(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetAllDocumentResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetAllDocumentResult> GetNotices(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang);
```

- `public abstract GetPrivacy(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.GetDocumentResult> GetPrivacy(System.Nullable<PDX.SDK.Contracts.Enums.Language> lang);
```

- `public abstract ListUnviewed() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.ListUnviewedResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Legal.Result.ListUnviewedResult> ListUnviewed();
```

- `public abstract MarkAsViewed(PDX.SDK.Contracts.Service.Legal.Models.Document document) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> MarkAsViewed(PDX.SDK.Contracts.Service.Legal.Models.Document document);
```

- `public abstract MarkAsViewed(System.String title, System.String type) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> MarkAsViewed(System.String title, System.String type);
```


