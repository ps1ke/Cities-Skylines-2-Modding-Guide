# Game.Simulation.XPMessage

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct XPMessage
{
    private System.UInt32 <createdSimFrame>k__BackingField;
    private Game.Simulation.XPReason <reason>k__BackingField;
    private System.Int32 <amount>k__BackingField;

    public System.UInt32 createdSimFrame { get; private set; }
    public Game.Simulation.XPReason reason { get; private set; }
    public System.Int32 amount { get; private set; }

    public XPMessage(System.UInt32 createdSimFrame, System.Int32 amount, Game.Simulation.XPReason reason);

}
```


## Fields

- `private System.UInt32 <createdSimFrame>k__BackingField`  

```csharp
private System.UInt32 <createdSimFrame>k__BackingField;
```

- `private Game.Simulation.XPReason <reason>k__BackingField`  

```csharp
private Game.Simulation.XPReason <reason>k__BackingField;
```

- `private System.Int32 <amount>k__BackingField`  

```csharp
private System.Int32 <amount>k__BackingField;
```


## Properties

- `public System.UInt32 createdSimFrame { get; private set }`  

```csharp
public System.UInt32 createdSimFrame { get; private set; }
```

- `public Game.Simulation.XPReason reason { get; private set }`  

```csharp
public Game.Simulation.XPReason reason { get; private set; }
```

- `public System.Int32 amount { get; private set }`  

```csharp
public System.Int32 amount { get; private set; }
```


## Constructors

- `public XPMessage(System.UInt32 createdSimFrame, System.Int32 amount, Game.Simulation.XPReason reason)`  

```csharp
public XPMessage(System.UInt32 createdSimFrame, System.Int32 amount, Game.Simulation.XPReason reason);
```


