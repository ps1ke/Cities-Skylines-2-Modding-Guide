# Colossal.ProcessWrapper

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ProcessWrapper
{
    private System.Object m_LockObject;
    private System.Diagnostics.Process m_AttachedProcess;
    private System.Threading.Thread m_StdoutThread;
    private System.Threading.Thread m_StderrThread;
    private System.Text.StringBuilder m_Streambuffer;
    private Colossal.ProcessWrapper+StringReadEventHandler m_EventStdoutTextRead;
    private Colossal.ProcessWrapper+StringReadEventHandler m_EventStderrTextRead;
    private Colossal.ProcessWrapper+StringReadEventHandler m_EventReactForInput;

    public System.Boolean hasExited { get; }

    public ProcessWrapper();

    private System.Void CheckForValidProcess(System.String errorMessageText, System.Boolean checkForHasExited);
    private System.Void NotifyAndFlushBufferText(System.Text.StringBuilder textbuffer, System.Boolean isStdout);
    private System.Void ProcessdExited(System.Object sender, System.EventArgs e);
    private System.Void ReadStandardErrorThreadMethod();
    private System.Void ReadStandardOutputThreadMethod();
    private System.Void ReadStream(System.IO.StreamReader streamReader, System.Boolean isStdout);
    public System.Void Start(System.String command, Colossal.ProcessWrapper+StringReadEventHandler eventStdoutTextRead, Colossal.ProcessWrapper+StringReadEventHandler eventStderrTextRead, Colossal.ProcessWrapper+StringReadEventHandler eventReactForInput);
    private System.Void StartProcessOutputRead();
    public System.Void StopMonitoringProcessOutput();
    public System.Void WriteStdin(System.String text);
}
```


## Fields

- `private System.Object m_LockObject`  

```csharp
private System.Object m_LockObject;
```

- `private System.Diagnostics.Process m_AttachedProcess`  

```csharp
private System.Diagnostics.Process m_AttachedProcess;
```

- `private System.Threading.Thread m_StdoutThread`  

```csharp
private System.Threading.Thread m_StdoutThread;
```

- `private System.Threading.Thread m_StderrThread`  

```csharp
private System.Threading.Thread m_StderrThread;
```

- `private System.Text.StringBuilder m_Streambuffer`  

```csharp
private System.Text.StringBuilder m_Streambuffer;
```

- `private Colossal.ProcessWrapper+StringReadEventHandler m_EventStdoutTextRead`  

```csharp
private Colossal.ProcessWrapper+StringReadEventHandler m_EventStdoutTextRead;
```

- `private Colossal.ProcessWrapper+StringReadEventHandler m_EventStderrTextRead`  

```csharp
private Colossal.ProcessWrapper+StringReadEventHandler m_EventStderrTextRead;
```

- `private Colossal.ProcessWrapper+StringReadEventHandler m_EventReactForInput`  

```csharp
private Colossal.ProcessWrapper+StringReadEventHandler m_EventReactForInput;
```


## Properties

- `public System.Boolean hasExited { get }`  

```csharp
public System.Boolean hasExited { get; }
```


## Constructors

- `public ProcessWrapper()`  

```csharp
public ProcessWrapper();
```


## Methods

- `private CheckForValidProcess(System.String errorMessageText, System.Boolean checkForHasExited) : System.Void`  

```csharp
private System.Void CheckForValidProcess(System.String errorMessageText, System.Boolean checkForHasExited);
```

- `private NotifyAndFlushBufferText(System.Text.StringBuilder textbuffer, System.Boolean isStdout) : System.Void`  

```csharp
private System.Void NotifyAndFlushBufferText(System.Text.StringBuilder textbuffer, System.Boolean isStdout);
```

- `private ProcessdExited(System.Object sender, System.EventArgs e) : System.Void`  

```csharp
private System.Void ProcessdExited(System.Object sender, System.EventArgs e);
```

- `private ReadStandardErrorThreadMethod() : System.Void`  

```csharp
private System.Void ReadStandardErrorThreadMethod();
```

- `private ReadStandardOutputThreadMethod() : System.Void`  

```csharp
private System.Void ReadStandardOutputThreadMethod();
```

- `private ReadStream(System.IO.StreamReader streamReader, System.Boolean isStdout) : System.Void`  

```csharp
private System.Void ReadStream(System.IO.StreamReader streamReader, System.Boolean isStdout);
```

- `public Start(System.String command, Colossal.ProcessWrapper+StringReadEventHandler eventStdoutTextRead, Colossal.ProcessWrapper+StringReadEventHandler eventStderrTextRead, Colossal.ProcessWrapper+StringReadEventHandler eventReactForInput) : System.Void`  

```csharp
public System.Void Start(System.String command, Colossal.ProcessWrapper+StringReadEventHandler eventStdoutTextRead, Colossal.ProcessWrapper+StringReadEventHandler eventStderrTextRead, Colossal.ProcessWrapper+StringReadEventHandler eventReactForInput);
```

- `private StartProcessOutputRead() : System.Void`  

```csharp
private System.Void StartProcessOutputRead();
```

- `public StopMonitoringProcessOutput() : System.Void`  

```csharp
public System.Void StopMonitoringProcessOutput();
```

- `public WriteStdin(System.String text) : System.Void`  

```csharp
public System.Void WriteStdin(System.String text);
```


## Nested types

- `Colossal.ProcessWrapper+StringReadEventHandler`  

