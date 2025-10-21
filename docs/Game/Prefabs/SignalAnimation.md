# Game.Prefabs.SignalAnimation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SignalAnimation
{
    private Unity.Collections.FixedList128Bytes<Game.Prefabs.SignalGroupMask> m_Buffer;
    private System.Single m_LengthFactor;

    public SignalAnimation(Game.Prefabs.SignalGroupMask[] masks);

    public System.Single Evaluate(Game.Prefabs.SignalGroupMask signalGroupMask, System.Single time);
}
```


## Fields

- `private Unity.Collections.FixedList128Bytes<Game.Prefabs.SignalGroupMask> m_Buffer`  

```csharp
private Unity.Collections.FixedList128Bytes<Game.Prefabs.SignalGroupMask> m_Buffer;
```

- `private System.Single m_LengthFactor`  

```csharp
private System.Single m_LengthFactor;
```


## Constructors

- `public SignalAnimation(Game.Prefabs.SignalGroupMask[] masks)`  

```csharp
public SignalAnimation(Game.Prefabs.SignalGroupMask[] masks);
```


## Methods

- `public Evaluate(Game.Prefabs.SignalGroupMask signalGroupMask, System.Single time) : System.Single`  

```csharp
public System.Single Evaluate(Game.Prefabs.SignalGroupMask signalGroupMask, System.Single time);
```


