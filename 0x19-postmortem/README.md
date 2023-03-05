**My personal blog outage incident report**

Something was wrong with the network when files suddenly became inaccessible on my latest blog post.

**Issue Summary**

From 10:00 to 11:00 EAT all users where unable to access my personal blogs webpage. The service was down 100% due to the issue. The issue was caused by depolying of untested configuration of wordpress.

**Timeline (all times East Africa Time)**

09:55 AM: The sites is deployed
10:00 AM: Outage begins
10:20 AM: Users alerted me of the issue
10:45 AM: Figured out the cause
10:55 AM: Pushed updated configuration
11:00 AM: The site is back online

**Root Cause**

I added some configurations to my wordpress blog and mistyped php extentsion to .phpp. At 09:55 AM I pushed this untested code to github. Due to this issues the site responded with HTTP error code 500 for users.

**Resolution and recovery**

After the issue brought to my attention I've tried to debug by using different tools like strace. I came to conclusion that there is error in settings. I corrected the error the sites live again

**Corrective and Preventative Measures**

Testing before deployement
Using monitoring tools like datadog
![image](https://user-images.githubusercontent.com/104936934/222953374-025f2581-543d-4217-82fc-12723daeb3f0.png)
