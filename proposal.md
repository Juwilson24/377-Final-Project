
### Bigger Picture Question
How does geographic location impact real estate prices, demand, and investment opportunities? More specifically, how do regional factors such as proximity to amenities, socioeconomic conditions, or climate risks influence residential property values and market trends?

This is a broad and widely studied question in real estate economics and urban planning. Our project aims to explore a slice of this broader issue with data-driven methods.

### Specific Research Question(s)
How do real estate prices vary based on proximity to amenities like public transportation, schools, and green spaces in a specific metropolitan area (e.g., New York City or Los Angeles)?

1. Are property values significantly impacted by neighborhood-level characteristics such as average income, crime rates, or walkability scores?

2. Does climate risk (e.g. flood zones) correlate with lower home values, and is this impact more noticeable in some neighborhoods?

These specific questions aim to shed light on how spatial and socioeconomic features influence housing prices within a single city or metro area.

### Type of Project
This is primarily an explanatory/relationship-based project.

### Hypotheses
H1: *Homes closer to public transit hubs or good schools command higher prices.*

H2: *Neighborhoods with higher average income and lower crime rates have higher real estate values.*

H3: *Properties located in areas with climate-related risks (e.g. flood zones) have lower values, controlling for other factors.*


### Metrics of Success
**Statistical significance of location-based predictors in a regression or model.**

1. Model performance (if we use prediction methods): R² or MAE on test set.

2. Clarity of spatial patterns shown in maps or visualizations.

Baseline: *Previous studies or Zillow research reports can give ballpark estimates (e.g., how much a 1-point increase in walkability boosts home prices).*

### Dashboard
**Interactive Real Estate Dashboard**
- Our dashboard will allow users to regional factors (amenities, socioeconomic conditions, climate risk, etc) correlate with housing prices. 
- Dashboard Layout:
    - Display a map of neighborhoods in metro areas colored by median home prices
    - Users would be able to view home prices, nighborhood names, and other key states
    - Dashboard would also display proximity of regional factors to homes
- Visuals:
    - Amenities:
        - Visual to show price vs distance to amenities(park, school, subway)
        - Heatmap to show density of certain amenities in an metro area.
     - Climate Risk:
         - Visual to show average price distance between high/low climate risk areas
         - Display to show proximity of possible naturatl disaster to homes with home prices

### How to Handle Maps
- Integrate Pythons Folium & Plotly librariers to create interactive maps.
- Merge Redfin's neighborhood price data with public geographic boundries 
- We will overlay amenity & climate risk data 
- The maps will be embedded on the dashboard, via tooltips by the Streamlit python library

### Data
- Data provides nationwide loan-level records such as:
    - Loan Application Details
    - Applicant Demographics
    - Geographic Data
- We can use the variable msamd_name which holds names of the metro areas to find proximity to amenities
- We can utilize state_name variable to research types of climates risk by each state then use the msamd_name variable to filter by particular areas.

| **Concept**             | **Description** |
|-------------------------|-----------------|
| **Home Prices**         | Sourced from Redfin or Zillow datasets. Includes median sale price, number of homes sold, and neighborhood names. This is the core dependent variable in our analysis. |
| **Amenities**           | Pulled from OpenStreetMap or city-specific data portals. Includes the locations of schools, parks, public transit stations. Will be used to compute proximity to each amenity. |
| **Socioeconomic Data**  | From the U.S. Census Bureau’s American Community Survey (ACS). Variables include median income, unemployment rates, and education levels at the neighborhood or census tract level. |
| **Crime Rates**         | Accessed via local city open data platforms (e.g., NYC Open Data). Contains incident-level or aggregated neighborhood crime statistics. Used to test the impact of safety on home values. |
| **Climate Risk**        | FEMA Flood Maps, First Street Foundation, or ClimateCheck. Provides data on flood zones, wildfire risk, and other climate hazards by region or parcel. Used to assess H3. |
| **Geographic Boundaries** | GeoJSON or shapefile data from TIGER/Line (U.S. Census) or city GIS repositories. Defines the physical boundaries of neighborhoods or metro areas. Required for mapping and spatial joins. |
| **Loan & Demographic Data** | HMDA (Home Mortgage Disclosure Act) dataset. Includes loan application details, applicant income, race, gender, and location via `msamd_name`. Useful for filtering and segmentation. |

### Missing Data

To ensure that our analysis produces both statistically valid and practically meaningful insights, we will evaluate our models using a combination of quantitative metrics and qualitative assessments. These methods will help us assess how well regional factors explain or predict housing prices, and whether the patterns shown in our dashboard are both accurate and interpretable.

While R² and MAE were mentioned initially, we’re expanding our framework to include several important tools for evaluating regression models, machine learning predictions, and geospatial insights.

- **R²** will show how well our models explain the variability in home prices.

- **MAE** offers an intuitive measure of prediction accuracy in dollar terms.

- **P-values** will help validate the statistical significance of individual predictors tied to our core hypotheses (e.g., H1: homes closer to amenities are worth more).

- **Variance Inflation Factor (VIF)** will help check for multicollinearity between predictors like income and education.

- **Feature Importance** will rank which geographic or socioeconomic variables are most influential in ML models.

- **Geospatial Visual Clarity** allows us to evaluate whether patterns like clustering, amenity proximity, or climate risk are clearly communicated through maps.

- **Baseline Comparison** ensures our results are aligned with industry benchmarks from Zillow, Redfin, and academic literature—supporting the real-world relevance of our findings.


| **Metric** | **Description** |
|------------|-----------------|
| **R² (Coefficient of Determination)** | Measures how much of the variation in home prices is explained by the model. Values closer to 1 indicate better model performance. |
| **MAE (Mean Absolute Error)** | Evaluates the average prediction error in dollar terms. Lower MAE means the model is making more accurate price predictions. |
| **P-values** | Used in regression analysis to determine if a predictor (e.g., distance to subway, crime rate) is statistically significant. A p-value < 0.05 typically indicates a meaningful effect. |
| **Variance Inflation Factor (VIF)** | Identifies multicollinearity between independent variables to ensure the model's stability and interpretability. |
| **Feature Importance** | In machine learning models (e.g., Random Forest), this ranks which features (e.g., income, amenity proximity) are most influential in predicting home prices. |
| **Geospatial Visual Clarity** | A qualitative measure of how clearly maps display spatial patterns like clustering of high/low prices or proximity trends. |
| **Baseline Comparison** | Compares model results to external industry benchmarks (e.g., Zillow research) to verify that trends and effect sizes are realistic. |