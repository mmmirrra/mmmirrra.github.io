---
layout: post
title:  "REACT: 리스트에서 필터로 조건에 해당하는 것만 보여주는 방법"
date:   2023-07-28 15:56:04 +0900
categories: jekyll update
---
const sendListData = dbListData.filter(v => ((Number(v.buyDt) > Number(start) && Number(v.buyDt) < Number(end)) || (Number(v.buyDt) === Number(start) || Number(v.buyDt) === Number(end))) && v.buyPaymentCode === buyPaymentCode);
