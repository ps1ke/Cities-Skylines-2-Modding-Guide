# Game.Prefabs.InfoviewMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct InfoviewMode : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Mode;
    public System.Int32 m_Priority;
    public System.Boolean m_Supplemental;
    public System.Boolean m_Optional;

    public InfoviewMode(Unity.Entities.Entity mode, System.Int32 priority, System.Boolean supplemental, System.Boolean optional);

}
```


## Fields

- `public Unity.Entities.Entity m_Mode`  

```csharp
public Unity.Entities.Entity m_Mode;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Boolean m_Supplemental`  

```csharp
public System.Boolean m_Supplemental;
```

- `public System.Boolean m_Optional`  

```csharp
public System.Boolean m_Optional;
```


## Constructors

- `public InfoviewMode(Unity.Entities.Entity mode, System.Int32 priority, System.Boolean supplemental, System.Boolean optional)`  

```csharp
public InfoviewMode(Unity.Entities.Entity mode, System.Int32 priority, System.Boolean supplemental, System.Boolean optional);
```


