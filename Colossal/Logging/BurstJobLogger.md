# Colossal.Logging.BurstJobLogger

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class BurstJobLogger
{
    public static readonly Unity.Burst.SharedStatic<Colossal.Logging.BurstJobLogger+LogFilter> ActiveLogFilter;
    public static readonly Unity.Burst.SharedStatic<System.Int32> ActiveEntity1Filter;
    public static readonly Unity.Burst.SharedStatic<System.Int32> ActiveEntity2Filter;

    public BurstJobLogger();

    public static System.Void Log(Unity.Collections.FixedString512Bytes content, Colossal.Logging.BurstJobLogger+LogFilter logFilter);
    public static System.Void LogEntity(System.Int32 entityIndex, Unity.Collections.FixedString512Bytes content, Colossal.Logging.BurstJobLogger+LogFilter logFilter);
}
```


## Fields

- `public static readonly Unity.Burst.SharedStatic<Colossal.Logging.BurstJobLogger+LogFilter> ActiveLogFilter`  

```csharp
public static readonly Unity.Burst.SharedStatic<Colossal.Logging.BurstJobLogger+LogFilter> ActiveLogFilter;
```

- `public static readonly Unity.Burst.SharedStatic<System.Int32> ActiveEntity1Filter`  

```csharp
public static readonly Unity.Burst.SharedStatic<System.Int32> ActiveEntity1Filter;
```

- `public static readonly Unity.Burst.SharedStatic<System.Int32> ActiveEntity2Filter`  

```csharp
public static readonly Unity.Burst.SharedStatic<System.Int32> ActiveEntity2Filter;
```


## Constructors

- `public BurstJobLogger()`  

```csharp
public BurstJobLogger();
```


## Methods

- `public static Log(Unity.Collections.FixedString512Bytes content, Colossal.Logging.BurstJobLogger+LogFilter logFilter = None) : System.Void`  

```csharp
public static System.Void Log(Unity.Collections.FixedString512Bytes content, Colossal.Logging.BurstJobLogger+LogFilter logFilter);
```

- `public static LogEntity(System.Int32 entityIndex, Unity.Collections.FixedString512Bytes content, Colossal.Logging.BurstJobLogger+LogFilter logFilter = None) : System.Void`  

```csharp
public static System.Void LogEntity(System.Int32 entityIndex, Unity.Collections.FixedString512Bytes content, Colossal.Logging.BurstJobLogger+LogFilter logFilter);
```


## Nested types

- `Colossal.Logging.BurstJobLogger+LogFilter`  

