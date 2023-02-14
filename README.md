# Meltano Google Analytics V4: Extract, Transform, Load

Google Analytics is one of the main sources of data for the marketing team.
___
___


## Running the application
 This application contains two GA4 streams (sourcemedium_campaign_sessions & new_vs_returning_conversions). 
 Both are associated with unique ETL pipelines, that utilize the `target-csv` (default) loader. 
 When you follow these steps your pipelines will output a local csv file in the `output` directory.
 ___
___


### Configuration
 1. Clone this repository locally
```
clone https://github.com/connorflyn/meltano-ga4-cqf.git
```
 2. Open the locally cloned repository
```
cd meltano-ga4-cqf
```
 3. Create and open the `.evn` file with the repository (which is also a Meltano project)
```
nano .evn
```
 4. In the `.env` file enter your credentials (using the example provided below)
```
TAP_GOOGLE_ANALYTICS_V4_PROPERTY_ID=123456789
```
 5. Create and open the `meltano_GA4_client_secrets` JSON file, which will act as your service account file for GA authentication
```
nano .meltano/meltano_GA4_client_secrets.json
```
 6. Paste your GA service account credential file contents in the `meltano_GA4_client_secrets` JSON file
___
 








### Run an ETL pipelines
This Meltano project contains two pipelines you may run. Both of which will output into a local CSV file in the `output` direcotry
___






#### Run GA4 Sourcemedium Campaign Sessions

 1. If you are not already located in the locally cloned `meltano-ga4-cqf` repository, navigate to it now
```
cd meltano-ga4-cqf
```
 2. Once inside of the `meltano-ga4-cqf` repository, run the following command to trigger the ***Sourcemedium Campaign Sessions*** pipeline
```
meltano elt tap-google-analytics-v4-new-vs-returning-conversions-us target-csv --state-id=ga4-new-vs-returning-conversions
```

___
#### Run GA4 New Vs Returning Conversions

 1. If you are not already located in the locally cloned `meltano-ga4-cqf` repository, navigate to it now
```
cd meltano-ga4-cqf
```
 2. Once inside of the `meltano-ga4-cqf` repository, run the following command to trigger the ***New Vs Returning Conversions*** pipeline
```
meltano elt tap-google-analytics-v4-sourcemedium-campaign-sessions-us target-csv --state-id=ga4-sourcemedium-campaign-sessions
```