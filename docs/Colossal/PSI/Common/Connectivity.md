# Colossal.PSI.Common.Connectivity

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.String[] kHosts`  
- `private static System.Boolean <hasConnectivity>k__BackingField`  
- `private static System.Threading.CancellationTokenSource m_Cts`  
- `private static System.Boolean s_IsRunning`  

## Properties

- `public static System.Boolean hasConnectivity { get; private set }`  

## Methods

- `private static DnsCheck(System.String[] hosts) : System.Threading.Tasks.Task<System.Boolean>`  
- `public static Ping(System.String[] hosts) : System.Threading.Tasks.Task<System.Boolean>`  
- `public static StartConnectivityCheck(System.Int32 interval, System.Action<System.Boolean> callBack) : System.Void`  
- `private static StartConnectivityCheck(System.Int32 interval, System.Action<System.Boolean> callBack, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public static StopConnectivityCheck() : System.Void`  

## Nested types

- `Colossal.PSI.Common.Connectivity+<>c`  
- `Colossal.PSI.Common.Connectivity+<>c__DisplayClass7_0`  
- `Colossal.PSI.Common.Connectivity+<DnsCheck>d__10`  
- `Colossal.PSI.Common.Connectivity+<Ping>d__11`  
- `Colossal.PSI.Common.Connectivity+<StartConnectivityCheck>d__7`  
- `Colossal.PSI.Common.Connectivity+<StartConnectivityCheck>d__9`  

