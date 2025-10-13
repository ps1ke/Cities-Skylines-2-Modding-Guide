# PDX.ModsUI.UITypes.SearchModsRequest

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `PDX.ModsUI.UITypes.Request`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class SearchModsRequest : PDX.ModsUI.UITypes.Request
{
    public System.String SearchQuery;
    public System.String Text;
    public System.Int32 Page;
    public System.Int32 PageSize;
    public System.Collections.Generic.List<System.String> Tags;
    public System.String SortBy;
    public System.String OrderBy;
    public System.String Author;
    public System.Boolean OnlyModsByMe;
    public System.String Time;

    public SearchModsRequest();

}
```


## Fields

- `public System.String SearchQuery`  

```csharp
public System.String SearchQuery;
```

- `public System.String Text`  

```csharp
public System.String Text;
```

- `public System.Int32 Page`  

```csharp
public System.Int32 Page;
```

- `public System.Int32 PageSize`  

```csharp
public System.Int32 PageSize;
```

- `public System.Collections.Generic.List<System.String> Tags`  

```csharp
public System.Collections.Generic.List<System.String> Tags;
```

- `public System.String SortBy`  

```csharp
public System.String SortBy;
```

- `public System.String OrderBy`  

```csharp
public System.String OrderBy;
```

- `public System.String Author`  

```csharp
public System.String Author;
```

- `public System.Boolean OnlyModsByMe`  

```csharp
public System.Boolean OnlyModsByMe;
```

- `public System.String Time`  

```csharp
public System.String Time;
```


## Constructors

- `public SearchModsRequest()`  

```csharp
public SearchModsRequest();
```


