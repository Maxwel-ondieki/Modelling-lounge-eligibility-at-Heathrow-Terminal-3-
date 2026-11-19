# Modelling-lounge-eligibility-at-Heathrow-Terminal-3-
The BA data science project at Forage seeks to analyse the eligibility of passengers of British airways at any particular time to enhance time-based capacity management and proper passenger eligibility segmentation.
# BACKGROUND STATEMENT
## As outlined in the BA forage description ##
Lounge access is a key part of the premium travel experience, and understanding lounge demand is crucial for British Airways (BA) to maintain high standards while optimizing space and resources. As the airline plans for future operations at Heathrow Terminal 3, it’s important to anticipate demand across different types of lounge access, each associated with varying levels of customer loyalty and travel class.

As BA plans for the future, especially with changes in flying schedules and fleet strategy, it's important to forecast how many passengers will be eligible to use each lounge on a typical day. However, future schedules can be unpredictable, which means we need a modeling approach that is both flexible and scalable.

That’s where you come in. Your job is to create a lookup table that BA can use to estimate lounge eligibility percentages across different flight groupings. This will allow the business to anticipate lounge demand without needing exact flight or aircraft details.

To do this well, you’ll need to think critically about how to group flights in a meaningful way—by time of day, route type, or regional destination, for example, and apply logical assumptions to estimate how many travelers fall into each lounge tier. These estimates will help the Airport Planning team better understand where lounge investments may be needed as operations evolve.

In short, your table and justification will help translate data into decisions—and ensure BA continues to deliver a seamless experience for its most valued customers.

#EXPOLATORY DATA ANALYSIS
For my project I will use google Collab for python analysis.

summer_df = pd.read_excel(
    summer_file,
    sheet_name='british_airways_schedule_summer'
)

summer_df.head()

# results
 Number of rows: 10000
Number of columns: 17
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 10000 entries, 0 to 9999
Data columns (total 17 columns):
 #   Column                Non-Null Count  Dtype         
---  ------                --------------  -----         
 0   FLIGHT_DATE           10000 non-null  datetime64[ns]
 1   FLIGHT_TIME           10000 non-null  object        
 2   TIME_OF_DAY           10000 non-null  object        
 3   AIRLINE_CD            10000 non-null  object        
 4   FLIGHT_NO             10000 non-null  object        
 5   DEPARTURE_STATION_CD  10000 non-null  object        
 6   ARRIVAL_STATION_CD    10000 non-null  object        
 7   ARRIVAL_COUNTRY       10000 non-null  object        
 8   ARRIVAL_REGION        10000 non-null  object        
 9   HAUL                  10000 non-null  object        
 10  AIRCRAFT_TYPE         10000 non-null  object        
 11  FIRST_CLASS_SEATS     10000 non-null  int64         
 12  BUSINESS_CLASS_SEATS  10000 non-null  int64         
 13  ECONOMY_SEATS         10000 non-null  int64         
 14  TIER1_ELIGIBLE_PAX    10000 non-null  int64         
 15  TIER2_ELIGIBLE_PAX    10000 non-null  int64         
 16  TIER3_ELIGIBLE_PAX    10000 non-null  int64         
dtypes: datetime64[ns](1), int64(6), object(10)
memory usage: 1.3+ MB

  
    

    
