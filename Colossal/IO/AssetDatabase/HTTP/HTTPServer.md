# Colossal.IO.AssetDatabase.HTTP.HTTPServer

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.HTTP`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class HTTPServer
{
    public Colossal.Logging.ILog log;
    private System.Net.Sockets.TcpListener m_Listener;
    private System.Threading.Thread m_Thread;
    private System.Boolean m_ShutdownFlag;
    private System.Int32 <port>k__BackingField;
    private System.Collections.Hashtable <responseStatus>k__BackingField;

    public System.Int32 port { get; private set; }
    public System.Collections.Hashtable responseStatus { get; private set; }
    public System.String name { get; }
    public System.Boolean IsAlive { get; }

    protected HTTPServer();
    protected HTTPServer(System.Int32 port);

    private System.Void InitializeResponseStatus();
    private System.Void Listen();
    public abstract System.Void OnResponse(Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct& rq, Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct& rp);
    public System.Void Start();
    public System.Void Stop();
}
```


## Fields

- `public Colossal.Logging.ILog log`  

```csharp
public Colossal.Logging.ILog log;
```

- `private System.Net.Sockets.TcpListener m_Listener`  

```csharp
private System.Net.Sockets.TcpListener m_Listener;
```

- `private System.Threading.Thread m_Thread`  

```csharp
private System.Threading.Thread m_Thread;
```

- `private System.Boolean m_ShutdownFlag`  

```csharp
private System.Boolean m_ShutdownFlag;
```

- `private System.Int32 <port>k__BackingField`  

```csharp
private System.Int32 <port>k__BackingField;
```

- `private System.Collections.Hashtable <responseStatus>k__BackingField`  

```csharp
private System.Collections.Hashtable <responseStatus>k__BackingField;
```


## Properties

- `public System.Int32 port { get; private set }`  

```csharp
public System.Int32 port { get; private set; }
```

- `public System.Collections.Hashtable responseStatus { get; private set }`  

```csharp
public System.Collections.Hashtable responseStatus { get; private set; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean IsAlive { get }`  

```csharp
public System.Boolean IsAlive { get; }
```


## Constructors

- `protected HTTPServer()`  

```csharp
protected HTTPServer();
```

- `protected HTTPServer(System.Int32 port)`  

```csharp
protected HTTPServer(System.Int32 port);
```


## Methods

- `private InitializeResponseStatus() : System.Void`  

```csharp
private System.Void InitializeResponseStatus();
```

- `private Listen() : System.Void`  

```csharp
private System.Void Listen();
```

- `public abstract OnResponse(Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct& rq, Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct& rp) : System.Void`  

```csharp
public abstract System.Void OnResponse(Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct& rq, Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct& rp);
```

- `public Start() : System.Void`  

```csharp
public System.Void Start();
```

- `public Stop() : System.Void`  

```csharp
public System.Void Stop();
```


