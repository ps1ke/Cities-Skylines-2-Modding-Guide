# Colossal.PSI.Common.PSIExtensions

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class PSIExtensions
{
    private static System.Boolean s_IsQuitting;

    private static System.Boolean needsUpdate { private get; }

    public static System.Threading.Tasks.Task WaitWithDispatchAsync(System.Threading.Tasks.Task task, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task WaitWithDispatchAsync(System.Threading.Tasks.Task task, Colossal.PSI.Common.IPlatformServiceIntegration psi);
}
```


## Fields

- `private static System.Boolean s_IsQuitting`  

```csharp
private static System.Boolean s_IsQuitting;
```


## Properties

- `private static System.Boolean needsUpdate { private get }`  

```csharp
private static System.Boolean needsUpdate { private get; }
```


## Methods

- `public static WaitWithDispatchAsync(System.Threading.Tasks.Task task, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task WaitWithDispatchAsync(System.Threading.Tasks.Task task, Colossal.PSI.Common.IPlatformServiceIntegration psi, System.Threading.CancellationToken token);
```

- `public static WaitWithDispatchAsync(System.Threading.Tasks.Task task, Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task WaitWithDispatchAsync(System.Threading.Tasks.Task task, Colossal.PSI.Common.IPlatformServiceIntegration psi);
```


## Nested types

- `Colossal.PSI.Common.PSIExtensions+<>c`  
- `Colossal.PSI.Common.PSIExtensions+<WaitWithDispatchAsync>d__4`  
- `Colossal.PSI.Common.PSIExtensions+<WaitWithDispatchAsync>d__5`  

