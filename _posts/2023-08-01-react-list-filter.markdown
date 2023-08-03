---
layout: post
title:  "REACT: To display only the items that meet the filter criteria in the list"
date:   2023-08-01 09:00:00 +0900
categories: react
thumbnail: /assets/profile.png
---

`dbListDate` is the source list.   
`buyDt` is the date to search.   
`start` is the start date.   
`end` is the end date.   

Filters dates that are greater than the start date and less than the end date, or dates that are equal to the start date or the end date.   
Filter items with the same `buyPaymentCode`.   

{% highlight react %}
const sendListData = dbListData.filter(
    v => (
            (Number(v.buyDt) > Number(start) && Number(v.buyDt) < Number(end)) 
            || 
            (Number(v.buyDt) === Number(start) || Number(v.buyDt) === Number(end))
         )
         && v.buyPaymentCode === buyPaymentCode
);
{% endhighlight %}
