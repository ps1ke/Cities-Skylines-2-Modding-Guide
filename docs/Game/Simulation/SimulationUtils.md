# Game.Simulation.SimulationUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Single FRAMES_PER_SECOND`  
- `public static const System.Int32 MOVING_OBJECT_UPDATE_GROUP_SHIFT`  
- `public static const System.Int32 MOVING_OBJECT_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 NET_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 LANE_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 TREE_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 BUILDING_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 COMPANY_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 HOUSEHOLD_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 CITIZEN_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 HOUSEHOLDPET_UPDATE_GROUP_COUNT`  
- `public static const System.Int32 GARBAGE_COLLECTION_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 TRANSPORT_VEHICLE_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 RANDOM_TRAFFIC_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 FIRE_RESCUE_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 POLICE_PATROL_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 TAXI_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 HEALTHCARE_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 MAINTENANCE_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 POST_VAN_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 MAIL_TRANSFER_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 POLICE_EMERGENCY_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 EVACUATION_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 PRISONER_TRANSPORT_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 GARBAGE_TRANSFER_DISPATCH_GROUP_COUNT`  
- `public static const System.Int32 MOVING_OBJECT_INTERPOLATION_FRAME_COUNT`  
- `public static const System.Int32 MOVING_EVENT_INTERPOLATION_FRAME_COUNT`  
- `public static const System.Int32 AMBULANCE_UPDATE_GROUP`  
- `public static const System.Int32 BUS_UPDATE_GROUP`  
- `public static const System.Int32 GARBAGE_TRUCK_UPDATE_GROUP`  
- `public static const System.Int32 TRAIN_UPDATE_GROUP`  
- `public static const System.Int32 FIRE_ENGINE_UPDATE_GROUP`  
- `public static const System.Int32 POLICE_CAR_UPDATE_GROUP`  
- `public static const System.Int32 TAXI_UPDATE_GROUP`  
- `public static const System.Int32 MAINTENANCE_VEHICLE_UPDATE_GROUP`  
- `public static const System.Int32 WATERCRAFT_UPDATE_GROUP`  
- `public static const System.Int32 POST_VAN_UPDATE_GROUP`  
- `public static const System.Int32 AIRCRAFT_UPDATE_GROUP`  
- `public static const System.Int32 HEARSE_UPDATE_GROUP`  
- `public static const System.Int32 WORK_VEHICLE_UPDATE_GROUP`  
- `public static const System.Int32 PET_UPDATE_GROUP`  
- `public static const System.Int32 WILDLIFE_UPDATE_GROUP`  
- `public static const System.Int32 DOMESTICATED_UPDATE_GROUP`  
- `public static const System.UInt32 BUILDING_UPDATE_INTERVAL`  
- `public static const System.UInt32 DISPATCH_INTERVAL`  
- `public static const System.UInt32 DISPATCH_DELAY`  
- `public static const System.UInt32 MAX_PATHFIND_DELAY`  
- `public static const System.UInt32 CREATURE_SPAWN_INTERVAL`  
- `public static const System.UInt32 MOVING_EVENT_UPDATE_INTERVAL`  
- `public static const System.UInt32 MOVING_EVENT_UPDATE_GROUP`  
- `public static const System.Int32 TRANSPORT_STATION_UPDATE_GROUP`  
- `public static const System.Int32 HOSPITAL_UPDATE_GROUP`  
- `public static const System.Int32 TRANSPORT_DEPOT_UPDATE_GROUP`  
- `public static const System.Int32 GARBAGE_FACILITY_UPDATE_GROUP`  
- `public static const System.Int32 SCHOOL_UPDATE_GROUP`  
- `public static const System.Int32 FIRE_STATION_UPDATE_GROUP`  
- `public static const System.Int32 POLICE_STATION_UPDATE_GROUP`  
- `public static const System.Int32 PARK_UPDATE_GROUP`  
- `public static const System.Int32 MAINTENANCE_DEPOT_UPDATE_GROUP`  
- `public static const System.Int32 POST_FACILITY_UPDATE_GROUP`  
- `public static const System.Int32 PARKING_FACILITY_UPDATE_GROUP`  
- `public static const System.Int32 TELECOM_FACILITY_UPDATE_GROUP`  
- `public static const System.Int32 EXTRACTOR_FACILITY_UPDATE_GROUP`  
- `public static const System.Int32 EMERGENCY_SHELTER_UPDATE_GROUP`  
- `public static const System.Int32 DISASTER_FACILITY_UPDATE_GROUP`  
- `public static const System.Int32 FIREWATCH_TOWER_UPDATE_GROUP`  
- `public static const System.Int32 DEATHCARE_FACILITY_UPDATE_GROUP`  
- `public static const System.Int32 PRISON_UPDATE_GROUP`  
- `public static const System.Int32 ADMIN_BUILDING_UPDATE_GROUP`  
- `public static const System.Int32 WELFARE_OFFICE_UPDATE_GROUP`  
- `public static const System.Int32 RESEARCH_FACILITY_UPDATE_GROUP`  

## Methods

- `public static GetUpdateFrame(System.UInt32 frame, System.Int32 updatesPerDay, System.Int32 groupCount) : System.UInt32`  
- `public static GetUpdateFrameRare(System.UInt32 frame, System.Int32 daysPerUpdate, System.Int32 groupCount) : System.UInt32`  
- `public static GetUpdateFrameWithInterval(System.UInt32 frame, System.UInt32 interval, System.Int32 groupCount) : System.UInt32`  
- `public static ResetFailedRequest(Game.Simulation.ServiceRequest& serviceRequest) : System.Void`  
- `public static ResetReverseRequest(Game.Simulation.ServiceRequest& serviceRequest) : System.Void`  
- `public static TickServiceRequest(Game.Simulation.ServiceRequest& serviceRequest) : System.Boolean`  

