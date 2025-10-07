# Using the Travel Impact Model (TIM) for Greenhouse Gases (GHG) Reporting

## Overview

The Travel Impact Model (TIM): Scope 3, category 6 flight emissions dataset is
designed to help companies and individuals calculate and report Scope 3,
category 6 flight emissions from business travel. The full model output includes
emission estimates from 2019 for scheduled worldwide commercial flights.[^1]

This dataset offers three calculation tiers. Users should select the tier that
matches the granularity of their own available travel data, prioritizing higher
tiers:

*   **Tier 1 (High-Accuracy): TIM past direct flight emissions**
    *   When to use: Use this when you have detailed records of specific past
        flights (e.g., origin, destination, and date).
*   **Tier 2 (Fallback): Typical flight emissions**
    *   When to use: Use this as the first fallback when you lack specific
        flight details but know the general flight path (origin and
        destination).
*   **Tier 3 (Basic Estimate): Distance-based emission factors**
    *   When to use: Use this as the second fallback when you only have
        aggregate data, such as total distances traveled.

### Intended Use

This dataset is intended for past flight emissions reporting. It covers three
components of emissions: well-to-tank (WTT) value for the upstream emissions
from fuel extraction, refining, and transportation; tank-to-wake (TTW) value for
the emissions produced by burning aviation fuel during a flight; and the
well-to-wake (WTW) value, which is the combination of the first two, for a more
holistic view of the climate impact.

### How to Use

Please refer to the API documentation for
[`computeScope3FlightEmissions` in the Travel Impact Model API website](https://developers.google.com/travel/impact-model/docs/reference/rest/v1/flights/computeScope3FlightEmissions).

## Methodology

The dataset allows you to calculate emissions in several ways, organized into
tiers. When calculating your emissions, you should always use the highest tier
dataset for which you have all of the required data.

### Tier 1: TIM Past Direct Flight Emissions

This is the main dataset and provides the most accurate calculations. It is
applicable for **direct flights only**.

#### Required Data

*   Carrier
*   Flight number
*   Origin airport
*   Destination airport
*   Flight departure date
*   Cabin class

### Tier 2: Typical Flight Emissions

Use this dataset when you do not have all the data required for Tier 1, or for
trips that include indirect flights. If you have Tier 1 data for some legs of a
journey and Tier 2 for others, you should use the Tier 2 dataset for the entire
trip (from origin to final destination).

#### Required Data

*   Origin airport
*   Destination airport
*   Flight departure year
*   Cabin class

### Tier 3: Distance-Based Emission Factors

Use this dataset when the information required for Tier 1 and Tier 2 is not
available. This method is applicable for direct or indirect flights.

#### Required Data

*   Distance traveled
*   Flight departure year
*   Cabin class

### Data Handling & Recommendations

#### Short-lived Climate Pollutants and Contrail-induced Cirrus Clouds

The TIM Scope 3, category 6 flight emissions dataset does not yet account for
the climate impact of short-lived climate pollutants and contrail-induced cirrus
clouds.

#### Sustainable Aviation Fuel (SAF)

Sustainable Aviation Fuel certificates (SAFc) are not directly supported. We
recommend users calculate any emissions reductions from SAFc separately from the
figures generated using TIM data.

#### Distance Calculation

The distance provided for Tier 3 calculations should be the Great Circle
Distance (GCD). You should not add any correction factors to this distance, as
TIM's emission factors already incorporate necessary adjustments
([see documentation for the main model](https://github.com/google/travel-impact-model?tab=readme-ov-file#distance-adjustment)).
If you do not have distance information for a trip, it cannot be processed with
this dataset[^2].

#### Mapping Airports

If your activity data contains locations without specific airport codes, you can
map them to the nearest major airport based on distance and traffic volume.

## TIM Versioning

The current version for the Scope 3, category 6 flight emissions dataset uses
[the Travel Impact Model v2.0.0](https://github.com/google/travel-impact-model/tree/main?tab=readme-ov-file#200).

## Model Validation

TIM employs a rigorous validation process to ensure the model accurately
estimates aircraft fuel burn, leveraging both public and private data. This
process increases transparency and ensures TIM provides reliable fuel
consumption estimates. More details can be found in the
[Model Validation Methodology](https://travelimpactmodel.org/static/media/tim_model_validation_methodology.pdf)
and
[this technical brief](https://travelimpactmodel.org/static/media/tim_model_selection.pdf).

## Country-Specific Factors

If a country mandates the use of specific, government-provided emission factors,
the TIM dataset is not applicable. In these cases, you should use the
country-specific factors instead.

[^1]: We do not yet support charter flights, private flights, cargo flights, or
    travel operated by ferries, buses, and rail.
[^2]: For cases with no distance information, we recommend using a spend-based
    method with a relevant environmentally-extended input-output (EEIO)
    database, following GHG Protocol guidance.
