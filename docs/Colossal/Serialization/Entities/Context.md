# Colossal.Serialization.Entities.Context

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Colossal.Version <version>k__BackingField`  
- `private Colossal.Serialization.Entities.Purpose <purpose>k__BackingField`  
- `private Colossal.Hash128 <instigatorGuid>k__BackingField`  
- `internal Colossal.Serialization.Entities.ContextFormat m_Format`  

## Properties

- `public Colossal.Version version { get; internal set }`  
- `public Colossal.Serialization.Entities.Purpose purpose { get; private set }`  
- `public Colossal.Hash128 instigatorGuid { get; private set }`  
- `public Colossal.Serialization.Entities.ContextFormat format { get }`  

## Constructors

- `public Context(Colossal.Serialization.Entities.Purpose purpose, Colossal.Version version, Colossal.Hash128 instigatorGuid)`  
- `public Context(Colossal.Serialization.Entities.Purpose purpose, Colossal.Version version, Colossal.Hash128 instigatorGuid, System.Int32 formatTagCount, Unity.Collections.Allocator allocator)`  

## Methods

- `public Dispose() : System.Void`  

