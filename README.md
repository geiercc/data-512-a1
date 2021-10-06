# data-512-a1

The goal of this project was to show a time series visualization of the number of English Wikipedia views on both the desktop site and the mobile site or application. 

The source data is licensed under the CC-BY-SA 3.0 and GFDL licenses. 
The Wikimedia Foundation REST API terms of use are available at this link: https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions

The API endpoints can be found here:
1. Legacy Pagecounts API - https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end
2. Pageviews API - https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end

The API documentation can be found here:
1. Legacy Pagecounts API - https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts
2. Pageviews API - https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews

Code from this notebook, which licensed under CC0, was also used in this analysis to get data from the API endpoints: 
https://public.paws.wmcloud.org/User:Jtmorgan/data512_a1_example.ipynb

The final analysis csv file procuded is titled en-wikipedia_traffic_200712-202108.csv and has the following fields
1. year (format: YYYY)
  a) This field contains the year value for the number of views 
2. month (format: MM)
  a) This field contains the month value for the number of views
3. pagecount_all_views (format: int value for number of views)
  a) This field contains the total number of views across mobile and desktop sites for the legacy Wikipedia format
4. pagecount_desktop_views (format: int value for number of views)
  a) This field contains the number of views on the desktop site for the legacy Wikipedia format
5. pagecount_mobile_views (format: int value for number of views)
  a) This field contains the number of views on the mobile site for the legacy Wikipedia format
7. pageview_all_views (format: int value for number of views)
  a) This field contains the total number of views across mobile and desktop sites for the updated Wikipedia format
9. pageview_desktop_views (format: int value for number of views)
  a) This field contains the number of views on the desktop site for the updated Wikipedia format
11. pageview_mobile_views (format: int value for number of views)
  a) This field contains the number of views on the mobile site and the mobile app for the updated Wikipedia format

Special considerations

It should be noted that data from the Pageview API does not include spiders/crawlers, but the data from the Pagecounts API (or Legacy API) does contain this as there is no option to filter these out. 
Mobile views from the Pagecounts API contains views from both the mobile site and the mobile app, while mobile views from the Pagecounts API is coming solely from the mobile site.
The naming convention for the json files outputed was "apiname_accesstype_firstmonth-lastmonth.json" 
Months with 0 pageviews for a given access method (e.g. desktop-site, mobile-app) were listed as 0 and were not graphed in the final png output.
Additionally, there is about 1 year of overlapping traffic data between the two APIs which are both graphed in this analysis.

