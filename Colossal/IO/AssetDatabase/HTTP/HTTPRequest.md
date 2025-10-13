# Colossal.IO.AssetDatabase.HTTP.HTTPRequest

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.HTTP`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class HTTPRequest
{
    private readonly System.Net.Sockets.TcpClient m_TcpClient;
    private Colossal.IO.AssetDatabase.HTTP.RequestState m_ParserState;
    private Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct m_HttpRequest;
    private Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct m_HttpResponse;
    private System.Byte[] m_ReadBuffer;
    private Colossal.IO.AssetDatabase.HTTP.HTTPServer m_Owner;

    public HTTPRequest(System.Net.Sockets.TcpClient client, Colossal.IO.AssetDatabase.HTTP.HTTPServer owner);

    public System.Void Process();
}
```


## Fields

- `private readonly System.Net.Sockets.TcpClient m_TcpClient`  

```csharp
private readonly System.Net.Sockets.TcpClient m_TcpClient;
```

- `private Colossal.IO.AssetDatabase.HTTP.RequestState m_ParserState`  

```csharp
private Colossal.IO.AssetDatabase.HTTP.RequestState m_ParserState;
```

- `private Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct m_HttpRequest`  

```csharp
private Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct m_HttpRequest;
```

- `private Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct m_HttpResponse`  

```csharp
private Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct m_HttpResponse;
```

- `private System.Byte[] m_ReadBuffer`  

```csharp
private System.Byte[] m_ReadBuffer;
```

- `private Colossal.IO.AssetDatabase.HTTP.HTTPServer m_Owner`  

```csharp
private Colossal.IO.AssetDatabase.HTTP.HTTPServer m_Owner;
```


## Constructors

- `public HTTPRequest(System.Net.Sockets.TcpClient client, Colossal.IO.AssetDatabase.HTTP.HTTPServer owner)`  

```csharp
public HTTPRequest(System.Net.Sockets.TcpClient client, Colossal.IO.AssetDatabase.HTTP.HTTPServer owner);
```


## Methods

- `public Process() : System.Void`  

```csharp
public System.Void Process();
```


