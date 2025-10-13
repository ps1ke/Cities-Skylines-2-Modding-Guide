# PDX.ModsUI.UITypes.GetForumPostsRequest

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `PDX.ModsUI.UITypes.Request`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class GetForumPostsRequest : PDX.ModsUI.UITypes.Request
{
    public System.Int32 ModId;
    public System.Int32 ThreadId;
    public System.String ModVersion;
    public System.Int32 Page;
    public System.Int32 Limit;

    public GetForumPostsRequest();

}
```


## Fields

- `public System.Int32 ModId`  

```csharp
public System.Int32 ModId;
```

- `public System.Int32 ThreadId`  

```csharp
public System.Int32 ThreadId;
```

- `public System.String ModVersion`  

```csharp
public System.String ModVersion;
```

- `public System.Int32 Page`  

```csharp
public System.Int32 Page;
```

- `public System.Int32 Limit`  

```csharp
public System.Int32 Limit;
```


## Constructors

- `public GetForumPostsRequest()`  

```csharp
public GetForumPostsRequest();
```


