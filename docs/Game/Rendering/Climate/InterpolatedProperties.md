# Game.Rendering.Climate.WeatherPropertiesStack+InterpolatedProperties

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Climate`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `public System.Single time`  
- `public Colossal.Mathematics.Bounds1 remapLimits`  
- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent current`  
- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent previous`  
- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent target`  
- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent from`  
- `public readonly Game.Prefabs.Climate.OverrideablePropertiesComponent to`  
- `internal Game.Prefabs.Climate.OverrideablePropertiesComponent source`  

## Constructors

- `public InterpolatedProperties(Game.Prefabs.Climate.OverrideablePropertiesComponent current, Game.Prefabs.Climate.OverrideablePropertiesComponent previous, Game.Prefabs.Climate.OverrideablePropertiesComponent target, Game.Prefabs.Climate.OverrideablePropertiesComponent from, Game.Prefabs.Climate.OverrideablePropertiesComponent to)`  

## Methods

- `public Advance(System.Single deltaTime, System.Single renderingDeltaTime) : System.Void`  
- `public GetLerp(Game.Simulation.ClimateSystem+ClimateSample sample) : System.Single`  
- `private static Remap(System.Single value, System.Single from1, System.Single to1, System.Single from2, System.Single to2) : System.Single`  
- `public SetFrom(Game.Prefabs.Climate.OverrideablePropertiesComponent newTo) : System.Void`  
- `public SetPrevious(Game.Prefabs.Climate.OverrideablePropertiesComponent newSource) : System.Void`  
- `public SetTarget(Game.Prefabs.Climate.OverrideablePropertiesComponent newTarget) : System.Void`  
- `public SetTo(Game.Prefabs.Climate.OverrideablePropertiesComponent newTo) : System.Void`  

