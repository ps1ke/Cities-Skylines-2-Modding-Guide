# Game.Simulation.CitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ICitySystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.Entity m_City`  
- `private System.Int32 m_Money`  
- `private System.Int32 m_XP`  

## Properties

- `public Unity.Entities.Entity City { get }`  
- `public System.Int32 moneyAmount { get }`  
- `public System.Int32 XP { get }`  

## Constructors

- `public CitySystem()`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

