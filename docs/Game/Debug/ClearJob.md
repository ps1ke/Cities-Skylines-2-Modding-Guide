# Game.Debug.DebugWatchDistribution+ClearJob

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

## Code

```csharp
public sealed struct ClearJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeQueue<System.Int32> m_RawData;

    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeQueue<System.Int32> m_RawData`  

```csharp
public Unity.Collections.NativeQueue<System.Int32> m_RawData;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


