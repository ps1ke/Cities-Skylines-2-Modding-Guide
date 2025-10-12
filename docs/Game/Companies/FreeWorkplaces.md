# Game.Companies.FreeWorkplaces

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Byte m_Uneducated`  
- `public System.Byte m_PoorlyEducated`  
- `public System.Byte m_Educated`  
- `public System.Byte m_WellEducated`  
- `public System.Byte m_HighlyEducated`  

## Properties

- `public System.Int32 Count { get }`  

## Constructors

- `public FreeWorkplaces(Game.Companies.Workplaces free)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetBestFor(System.Int32 level) : System.Int32`  
- `public GetFree(System.Int32 level) : System.Byte`  
- `public GetLowestFree() : System.Byte`  
- `public Refresh(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 level) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `private SetFree(System.Int32 level, System.Byte amount) : System.Void`  

