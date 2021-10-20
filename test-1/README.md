# KPIS Dashboard task 
 
Submitted repo code should be in PHP Laravel 7, with simple blade views. 

Sample DB with schema is attached, and please feel free to seed it with more data to better test your setup. 

So I’ll leave the presentation of the stats to you because I’d be accessing how you handle UX in your development. This coding task accessing your coding skills and your UX approach to solving problems. 

There are three tables in the sample SQL
- Users: when users sign up, they’re put here 
- Purchases : when a transaction happens, it goes here.
- Products: when a product is created it goes here 

Feel free to suggest some recommendations for DB relationships or structure if you feel the existing structure limits the implementation of the task. 

Task details: 

At Selar, there are a few KPIs that matter to us and we monitor these KPIs both weekly and monthly.  
- Transactions volume by currency and profit : total amount of sales made in each currency and how much profit we made - this is gotten from the `
- New users: a count of all the new users that signed up.
- New products added: new products added to the table 
- New merchants : A merchant is defined as a user that has created at least one product, so a new merchant is a user that added their first product in that particular time frame. 
- Unique sellers: number of merchants with at least one sale in a particular time frame.
- New sellers: number of merchants that made their first sale in a particular time frame 
- Median average: rough calculation of the average Naira value of all merchant’s sales in a particular time frame. This gives a picture of the the average value a merchant sells in any given time frame. ***This is not a huge priority and mildly complex so feel free to not do this if you’re done with every other*** 



Key columns on each table 

Purchases 
- transaction_date (UTC) - UTC date the transaction was completed 
- merchant_id (foreign key ID from users table) 
- selar_profit - how much we made from the transaction 
- total_amount - total amount of the purchase 
- currency - currency of the purchase 
- status (paid, pending, failed) - paid as successful transactions 
- merchant_commission - the merchant’s profit 

Products  
- created_at (UTC) -  date the transaction was created
- merchant_id (foreign key ID from users table) 

Users  
- Id - User ID 
- created_at (UTC) -  date the user signed up


Things to look out for: 
- Dates in the DB are in UTC, so the timezone is important when displaying results based on date filters 
- KPIs are to be presented in two main forms: 
    - A date filtered version of all KPIs 
    - A historical monthly view of all KPIS - now this might be super tough, so if you can simply achieve the simple date filtered version above, that would be sufficient. The importance of this is to have a simple view of all the monthly data to make comparisons. 
- Presentation of the KPIs is key, I’d love to see how you believe is best to present this data, but don’t overthink it or go overboard with any UI, a simple HTML and CSS view is fine, I don’t think you need any JS or chart, except you think it’s needed. Remember, making the data understandable is what’s important. 



