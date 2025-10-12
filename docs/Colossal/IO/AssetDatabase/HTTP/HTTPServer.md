# Colossal.IO.AssetDatabase.HTTP.HTTPServer

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.HTTP`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Fields

- `public Colossal.Logging.ILog log`  
- `private System.Net.Sockets.TcpListener m_Listener`  
- `private System.Threading.Thread m_Thread`  
- `private System.Boolean m_ShutdownFlag`  
- `private System.Int32 <port>k__BackingField`  
- `private System.Collections.Hashtable <responseStatus>k__BackingField`  

## Properties

- `public System.Int32 port { get; private set }`  
- `public System.Collections.Hashtable responseStatus { get; private set }`  
- `public System.String name { get }`  
- `public System.Boolean IsAlive { get }`  

## Constructors

- `protected HTTPServer()`  
- `protected HTTPServer(System.Int32 port)`  

## Methods

- `private InitializeResponseStatus() : System.Void`  
- `private Listen() : System.Void`  
- `public abstract OnResponse(Colossal.IO.AssetDatabase.HTTP.HTTPRequestStruct& rq, Colossal.IO.AssetDatabase.HTTP.HTTPResponseStruct& rp) : System.Void`  
- `public Start() : System.Void`  
- `public Stop() : System.Void`  

