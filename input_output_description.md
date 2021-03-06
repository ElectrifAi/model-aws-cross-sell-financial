# Input/Output Description

- Input: A zip file containing 7 comma separated csv files. Reference file: sample.zip
- Details for each csv file:
    - scoring_date.csv (required)
        - Required columns:
            - scoring_date: scoring date for caculating signals and generate main table, format 'YYYY-MM-DD', eg: '2020-01-01'
    - customer_profile.csv (required)
        - Required columns: 
            - cust_id: customer id
            - enroll_cust_flag: whether a customer enrolled
            - income: income
            - gender: gender
            - phone_id: contact phone id
            - email_id: email id
            - address_id: address id
            - age: age
            - contract_cnt: count of contracts
            - tenure: tenure
    - purchase_trans.csv (required)
        - Required columns: 
            - cust_id: customer id
            - purchase_date: purchase date
            - product_sku: product sku
            - product_name: product name 
            - purchase_code: purchase code to indicate purchase status 
            - purchase_cnt: count of purchase
            - price: purchase price 
    - campaign_info.csv (required)
        - Required columns: 
            - campaign_id: campaign id
            - channel: channel
            - campaign_date: campaign date
            - product_name: product name targeted for campaign
    - sales_call_activity.csv (required)
        - Required columns: 
            - cust_id: customer id
            - campaign_id: campaign id assosiated to call channel
            - phone_id: phone id
            - product_name: product name targeted for campaign
            - call_start_time: call start time
            - call_end_time: call end time 
            - call_type: call type (inbound,outbound)
    - em_campaign.csv (required)
        - Required columns: 
            - cust_id: customer id
            - email_id: email id
            - campaign_id: campaign id assosiated to EM channel
            - product_name: product name 
            - em_send_date: email send date
            - em_open_date: email open date
            - em_click_date: email click date
    - dm_campaign.csv (required)
        - Required columns: 
            - cust_id: customer id
            - address_id: address id
            - campaign_id: campaign id assosiated to DM channel
            - product_name: product name 
            - em_send_date: dm send date
    - Note: if end user do not have optional tables, empty CSV with identical columns should be generated to replace missing optional table.
    
- Output: JSON list of objects containing 'cust_id'  with original order, and one more column added named 'Score' which contains model's prediction of Cross Sell likelihood scores of account. Reference file: sample.zip.out

