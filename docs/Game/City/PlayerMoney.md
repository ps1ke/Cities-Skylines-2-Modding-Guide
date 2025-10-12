# Game.City.PlayerMoney

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private System.Int32 m_Money`  
- `public System.Boolean m_Unlimited`  
- `public static const System.Int32 kMaxMoney`  

## Properties

- `public System.Int32 money { get }`  

## Constructors

- `public PlayerMoney(System.Int32 amount)`  

## Methods

- `public Add(System.Int32 value) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public Subtract(System.Int32 amount) : System.Void`  

