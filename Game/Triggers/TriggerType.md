# Game.Triggers.TriggerType

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** enum sealed public  

**Base:** `System.Enum`  
**Implements:** `System.IComparable`, `System.ISpanFormattable`, `System.IFormattable`, `System.IConvertible`  

## Code

```csharp
public sealed enum TriggerType : System.IComparable, System.ISpanFormattable, System.IFormattable, System.IConvertible
{
    public System.Int32 value__;
    public static const Game.Triggers.TriggerType NewNotification;
    public static const Game.Triggers.TriggerType NotificationResolved;
    public static const Game.Triggers.TriggerType LevelUpResidentialBuilding;
    public static const Game.Triggers.TriggerType LevelUpCommercialBuilding;
    public static const Game.Triggers.TriggerType LevelUpIndustrialBuilding;
    public static const Game.Triggers.TriggerType LevelUpOfficeBuilding;
    public static const Game.Triggers.TriggerType LevelDownResidentialBuilding;
    public static const Game.Triggers.TriggerType LevelDownCommercialBuilding;
    public static const Game.Triggers.TriggerType LevelDownIndustrialBuilding;
    public static const Game.Triggers.TriggerType LevelDownOfficeBuilding;
    public static const Game.Triggers.TriggerType CitizenStartedWorking;
    public static const Game.Triggers.TriggerType CitizenStartedSchool;
    public static const Game.Triggers.TriggerType CitizenFailedSchool;
    public static const Game.Triggers.TriggerType CitizenGraduated;
    public static const Game.Triggers.TriggerType CitizenBecameUnemployed;
    public static const Game.Triggers.TriggerType CitizenDied;
    public static const Game.Triggers.TriggerType CitizenGotSick;
    public static const Game.Triggers.TriggerType CitizenGotInjured;
    public static const Game.Triggers.TriggerType CitizenGotTrapped;
    public static const Game.Triggers.TriggerType CitizenGotInDanger;
    public static const Game.Triggers.TriggerType CitizenPartneredUp;
    public static const Game.Triggers.TriggerType CitizenDivorced;
    public static const Game.Triggers.TriggerType CitizenMovedHouse;
    public static const Game.Triggers.TriggerType CitizenMovedOutOfCity;
    public static const Game.Triggers.TriggerType CitizenSingleMadeBaby;
    public static const Game.Triggers.TriggerType CitizensFamilyMemberDied;
    public static const Game.Triggers.TriggerType TouristLeftCity;
    public static const Game.Triggers.TriggerType CitizenCommitedCrime;
    public static const Game.Triggers.TriggerType CitizenGotArrested;
    public static const Game.Triggers.TriggerType CitizenGotSentencedToPrison;
    public static const Game.Triggers.TriggerType PolicyActivated;
    public static const Game.Triggers.TriggerType MapTilePurchased;
    public static const Game.Triggers.TriggerType BrandRented;
    public static const Game.Triggers.TriggerType FreePublicTransport;
    public static const Game.Triggers.TriggerType EventHappened;
    public static const Game.Triggers.TriggerType AverageAirPollution;
    public static const Game.Triggers.TriggerType ObjectCreated;
    public static const Game.Triggers.TriggerType Temperature;
    public static const Game.Triggers.TriggerType WeatherStormy;
    public static const Game.Triggers.TriggerType WeatherClear;
    public static const Game.Triggers.TriggerType WeatherRainy;
    public static const Game.Triggers.TriggerType WeatherSunny;
    public static const Game.Triggers.TriggerType WeatherCloudy;
    public static const Game.Triggers.TriggerType AuroraBorealis;
    public static const Game.Triggers.TriggerType UnpaidLoan;
    public static const Game.Triggers.TriggerType StatisticsValue;
    public static const Game.Triggers.TriggerType ResidentialDemand;
    public static const Game.Triggers.TriggerType NoisePollutionHappinessFactor;
    public static const Game.Triggers.TriggerType WeatherSnowy;
    public static const Game.Triggers.TriggerType NoOutsideConnection;
    public static const Game.Triggers.TriggerType ServiceTradeBalance;
    public static const Game.Triggers.TriggerType TrafficBottleneck;
    public static const Game.Triggers.TriggerType TelecomHappinessFactor;
    public static const Game.Triggers.TriggerType CrimeHappinessFactor;
    public static const Game.Triggers.TriggerType AirPollutionHappinessFactor;
    public static const Game.Triggers.TriggerType ApartmentHappinessFactor;
    public static const Game.Triggers.TriggerType ElectricityHappinessFactor;
    public static const Game.Triggers.TriggerType HealthcareHappinessFactor;
    public static const Game.Triggers.TriggerType GroundPollutionHappinessFactor;
    public static const Game.Triggers.TriggerType WaterHappinessFactor;
    public static const Game.Triggers.TriggerType WaterPollutionHappinessFactor;
    public static const Game.Triggers.TriggerType SewageHappinessFactor;
    public static const Game.Triggers.TriggerType GarbageHappinessFactor;
    public static const Game.Triggers.TriggerType EntertainmentHappinessFactor;
    public static const Game.Triggers.TriggerType EducationHappinessFactor;
    public static const Game.Triggers.TriggerType MailHappinessFactor;
    public static const Game.Triggers.TriggerType WelfareHappinessFactor;
    public static const Game.Triggers.TriggerType LeisureHappinessFactor;
    public static const Game.Triggers.TriggerType CityServicePost;
    public static const Game.Triggers.TriggerType CityServiceEducation;
    public static const Game.Triggers.TriggerType CityServiceElectricity;
    public static const Game.Triggers.TriggerType CityServiceFireAndRescue;
    public static const Game.Triggers.TriggerType CityServiceGarbage;
    public static const Game.Triggers.TriggerType CityServiceHealthcare;
    public static const Game.Triggers.TriggerType CityServicePolice;
    public static const Game.Triggers.TriggerType CityServiceWaterSewage;
    public static const Game.Triggers.TriggerType TaxHappinessFactor;
    public static const Game.Triggers.TriggerType BuildingsHappinessFactor;
    public static const Game.Triggers.TriggerType WealthHappinessFactor;
    public static const Game.Triggers.TriggerType TrafficPenaltyHappinessFactor;
    public static const Game.Triggers.TriggerType DeathPenaltyHappinessFactor;
    public static const Game.Triggers.TriggerType CitizenCoupleMadeBaby;
    public static const Game.Triggers.TriggerType HomelessnessHappinessFactor;
    public static const Game.Triggers.TriggerType CitizenDroppedOutSchool;
    public static const Game.Triggers.TriggerType ElectricityFeeHappinessFactor;
    public static const Game.Triggers.TriggerType WaterFeeHappinessFactor;

}
```


## Fields

- `public System.Int32 value__`  

```csharp
public System.Int32 value__;
```

- `public static const Game.Triggers.TriggerType NewNotification`  

```csharp
public static const Game.Triggers.TriggerType NewNotification;
```

- `public static const Game.Triggers.TriggerType NotificationResolved`  

```csharp
public static const Game.Triggers.TriggerType NotificationResolved;
```

- `public static const Game.Triggers.TriggerType LevelUpResidentialBuilding`  

```csharp
public static const Game.Triggers.TriggerType LevelUpResidentialBuilding;
```

- `public static const Game.Triggers.TriggerType LevelUpCommercialBuilding`  

```csharp
public static const Game.Triggers.TriggerType LevelUpCommercialBuilding;
```

- `public static const Game.Triggers.TriggerType LevelUpIndustrialBuilding`  

```csharp
public static const Game.Triggers.TriggerType LevelUpIndustrialBuilding;
```

- `public static const Game.Triggers.TriggerType LevelUpOfficeBuilding`  

```csharp
public static const Game.Triggers.TriggerType LevelUpOfficeBuilding;
```

- `public static const Game.Triggers.TriggerType LevelDownResidentialBuilding`  

```csharp
public static const Game.Triggers.TriggerType LevelDownResidentialBuilding;
```

- `public static const Game.Triggers.TriggerType LevelDownCommercialBuilding`  

```csharp
public static const Game.Triggers.TriggerType LevelDownCommercialBuilding;
```

- `public static const Game.Triggers.TriggerType LevelDownIndustrialBuilding`  

```csharp
public static const Game.Triggers.TriggerType LevelDownIndustrialBuilding;
```

- `public static const Game.Triggers.TriggerType LevelDownOfficeBuilding`  

```csharp
public static const Game.Triggers.TriggerType LevelDownOfficeBuilding;
```

- `public static const Game.Triggers.TriggerType CitizenStartedWorking`  

```csharp
public static const Game.Triggers.TriggerType CitizenStartedWorking;
```

- `public static const Game.Triggers.TriggerType CitizenStartedSchool`  

```csharp
public static const Game.Triggers.TriggerType CitizenStartedSchool;
```

- `public static const Game.Triggers.TriggerType CitizenFailedSchool`  

```csharp
public static const Game.Triggers.TriggerType CitizenFailedSchool;
```

- `public static const Game.Triggers.TriggerType CitizenGraduated`  

```csharp
public static const Game.Triggers.TriggerType CitizenGraduated;
```

- `public static const Game.Triggers.TriggerType CitizenBecameUnemployed`  

```csharp
public static const Game.Triggers.TriggerType CitizenBecameUnemployed;
```

- `public static const Game.Triggers.TriggerType CitizenDied`  

```csharp
public static const Game.Triggers.TriggerType CitizenDied;
```

- `public static const Game.Triggers.TriggerType CitizenGotSick`  

```csharp
public static const Game.Triggers.TriggerType CitizenGotSick;
```

- `public static const Game.Triggers.TriggerType CitizenGotInjured`  

```csharp
public static const Game.Triggers.TriggerType CitizenGotInjured;
```

- `public static const Game.Triggers.TriggerType CitizenGotTrapped`  

```csharp
public static const Game.Triggers.TriggerType CitizenGotTrapped;
```

- `public static const Game.Triggers.TriggerType CitizenGotInDanger`  

```csharp
public static const Game.Triggers.TriggerType CitizenGotInDanger;
```

- `public static const Game.Triggers.TriggerType CitizenPartneredUp`  

```csharp
public static const Game.Triggers.TriggerType CitizenPartneredUp;
```

- `public static const Game.Triggers.TriggerType CitizenDivorced`  

```csharp
public static const Game.Triggers.TriggerType CitizenDivorced;
```

- `public static const Game.Triggers.TriggerType CitizenMovedHouse`  

```csharp
public static const Game.Triggers.TriggerType CitizenMovedHouse;
```

- `public static const Game.Triggers.TriggerType CitizenMovedOutOfCity`  

```csharp
public static const Game.Triggers.TriggerType CitizenMovedOutOfCity;
```

- `public static const Game.Triggers.TriggerType CitizenSingleMadeBaby`  

```csharp
public static const Game.Triggers.TriggerType CitizenSingleMadeBaby;
```

- `public static const Game.Triggers.TriggerType CitizensFamilyMemberDied`  

```csharp
public static const Game.Triggers.TriggerType CitizensFamilyMemberDied;
```

- `public static const Game.Triggers.TriggerType TouristLeftCity`  

```csharp
public static const Game.Triggers.TriggerType TouristLeftCity;
```

- `public static const Game.Triggers.TriggerType CitizenCommitedCrime`  

```csharp
public static const Game.Triggers.TriggerType CitizenCommitedCrime;
```

- `public static const Game.Triggers.TriggerType CitizenGotArrested`  

```csharp
public static const Game.Triggers.TriggerType CitizenGotArrested;
```

- `public static const Game.Triggers.TriggerType CitizenGotSentencedToPrison`  

```csharp
public static const Game.Triggers.TriggerType CitizenGotSentencedToPrison;
```

- `public static const Game.Triggers.TriggerType PolicyActivated`  

```csharp
public static const Game.Triggers.TriggerType PolicyActivated;
```

- `public static const Game.Triggers.TriggerType MapTilePurchased`  

```csharp
public static const Game.Triggers.TriggerType MapTilePurchased;
```

- `public static const Game.Triggers.TriggerType BrandRented`  

```csharp
public static const Game.Triggers.TriggerType BrandRented;
```

- `public static const Game.Triggers.TriggerType FreePublicTransport`  

```csharp
public static const Game.Triggers.TriggerType FreePublicTransport;
```

- `public static const Game.Triggers.TriggerType EventHappened`  

```csharp
public static const Game.Triggers.TriggerType EventHappened;
```

- `public static const Game.Triggers.TriggerType AverageAirPollution`  

```csharp
public static const Game.Triggers.TriggerType AverageAirPollution;
```

- `public static const Game.Triggers.TriggerType ObjectCreated`  

```csharp
public static const Game.Triggers.TriggerType ObjectCreated;
```

- `public static const Game.Triggers.TriggerType Temperature`  

```csharp
public static const Game.Triggers.TriggerType Temperature;
```

- `public static const Game.Triggers.TriggerType WeatherStormy`  

```csharp
public static const Game.Triggers.TriggerType WeatherStormy;
```

- `public static const Game.Triggers.TriggerType WeatherClear`  

```csharp
public static const Game.Triggers.TriggerType WeatherClear;
```

- `public static const Game.Triggers.TriggerType WeatherRainy`  

```csharp
public static const Game.Triggers.TriggerType WeatherRainy;
```

- `public static const Game.Triggers.TriggerType WeatherSunny`  

```csharp
public static const Game.Triggers.TriggerType WeatherSunny;
```

- `public static const Game.Triggers.TriggerType WeatherCloudy`  

```csharp
public static const Game.Triggers.TriggerType WeatherCloudy;
```

- `public static const Game.Triggers.TriggerType AuroraBorealis`  

```csharp
public static const Game.Triggers.TriggerType AuroraBorealis;
```

- `public static const Game.Triggers.TriggerType UnpaidLoan`  

```csharp
public static const Game.Triggers.TriggerType UnpaidLoan;
```

- `public static const Game.Triggers.TriggerType StatisticsValue`  

```csharp
public static const Game.Triggers.TriggerType StatisticsValue;
```

- `public static const Game.Triggers.TriggerType ResidentialDemand`  

```csharp
public static const Game.Triggers.TriggerType ResidentialDemand;
```

- `public static const Game.Triggers.TriggerType NoisePollutionHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType NoisePollutionHappinessFactor;
```

- `public static const Game.Triggers.TriggerType WeatherSnowy`  

```csharp
public static const Game.Triggers.TriggerType WeatherSnowy;
```

- `public static const Game.Triggers.TriggerType NoOutsideConnection`  

```csharp
public static const Game.Triggers.TriggerType NoOutsideConnection;
```

- `public static const Game.Triggers.TriggerType ServiceTradeBalance`  

```csharp
public static const Game.Triggers.TriggerType ServiceTradeBalance;
```

- `public static const Game.Triggers.TriggerType TrafficBottleneck`  

```csharp
public static const Game.Triggers.TriggerType TrafficBottleneck;
```

- `public static const Game.Triggers.TriggerType TelecomHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType TelecomHappinessFactor;
```

- `public static const Game.Triggers.TriggerType CrimeHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType CrimeHappinessFactor;
```

- `public static const Game.Triggers.TriggerType AirPollutionHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType AirPollutionHappinessFactor;
```

- `public static const Game.Triggers.TriggerType ApartmentHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType ApartmentHappinessFactor;
```

- `public static const Game.Triggers.TriggerType ElectricityHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType ElectricityHappinessFactor;
```

- `public static const Game.Triggers.TriggerType HealthcareHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType HealthcareHappinessFactor;
```

- `public static const Game.Triggers.TriggerType GroundPollutionHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType GroundPollutionHappinessFactor;
```

- `public static const Game.Triggers.TriggerType WaterHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType WaterHappinessFactor;
```

- `public static const Game.Triggers.TriggerType WaterPollutionHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType WaterPollutionHappinessFactor;
```

- `public static const Game.Triggers.TriggerType SewageHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType SewageHappinessFactor;
```

- `public static const Game.Triggers.TriggerType GarbageHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType GarbageHappinessFactor;
```

- `public static const Game.Triggers.TriggerType EntertainmentHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType EntertainmentHappinessFactor;
```

- `public static const Game.Triggers.TriggerType EducationHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType EducationHappinessFactor;
```

- `public static const Game.Triggers.TriggerType MailHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType MailHappinessFactor;
```

- `public static const Game.Triggers.TriggerType WelfareHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType WelfareHappinessFactor;
```

- `public static const Game.Triggers.TriggerType LeisureHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType LeisureHappinessFactor;
```

- `public static const Game.Triggers.TriggerType CityServicePost`  

```csharp
public static const Game.Triggers.TriggerType CityServicePost;
```

- `public static const Game.Triggers.TriggerType CityServiceEducation`  

```csharp
public static const Game.Triggers.TriggerType CityServiceEducation;
```

- `public static const Game.Triggers.TriggerType CityServiceElectricity`  

```csharp
public static const Game.Triggers.TriggerType CityServiceElectricity;
```

- `public static const Game.Triggers.TriggerType CityServiceFireAndRescue`  

```csharp
public static const Game.Triggers.TriggerType CityServiceFireAndRescue;
```

- `public static const Game.Triggers.TriggerType CityServiceGarbage`  

```csharp
public static const Game.Triggers.TriggerType CityServiceGarbage;
```

- `public static const Game.Triggers.TriggerType CityServiceHealthcare`  

```csharp
public static const Game.Triggers.TriggerType CityServiceHealthcare;
```

- `public static const Game.Triggers.TriggerType CityServicePolice`  

```csharp
public static const Game.Triggers.TriggerType CityServicePolice;
```

- `public static const Game.Triggers.TriggerType CityServiceWaterSewage`  

```csharp
public static const Game.Triggers.TriggerType CityServiceWaterSewage;
```

- `public static const Game.Triggers.TriggerType TaxHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType TaxHappinessFactor;
```

- `public static const Game.Triggers.TriggerType BuildingsHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType BuildingsHappinessFactor;
```

- `public static const Game.Triggers.TriggerType WealthHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType WealthHappinessFactor;
```

- `public static const Game.Triggers.TriggerType TrafficPenaltyHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType TrafficPenaltyHappinessFactor;
```

- `public static const Game.Triggers.TriggerType DeathPenaltyHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType DeathPenaltyHappinessFactor;
```

- `public static const Game.Triggers.TriggerType CitizenCoupleMadeBaby`  

```csharp
public static const Game.Triggers.TriggerType CitizenCoupleMadeBaby;
```

- `public static const Game.Triggers.TriggerType HomelessnessHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType HomelessnessHappinessFactor;
```

- `public static const Game.Triggers.TriggerType CitizenDroppedOutSchool`  

```csharp
public static const Game.Triggers.TriggerType CitizenDroppedOutSchool;
```

- `public static const Game.Triggers.TriggerType ElectricityFeeHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType ElectricityFeeHappinessFactor;
```

- `public static const Game.Triggers.TriggerType WaterFeeHappinessFactor`  

```csharp
public static const Game.Triggers.TriggerType WaterFeeHappinessFactor;
```


