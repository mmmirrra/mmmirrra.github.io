---
layout: post
title:  "Eclipse: shortcuts, key"
date:   2023-08-05 09:00:00 +0900
categories: Eclipse
thumbnail: /assets/profile.png
---

When you receive React's axios api responses as a list, check them as follows.   
   
`response.data[0]` is the first array of responses.   
`response.data[0].usrNo` is the value name of the first array.   

{% highlight react %}
const selecttestAxios = () => {
    axios.get('select')
    .then((response) => {
        console.log(response);
        console.log(response.data);
        console.log("response.data.un :: ", response.data[0].usrNo);
        console.log("response.data.id :: ", response.data[0].usrId);
        console.log("response.data.name :: ", response.data[0].usrNm);
        console.log("response.data.name :: ", response.data[0].usrPwd);
    });
}
{% endhighlight %}
