# KPIS Dashboard task 
 
The submitted repo code should be in PHP Laravel 7, with simple blade views (HTML & CSS). 

A sample DB with schema and demo data is also attached. Please feel free to seed it with more data to better test your setup. 

I’ll leave the presentation of the stats to you because I’d be accessing how you handle UX in your development. This coding task accessing your coding skills and your UX approach to solving problems. 

There are four tables in the sample SQL that matter
- Users: when users sign up, they’re put here 
- plans: plan names
- subscriptions : when a new user subscribes to a plan it goes here
- subscription_transactions: transaction record for a subscription goes here.

Feel free to suggest some recommendations for DB relationships or structure if you feel the existing structure limits the implementation of the task. 

Task details: 

At Selar, there are a few KPIs that matter to us when it comes to our subscriptions business https://selar.co/pricing and we monitor these KPIs both weekly and monthly.

NB: We have two main plans: pro & turbo, and we take subscriptions in two currencies today: NGN & USD, so for all KPIs, we have visibility on both plans and currencies, with the option to filter down any of the options to see more granular stats.

- New first time subscribers: a subscriber is a new first time subscriber when their subscription's table record is the first record ever in that time frame. 
- Number of new returning subscribers: a count of all the new subscribers in that time frame (where the subscription isn't the first one).
- Monthly view of profit earned: showing a breakdown of the quota earned from new first time subscribers, & subscription renewals (new subscriptions from existing subscribers and normal subscription autorenewals). along with the currency totals, you can add a count of the number of subscribers too.

### Nuances to the DB tables
- when a customer pays for a plan from the pricing page, it always creates a new subscription record and deactivates the other ones. So there's typically only one active subscription record in the subscriptions table for each user. When a subscription is active the is_active column is true. 
- As mentioned above about who is considered a new first time subscriber, if you're checking new first time subscribers in the month of Jan - May, a count will be if a customer had their first ever subscription record created in that time frame. If they had subscribed in December the last year, churned and just started a new subscription in Jan/Feb, that will not count as a new first time subscriber, it will just be a new subscription. 
- On the subscription transactions table, the type column can have two values: "new_subscription" or "subscription_renewal", a transaction with new_subscription means that's the transaction that started the subscription, and a subscription_renewal transaction is one for subsequent renewals of that transaction. 

Key columns on each table 

Plans 
- Id - Plan ID
- name - Name of the plan(Pro // Turbo)

Subscriptions  
- created_at (UTC) -  date the transaction was created (you can think of this as transaction completion date too)
- user_id - (foreign key ID from users table) 
- plan_id - (foreign key ID from plans table) 
- is_active - (foreign key ID from subscriptions table)  - if the subscription is currently active at that point in time
- currency, amount - subscription value 
- autorenewal - if autorenewal is enabled. This lets us calculate our expected MRR for the next month. I.e based on how many people have their autorenewals on. 

Subscription_transactions  
- created_at (UTC) -  date the transaction was created (you can think of this as transaction completion date too)
- user_id - (foreign key ID from users table) 
- plan_id - (foreign key ID from plans table) 
- subscription_id - (foreign key ID from subscriptions table)  - subscription the transaction is linked to.
- currency, amount - you get this.. 
- status (paid, pending, failed) - paid as successful transactions 
- type (new_subscription, subscription_renewal) - see above section for explanation
- status (paid, pending, failed) - paid as successful transactions 
- selar_profit - Selar profit from the transaction

Users  
- Id - User ID 
- created_at (UTC) -  date the user signed up


Things to look out for: 
- Dates in the DB are in UTC, so the timezone is important when displaying results based on date filters 
- KPIs are to be presented in two main forms: 
    - A date filtered version of all KPIs 
    - A historical monthly view of all KPIS 
- Presentation of the KPIs is key, I’d love to see how you believe is best to present this data, but don’t overthink it or go overboard with any UI, a simple HTML and CSS view is fine, I don’t think you need any JS or chart, except you think it’s needed. Remember, making the data understandable is what’s important. 

######Success! 



