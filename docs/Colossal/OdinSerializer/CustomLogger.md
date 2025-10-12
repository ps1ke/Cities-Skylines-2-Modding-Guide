# Colossal.OdinSerializer.CustomLogger

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.ILogger`  

## Fields

- `private System.Action<System.String> logWarningDelegate`  
- `private System.Action<System.String> logErrorDelegate`  
- `private System.Action<System.Exception> logExceptionDelegate`  

## Constructors

- `public CustomLogger(System.Action<System.String> logWarningDelegate, System.Action<System.String> logErrorDelegate, System.Action<System.Exception> logExceptionDelegate)`  

## Methods

- `public LogError(System.String error) : System.Void`  
- `public LogException(System.Exception exception) : System.Void`  
- `public LogWarning(System.String warning) : System.Void`  

