# Game.Simulation.XPBuiltSystem+XPElectricityJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Buildings.ElectricityConsumer> m_ElectricityConsumers`  
- `public Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue`  
- `public Unity.Entities.Entity m_City`  
- `public Unity.Entities.ComponentLookup<Game.City.XP> m_CityXPs`  

## Methods

- `public Execute() : System.Void`  

