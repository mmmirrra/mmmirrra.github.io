---
layout: post
title:  "REACT: To display only the items that meet the filter criteria in the list"
date:   2023-08-01 09:00:00 +0900
---
const sendListData = dbListData.filter(v => ((Number(v.buyDt) > Number(start) && Number(v.buyDt) < Number(end)) || (Number(v.buyDt) === Number(start) || Number(v.buyDt) === Number(end))) && v.buyPaymentCode === buyPaymentCode);
