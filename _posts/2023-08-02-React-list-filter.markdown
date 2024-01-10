---
layout: post
title:  "React: To only display list items that meet the filter criteria"
date:   2023-08-02 10:00:00 +0900
categories: [React]
---

Filters dates that are greater than the start date and less than the end date, or dates that are equal to the start date or the end date.   
Filter items with the same 'buyPaymentCode'.   
   
`dbListDate` : the source list.   
`buyDt` : the date to search.   
`start` : the start date.   
`end` : the end date.   

```react
const sendListData = dbListData.filter(
    v => (
            (Number(v.buyDt) > Number(start) && Number(v.buyDt) < Number(end)) 
            || 
            (Number(v.buyDt) === Number(start) || Number(v.buyDt) === Number(end))
         )
         && v.buyPaymentCode === buyPaymentCode
);
```
