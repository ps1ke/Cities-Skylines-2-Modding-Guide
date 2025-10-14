# Game.EndFrameBarrier

**Assembly:** Assembly-CSharp (inferred from project layout; original assembly not included)  
**Namespace:** Game

**Type:** enum

**Base:** System.Enum

**Summary:** This file defines the FormatTags enumeration — a simple list of tags (flags in name only, not a [Flags] enum) used by the game's content/formatting systems to mark or identify specific content fixes, features, or data categories. Each member corresponds to a particular feature, fix, resource, or DLC-related marker that the game or tools may check for when processing assets, patches, or configurations. Values are implicitly assigned starting at 0 (ShortLaneOptimization = 0, HomelessAndWorkerFix = 1, ...).

---

## Fields

- `ShortLaneOptimization`  
Short lane optimization tag — likely used to mark or enable optimizations in lane/pathing logic.

- `HomelessAndWorkerFix`  
Tag for fixes related to homeless citizen counts and worker assignment/availability.

- `CompanyAndCargoFix`  
Tag for fixes affecting company behavior and cargo handling/transport.

- `TradeCostFix`  
Tag indicating a fix or adjustment to trade cost calculations.

- `TerrainSystemCleanup`  
Tag for cleanup/refactor work in the terrain system (stability/performance improvements).

- `FishResource`  
Marks fish as a resource (resource type or related handling for fisheries).

- `AquacultureLandAmbience`  
Tag for aquaculture-related land ambience (audio/visual environment for aquaculture features).

- `BpPrefabData`  
Likely marks blueprint/prefab data related to "BP" systems (e.g., blueprints, building planner data).

- `ContentPrefabInCityConfiguration`  
Used when a content prefab is included inside a city configuration (serialization/packaging marker).

- `SeagullAmbience`  
Tag for seagull ambient sounds/ambience features.

- `BPDLCAchievement`  
Tag related to a DLC achievement (BPDLC abbreviation uncertain — used to mark DLC-specific achievement data).

- `StandingLegOffset`  
Tag for standing-leg animation/IK offset corrections (animation/pose adjustment).

## Properties

- None — this is a plain enum with no properties.

## Constructors

- None — enums do not have explicit constructors in typical use.

## Methods

- None — enums do not declare methods in this definition.

```csharp
namespace Game;

public enum FormatTags
{
	ShortLaneOptimization,
	HomelessAndWorkerFix,
	CompanyAndCargoFix,
	TradeCostFix,
	TerrainSystemCleanup,
	FishResource,
	AquacultureLandAmbience,
	BpPrefabData,
	ContentPrefabInCityConfiguration,
	SeagullAmbience,
	BPDLCAchievement,
	StandingLegOffset
}
```

Notes for modders:
- This enum is a simple list of identifiers — it is not marked with [Flags], so treat values as individual named constants rather than combinable bit flags.
- Use these tags to detect or mark asset/data behaviors when inspecting serialized data, tooling, or game code that references FormatTags.
- If you need to extend behavior in a mod, search the game codebase for references to FormatTags to see how each tag is consumed (e.g., conditional processing, serialization markers, feature gating).