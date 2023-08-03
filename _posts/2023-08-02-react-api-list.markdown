---
layout: post
title:  "React: AXIOS API response is a list"
date:   2023-08-02 09:00:00 +0900
categories: react
thumbnail: /assets/profile.png
---

When you receive React's AXIOS API responses as a list, check them as follows.   

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
