# Game.Companies.Workplaces

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.IAccumulable<Game.Companies.Workplaces>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `DefaultMember`  

## Fields

- `public System.Int32 m_Uneducated`  
- `public System.Int32 m_PoorlyEducated`  
- `public System.Int32 m_Educated`  
- `public System.Int32 m_WellEducated`  
- `public System.Int32 m_HighlyEducated`  

## Properties

- `public System.Int32 TotalCount { get }`  
- `public System.Int32 SimpleWorkplacesCount { get }`  
- `public System.Int32 ComplexWorkplacesCount { get }`  
- `public System.Int32 Item { get; set }`  

## Methods

- `public Accumulate(Game.Companies.Workplaces other) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public ToArray(Unity.Collections.NativeArray<System.Int32> array) : System.Void`  

