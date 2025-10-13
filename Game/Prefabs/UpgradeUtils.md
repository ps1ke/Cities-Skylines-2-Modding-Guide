# Game.Prefabs.UpgradeUtils

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class UpgradeUtils
{
    public static System.Void CombineStats<T>(T& result, Unity.Entities.BufferAccessor<Game.Buildings.InstalledUpgrade> accessor, System.Int32 i, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, ComponentLookup`1& combineDatas);
    public static System.Boolean CombineStats<T>(T& data, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, ComponentLookup`1& combineDatas);
    public static System.Boolean CombineStats<T>(Unity.Entities.EntityManager entityManager, T& data, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades);
    public static System.Void CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, BufferLookup`1& combineDatas);
    public static System.Void CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.Entity prefab, BufferLookup`1& combineDatas);
    public static System.Void CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.DynamicBuffer<T> combineData);
    public static System.Void CombineStats<T>(Unity.Collections.NativeList<T> result, T combineData);
    public static System.Boolean TryCombineData<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& data);
    public static System.Boolean TryGetCombinedComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, T& data);
    public static System.Boolean TryGetCombinedComponent<T>(Unity.Entities.Entity entity, T& data, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, ComponentLookup`1& combineDataLookup, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgradeLookup);
}
```


## Methods

- `public static CombineStats<T>(T& result, Unity.Entities.BufferAccessor<Game.Buildings.InstalledUpgrade> accessor, System.Int32 i, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, ComponentLookup`1& combineDatas) : System.Void`  

```csharp
public static System.Void CombineStats<T>(T& result, Unity.Entities.BufferAccessor<Game.Buildings.InstalledUpgrade> accessor, System.Int32 i, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, ComponentLookup`1& combineDatas);
```

- `public static CombineStats<T>(T& data, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, ComponentLookup`1& combineDatas) : System.Boolean`  

```csharp
public static System.Boolean CombineStats<T>(T& data, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, ComponentLookup`1& combineDatas);
```

- `public static CombineStats<T>(Unity.Entities.EntityManager entityManager, T& data, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades) : System.Boolean`  

```csharp
public static System.Boolean CombineStats<T>(Unity.Entities.EntityManager entityManager, T& data, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades);
```

- `public static CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, BufferLookup`1& combineDatas) : System.Void`  

```csharp
public static System.Void CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, BufferLookup`1& combineDatas);
```

- `public static CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.Entity prefab, BufferLookup`1& combineDatas) : System.Void`  

```csharp
public static System.Void CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.Entity prefab, BufferLookup`1& combineDatas);
```

- `public static CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.DynamicBuffer<T> combineData) : System.Void`  

```csharp
public static System.Void CombineStats<T>(Unity.Collections.NativeList<T> result, Unity.Entities.DynamicBuffer<T> combineData);
```

- `public static CombineStats<T>(Unity.Collections.NativeList<T> result, T combineData) : System.Void`  

```csharp
public static System.Void CombineStats<T>(Unity.Collections.NativeList<T> result, T combineData);
```

- `public static TryCombineData<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& data) : System.Boolean`  

```csharp
public static System.Boolean TryCombineData<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& data);
```

- `public static TryGetCombinedComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, T& data) : System.Boolean`  

```csharp
public static System.Boolean TryGetCombinedComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity prefab, T& data);
```

- `public static TryGetCombinedComponent<T>(Unity.Entities.Entity entity, T& data, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, ComponentLookup`1& combineDataLookup, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgradeLookup) : System.Boolean`  

```csharp
public static System.Boolean TryGetCombinedComponent<T>(Unity.Entities.Entity entity, T& data, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefLookup, ComponentLookup`1& combineDataLookup, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgradeLookup);
```


