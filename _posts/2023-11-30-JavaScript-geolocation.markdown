---
layout: post
title:  "JavaScript: geolocation"
date:   2023-11-30 09:00:00 +0900
categories: [JavaScript]
---

### example   
`
<script>
    function getLocation() {
        let pos = document.getElementById('result');
        if (navigator.geolocation) {
            options = { 
                enableHighAccuracy: true,
                timeout: 5000,
                maximumAge: 5000 };
            navigator.geolocation.getCurrentPosition(
                myPosition, showError, options);
        } else {
            pos.innerHTML = "Geolocation을 지원하지 않습니다.";
        }
    };
    let watchId;
    function positionStart() {
        let pos = document.getElementById('result');
        if (navigator.geolocation) {
            options = { 
                enableHighAccuracy: true,
                timeout: 5000,
                maximumAge: 5000 };
            watchId = navigator.geolocation.watchPosition(
                myPosition, showError, options);
        } else {
            pos.innerHTML = "Geolocation을 지원하지 않습니다.";
        }
    };
    function positionStop() {
        navigator.geolocation.clearWatch(watchId);
        pos.innerHTML = "위치 추적이 중단 되었습니다.";
    };
    function myPosition(position) {
        let pos = document.getElementById('result');
        let now = new Date(position.timestamp);
        let lat = position.coords.latitude;
        let lng = position.coords.longitude;
        let acc = position.coords.accuracy;
        let heading = position.coords.heading;
        let speed = position.coords.speed;
        let msg = 
            "현재 시간: " + now.toLocaleString() + "<br />" +
            "현재 위치 (위도: " + lat + " 경도: " + lng + ")<br />" +
            "정확도: " + acc + "m<br />" +
            "진행방향: " + heading + "<br />" +
            "속도: " + speed + "<br />";
        pos.innerHTML = msg;
    };
    function showError(error) {
        let pos = document.getElementById('result');
        switch(error.code) {
            case error.PERMISSION_DENIED:
                pos.innerHTML = "권한이 없습니다."; break;
            case error.POSITION_UNAVAILABLE:
                pos.innerHTML = "위치 정보를 구할 수 없습니다."; break;
            case error.TIMEOUT:
                pos.innerHTML = "제한 시간을 초과하였습니다."; break;
            case error.UNKNOWN_ERROR:
                pos.innerHTML = "알 수 없는 오류가 발생하였습니다."; break;
            default: 
                pos.innerHTML = error.message;
        }
    };
</script>
<body>
    <div>
        <input type="button" onclick="getLocation()" value="위치 얻기" />
        <input type="button" onclick="positionStart()" value="위치 추적 시작" />
        <input type="button" onclick="positionStop()" value="위치 추적 정지" />
        <hr>
        <div id="result"></div>
    </div>
</body>
`
   
{% highlight html %}
<!DOCTYPE html>
<html>
    <head>
        <script>
            function getLocation() {
                let pos = document.getElementById('result');
                if (navigator.geolocation) {
                    options = { 
                        enableHighAccuracy: true,
                        timeout: 5000,
                        maximumAge: 5000 };
                    navigator.geolocation.getCurrentPosition(
                        myPosition, showError, options);
                } else {
                    pos.innerHTML = "Geolocation을 지원하지 않습니다.";
                }
            };
            let watchId;
            function positionStart() {
                let pos = document.getElementById('result');
                if (navigator.geolocation) {
                    options = { 
                        enableHighAccuracy: true,
                        timeout: 5000,
                        maximumAge: 5000 };
                    watchId = navigator.geolocation.watchPosition(
                        myPosition, showError, options);
                } else {
                    pos.innerHTML = "Geolocation을 지원하지 않습니다.";
                }
            };
            function positionStop() {
                navigator.geolocation.clearWatch(watchId);
                pos.innerHTML = "위치 추적이 중단 되었습니다.";
            };
            function myPosition(position) {
                let pos = document.getElementById('result');
                let now = new Date(position.timestamp);
                let lat = position.coords.latitude;
                let lng = position.coords.longitude;
                let acc = position.coords.accuracy;
                let heading = position.coords.heading;
                let speed = position.coords.speed;
                let msg = 
                    "현재 시간: " + now.toLocaleString() + "<br />" +
                    "현재 위치 (위도: " + lat + " 경도: " + lng + ")<br />" +
                    "정확도: " + acc + "m<br />" +
                    "진행방향: " + heading + "<br />" +
                    "속도: " + speed + "<br />";
                pos.innerHTML = msg;
            };
            function showError(error) {
                let pos = document.getElementById('result');
                switch(error.code) {
                    case error.PERMISSION_DENIED:
                        pos.innerHTML = "권한이 없습니다."; break;
                    case error.POSITION_UNAVAILABLE:
                        pos.innerHTML = "위치 정보를 구할 수 없습니다."; break;
                    case error.TIMEOUT:
                        pos.innerHTML = "제한 시간을 초과하였습니다."; break;
                    case error.UNKNOWN_ERROR:
                        pos.innerHTML = "알 수 없는 오류가 발생하였습니다."; break;
                    default: 
                        pos.innerHTML = error.message;
                }
            };
        </script>
    </head>
    <body>
        <div>
            <input type="button" onclick="getLocation()" value="위치 얻기" />
            <input type="button" onclick="positionStart()" value="위치 추적 시작" />
            <input type="button" onclick="positionStop()" value="위치 추적 정지" />
            <hr>
            <div id="result"></div>
        </div>
    </body>
</html>
{% endhighlight %}
