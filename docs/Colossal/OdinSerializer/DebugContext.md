# Colossal.OdinSerializer.DebugContext

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Object LOCK`  
- `private Colossal.OdinSerializer.ILogger logger`  
- `private Colossal.OdinSerializer.LoggingPolicy loggingPolicy`  
- `private Colossal.OdinSerializer.ErrorHandlingPolicy errorHandlingPolicy`  

## Properties

- `public Colossal.OdinSerializer.ILogger Logger { get; set }`  
- `public Colossal.OdinSerializer.LoggingPolicy LoggingPolicy { get; set }`  
- `public Colossal.OdinSerializer.ErrorHandlingPolicy ErrorHandlingPolicy { get; set }`  

## Constructors

- `public DebugContext()`  

## Methods

- `public LogError(System.String message) : System.Void`  
- `public LogException(System.Exception exception) : System.Void`  
- `public LogWarning(System.String message) : System.Void`  
- `public ResetToDefault() : System.Void`  

