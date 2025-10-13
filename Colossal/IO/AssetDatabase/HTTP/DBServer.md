# Colossal.IO.AssetDatabase.HTTP.DBServer

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.HTTP`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.HTTP.HTTPServer`  

## Code

```csharp
public class DBServer : Colossal.IO.AssetDatabase.HTTP.HTTPServer
{
    private Colossal.IO.AssetDatabase.IAssetDatabase m_Database;
    private static readonly System.Collections.Generic.IDictionary<System.String, System.String> s_MimeTypeMappings;

    public DBServer(Colossal.IO.AssetDatabase.IAssetDatabase db);
    public DBServer(System.Int32 port, Colossal.IO.AssetDatabase.IAssetDatabase db);

    public virtual System.Void OnResponse(Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct& rq, Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct& rp);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.IAssetDatabase m_Database`  

```csharp
private Colossal.IO.AssetDatabase.IAssetDatabase m_Database;
```

- `private static readonly System.Collections.Generic.IDictionary<System.String, System.String> s_MimeTypeMappings`  

```csharp
private static readonly System.Collections.Generic.IDictionary<System.String, System.String> s_MimeTypeMappings;
```


## Constructors

- `public DBServer(Colossal.IO.AssetDatabase.IAssetDatabase db)`  

```csharp
public DBServer(Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `public DBServer(System.Int32 port, Colossal.IO.AssetDatabase.IAssetDatabase db)`  

```csharp
public DBServer(System.Int32 port, Colossal.IO.AssetDatabase.IAssetDatabase db);
```


## Methods

- `public virtual OnResponse(Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct& rq, Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct& rp) : System.Void`  

```csharp
public virtual System.Void OnResponse(Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct& rq, Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct& rp);
```


