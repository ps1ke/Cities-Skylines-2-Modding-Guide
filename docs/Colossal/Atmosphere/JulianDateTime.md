# Colossal.Atmosphere.JulianDateTime

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private System.Int64 m_Day`  
- `private System.Double m_Fraction`  
- `private static readonly Colossal.Atmosphere.JulianDateTime J2000`  
- `private static const System.Double kSecPerDay`  
- `private static const System.Double kOmegaE`  

## Constructors

- `public JulianDateTime(System.Double j)`  
- `public JulianDateTime(Colossal.Atmosphere.JulianDateTime j)`  
- `public JulianDateTime(System.DateTime utc)`  

## Methods

- `public AddSeconds(System.Double seconds) : System.Void`  
- `public Subtract(Colossal.Atmosphere.JulianDateTime j) : System.Double`  
- `public Subtract(System.Double j) : System.Double`  
- `public ToDateTime() : System.DateTime`  
- `public ToDouble() : System.Double`  
- `public ToGMST() : System.Double`  
- `public ToLMST(System.Double longitude) : System.Double`  
- `public virtual ToString() : System.String`  

