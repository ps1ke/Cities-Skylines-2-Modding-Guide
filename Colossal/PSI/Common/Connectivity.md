# Colossal.PSI.Common.Connectivity

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class Connectivity
{
    private static readonly System.String[] kHosts;
    private static System.Boolean <hasConnectivity>k__BackingField;
    private static System.Threading.CancellationTokenSource m_Cts;
    private static System.Boolean s_IsRunning;

    public static System.Boolean hasConnectivity { get; private set; }

    private static System.Threading.Tasks.Task<System.Boolean> DnsCheck(System.String[] hosts);
    public static System.Threading.Tasks.Task<System.Boolean> Ping(System.String[] hosts);
    public static System.Void StartConnectivityCheck(System.Int32 interval, System.Action<System.Boolean> callBack);
    private static System.Threading.Tasks.Task StartConnectivityCheck(System.Int32 interval, System.Action<System.Boolean> callBack, System.Threading.CancellationToken token);
    public static System.Void StopConnectivityCheck();
}
```


## Fields

- `private static readonly System.String[] kHosts`  

```csharp
private static readonly System.String[] kHosts;
```

- `private static System.Boolean <hasConnectivity>k__BackingField`  

```csharp
private static System.Boolean <hasConnectivity>k__BackingField;
```

- `private static System.Threading.CancellationTokenSource m_Cts`  

```csharp
private static System.Threading.CancellationTokenSource m_Cts;
```

- `private static System.Boolean s_IsRunning`  

```csharp
private static System.Boolean s_IsRunning;
```


## Properties

- `public static System.Boolean hasConnectivity { get; private set }`  

```csharp
public static System.Boolean hasConnectivity { get; private set; }
```


## Methods

- `private static DnsCheck(System.String[] hosts) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private static System.Threading.Tasks.Task<System.Boolean> DnsCheck(System.String[] hosts);
```

- `public static Ping(System.String[] hosts) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public static System.Threading.Tasks.Task<System.Boolean> Ping(System.String[] hosts);
```

- `public static StartConnectivityCheck(System.Int32 interval, System.Action<System.Boolean> callBack) : System.Void`  

```csharp
public static System.Void StartConnectivityCheck(System.Int32 interval, System.Action<System.Boolean> callBack);
```

- `private static StartConnectivityCheck(System.Int32 interval, System.Action<System.Boolean> callBack, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private static System.Threading.Tasks.Task StartConnectivityCheck(System.Int32 interval, System.Action<System.Boolean> callBack, System.Threading.CancellationToken token);
```

- `public static StopConnectivityCheck() : System.Void`  

```csharp
public static System.Void StopConnectivityCheck();
```


## Nested types

- `Colossal.PSI.Common.Connectivity+<>c`  
- `Colossal.PSI.Common.Connectivity+<>c__DisplayClass7_0`  
- `Colossal.PSI.Common.Connectivity+<DnsCheck>d__10`  
- `Colossal.PSI.Common.Connectivity+<Ping>d__11`  
- `Colossal.PSI.Common.Connectivity+<StartConnectivityCheck>d__7`  
- `Colossal.PSI.Common.Connectivity+<StartConnectivityCheck>d__9`  

