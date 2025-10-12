# Game.Simulation.ZoneAmbiences

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Single m_ResidentialLow`  
- `public System.Single m_CommercialLow`  
- `public System.Single m_Industrial`  
- `public System.Single m_Agriculture`  
- `public System.Single m_Forestry`  
- `public System.Single m_Oil`  
- `public System.Single m_Ore`  
- `public System.Single m_OfficeLow`  
- `public System.Single m_OfficeHigh`  
- `public System.Single m_ResidentialMedium`  
- `public System.Single m_ResidentialHigh`  
- `public System.Single m_ResidentialMixed`  
- `public System.Single m_CommercialHigh`  
- `public System.Single m_ResidentialLowRent`  
- `public System.Single m_Forest`  
- `public System.Single m_WaterfrontLow`  
- `public System.Single m_AquacultureLand`  
- `public System.Single m_SeagullAmbience`  

## Methods

- `public AddAmbience(Game.Simulation.GroupAmbienceType type, System.Single value) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetAmbience(Game.Simulation.GroupAmbienceType type) : System.Single`  
- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

