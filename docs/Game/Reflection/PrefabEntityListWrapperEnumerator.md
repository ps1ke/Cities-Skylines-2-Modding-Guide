# Game.Reflection.PrefabEntityListWrapper`1+PrefabEntityListWrapperEnumerator

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerator<T>`, `System.IDisposable`, `System.Collections.IEnumerator`  

## Fields

- `private System.Int32 m_Index`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_Entities`  

## Properties

- `public T Current { get }`  
- `private System.Object System.Collections.IEnumerator.Current { private get }`  

## Constructors

- `public PrefabEntityListWrapperEnumerator(Unity.Collections.NativeList<Unity.Entities.Entity> entities, Game.Prefabs.PrefabSystem prefabSystem)`  

## Methods

- `public Dispose() : System.Void`  
- `public MoveNext() : System.Boolean`  
- `public Reset() : System.Void`  

