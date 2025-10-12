# Colossal.ProcessWrapper

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Object m_LockObject`  
- `private System.Diagnostics.Process m_AttachedProcess`  
- `private System.Threading.Thread m_StdoutThread`  
- `private System.Threading.Thread m_StderrThread`  
- `private System.Text.StringBuilder m_Streambuffer`  
- `private Colossal.ProcessWrapper+StringReadEventHandler m_EventStdoutTextRead`  
- `private Colossal.ProcessWrapper+StringReadEventHandler m_EventStderrTextRead`  
- `private Colossal.ProcessWrapper+StringReadEventHandler m_EventReactForInput`  

## Properties

- `public System.Boolean hasExited { get }`  

## Constructors

- `public ProcessWrapper()`  

## Methods

- `private CheckForValidProcess(System.String errorMessageText, System.Boolean checkForHasExited) : System.Void`  
- `private NotifyAndFlushBufferText(System.Text.StringBuilder textbuffer, System.Boolean isStdout) : System.Void`  
- `private ProcessdExited(System.Object sender, System.EventArgs e) : System.Void`  
- `private ReadStandardErrorThreadMethod() : System.Void`  
- `private ReadStandardOutputThreadMethod() : System.Void`  
- `private ReadStream(System.IO.StreamReader streamReader, System.Boolean isStdout) : System.Void`  
- `public Start(System.String command, Colossal.ProcessWrapper+StringReadEventHandler eventStdoutTextRead, Colossal.ProcessWrapper+StringReadEventHandler eventStderrTextRead, Colossal.ProcessWrapper+StringReadEventHandler eventReactForInput) : System.Void`  
- `private StartProcessOutputRead() : System.Void`  
- `public StopMonitoringProcessOutput() : System.Void`  
- `public WriteStdin(System.String text) : System.Void`  

## Nested types

- `Colossal.ProcessWrapper+StringReadEventHandler`  

