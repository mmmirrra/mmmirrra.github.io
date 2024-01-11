---
layout: post
title:  "React: axios api response is a list"
date:   2023-08-02 09:00:00 +0900
categories: [React]
---

When you receive React's axios api responses as a list, check them as follows.   
   
`response.data[0]` : the first array of responses.   
`response.data[0].usrNo` : the value name of the first array.   
   
```react
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
```


<img src="https://th.bing.com/th?id=ORMS.940b39079df29728d2d4883226a4a05f&pid=Wdp&w=300&h=156&qlt=90&c=1&rs=1&dpr=1&p=0" />


![대체 텍스트](/_assets/profile.png)
![대체 텍스트](_assets/profile.png)
![대체 텍스트](https://github.com/mmmirrra/mmmirrra.github.io/blob/main/_assets/excelTool1.png)