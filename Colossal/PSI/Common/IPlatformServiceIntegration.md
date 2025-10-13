# Colossal.PSI.Common.IPlatformServiceIntegration

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IPlatformServiceIntegration : Colossal.PSI.Common.IDisposableAsync
{
    public System.String name { get; }
    public System.Boolean isInitialized { get; }

    public abstract System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
    public abstract System.Void LogVersion(System.Text.StringBuilder b);
    public abstract System.Void Update();
}
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean isInitialized { get }`  

```csharp
public System.Boolean isInitialized { get; }
```


## Methods

- `public abstract Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
```

- `public abstract LogVersion(System.Text.StringBuilder b) : System.Void`  

```csharp
public abstract System.Void LogVersion(System.Text.StringBuilder b);
```

- `public abstract Update() : System.Void`  

```csharp
public abstract System.Void Update();
```


## Events

- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```


