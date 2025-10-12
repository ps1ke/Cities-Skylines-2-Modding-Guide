# Colossal.UI.CoLogHandler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.LogHandler`  
**Implements:** `cohtml.Net.ILogHandler`, `System.IDisposable`  

## Fields

- `private static Colossal.Logging.ILog m_Log`  
- `private static Colossal.UI.CoLogHandler s_Instance`  
- `private static System.Text.RegularExpressions.Regex s_FontWeightRegex`  

## Properties

- `public static Colossal.UI.CoLogHandler Instance { get }`  

## Constructors

- `public CoLogHandler()`  

## Methods

- `public virtual Dispose() : System.Void`  
- `private LessenSeverity(cohtml.Net.Severity severity, System.String message) : cohtml.Net.Severity`  
- `private MuteMessage(System.String message) : System.Boolean`  
- `public virtual WriteLog(cohtml.Net.Severity severity, System.String message, System.UInt64 length) : System.Void`  

