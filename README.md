# StarRatingTrend_Alerts

The dashboard is used to track the historical ratings of listings over the last 30 days and highlight any drops or increases for actionable insights. 
It replaces the need to receive email alerts for star rating changes via Santrykit with the high volume of email alerts, it can be difficult to keep track of changes or review historical data.
The dashboard displays the current number of reviews and star rating at both the Parent ASIN level and subcategory level (TBD) during a 31-day time period including current day.

* Recent Change: Change of star rating in the last 7 days, showing 'Drop' or 'Uplift'
  Max of Today to Today-6 > Today -7 then it is an uplift, Min of Today to Today-6 < Today -7 then it is a drop
  
* Long-term Change: Comparison between star rating in the last 7 days vs the last 30 days, showing 'Drop' or 'Uplift'
  A drop means in the long term we had higher star rating than in the recent 7 days
  An uplift means in the long term we had lower star rating than in the recent 7 days
  
* Long-term Delta: The value difference in Long-term change
  Value greater than 0.1 shows the rating change was bigger than the usual and BMs should take a look into the recent review commentaries
  if drop: The difference between Max of (Today-7 to Today-30) vs Max ( today to today-6)
  if uplift: The difference between Min of (Today-7 to Today-30) vs Min of (Today to Today-6)
  
* Recent Star Alert: Comparison between Today’s star rating and Today-7 day’s, showing 'Star Up' or 'Star Drop'
  If the rating is equal to any of them: 4.7, 4.2, 3.7, 3.2, 2.7, 2.2, 1.7, 1.2 - they just lost a visual half star in the past 7 days
  If the rating is equal to any of them: 4.8, 4.3, 3.8, 3.3, 2.8, 2.3, 1.8, 1.3 - they just gained a visual half star in the past 7 days
  
* Visual Star: The visual star rating on Amazon, affected by the star rating change
  4.8-5: 5 stars
  4.3-4.7: 4.5 stars
  3.8-4.2: 4 stars
  3.3-3.7: 3.5 stars
  2.8-3.2: 3 stars
  2.3-2.7: 2.5 stars
  1.8-2.2: 2 stars
  1.3-1.7: 1.5 stars
  Less than 1.3: 1 star

**PARTICULAR CASES**

Please note that if the ASIN is broken by Amazon or merged by brands:

 * The star rating may be blank on the current day and/or during the 30-day history. In such cases, the rating will be equal to the last-non-blank value of the previous three days.
 * There might be multiple rows for single parent ASIN, the rating will be the maximum (best) value for the rating.
