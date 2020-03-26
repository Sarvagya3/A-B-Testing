### Challenge Description

Company XYZ is a worldwide e-commerce site with localized versions of the site.
A data scientist at XYZ noticed that Spain-based users have a much higher conversion rate than any other Spanish-speaking country.
The Spain and LatAm country manager suggested that one reason could be translation. All Spanish-speaking countries had the same translation of the site which was written by a Spaniard. Therefore, they agreed to try a test where each country would have its own translation written by a local. That is, Argentinian users would see a translation written by an Argentinian, Mexican users written by a Mexican and so on. Obviously, nothing would change for users from Spain.

After they run the test however, they were really surprised because the test was negative. That is, it appeared that the non-highly localized translation was doing better!

### Task at hand:

1. Confirm that test is actually negative. I.e., the old version of the site with just one translation across Spain and LatAm performs better

2. Explain why that might be happening. Are the localized translations really worse?

3. If you identified what was wrong, design an algorithm that would return FALSE if the same problem is happening in the future and TRUE if everything is good and results can be trusted.

### Data:
The 2 tables are:

**test_table - general information about the test results**

Columns:
user_id : the id of the user. Unique by user. Can be joined to user id in the other table. For each user, we just check whether conversion happens the first time they land on the site since the test started.

date : when they came to the site for the first time since the test started

source : marketing channel: Ads, SEO, Direct. Direct means everything except for ads and SEO, such as directly typing site URL on the 

browser, downloading the app w/o coming from SEO or Ads, referral friend, etc.

device : device used by the user. It can be mobile or web

browser_language : in browser or app settings, the language chosen by the user. It can be EN, ES, Other (Other means any language except for English and Spanish)

ads_channel : if marketing channel is ads, this is the site where the ad was displayed. It can be: Google, Facebook, Bing, Yahoo ,Other. If the user didn’t come via an ad, this field is NA

browser : user browser. It can be: IE, Chrome, Android_App, FireFox, Iphone_App, Safari, Opera

conversion : whether the user converted (1) or not (0). This is our label. A test is considered successful if it increases the proportion of users who convert.

test : users are randomly split into test (1) and control (0). Test users see the new translation and control the old one. For Spain-based users, this is obviously always 0 since there is no change there.


**user_table - some information about the user**

Columns:
user_id : the id of the user. It can be joined to user id in the other table

sex : user sex: Male or Female

age : user age (self-reported)

country : user country based on ip address
