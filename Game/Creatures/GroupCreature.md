# Game.Creatures.GroupCreature

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct GroupCreature : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Creature;

    public GroupCreature(Unity.Entities.Entity creature);

}
```


## Fields

- `public Unity.Entities.Entity m_Creature`  

```csharp
public Unity.Entities.Entity m_Creature;
```


## Constructors

- `public GroupCreature(Unity.Entities.Entity creature)`  

```csharp
public GroupCreature(Unity.Entities.Entity creature);
```


