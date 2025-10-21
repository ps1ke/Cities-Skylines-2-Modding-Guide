# Game.Debug.ComponentDebugUtils

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ComponentDebugUtils
{
    public static System.Collections.Generic.List<Game.Debug.ComponentDebugUtils+ComponentInfo> GetCommonComponents(Unity.Entities.EntityManager entityManager, System.String filter, System.Boolean unusedOnly, System.Int32& archetypeCount, System.Int32& filteredArchetypeCount, System.Int32& chunkCount, System.Int32& chunkCapacity, System.Int32& entityCount);
    private static System.Boolean IsMatching(Unity.Entities.ComponentType type, System.String filter);
}
```


## Methods

- `public static GetCommonComponents(Unity.Entities.EntityManager entityManager, System.String filter, System.Boolean unusedOnly, System.Int32& archetypeCount, System.Int32& filteredArchetypeCount, System.Int32& chunkCount, System.Int32& chunkCapacity, System.Int32& entityCount) : System.Collections.Generic.List<Game.Debug.ComponentDebugUtils+ComponentInfo>`  

```csharp
public static System.Collections.Generic.List<Game.Debug.ComponentDebugUtils+ComponentInfo> GetCommonComponents(Unity.Entities.EntityManager entityManager, System.String filter, System.Boolean unusedOnly, System.Int32& archetypeCount, System.Int32& filteredArchetypeCount, System.Int32& chunkCount, System.Int32& chunkCapacity, System.Int32& entityCount);
```

- `private static IsMatching(Unity.Entities.ComponentType type, System.String filter) : System.Boolean`  

```csharp
private static System.Boolean IsMatching(Unity.Entities.ComponentType type, System.String filter);
```


## Nested types

- `Game.Debug.ComponentDebugUtils+ComponentInfo`  
- `Game.Debug.ComponentDebugUtils+<>c`  

