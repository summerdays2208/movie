## 영화소개 모바일 전용 웹페이지

### 🖥환경
- HTML
- CSS
- jQuery Mobile
- 카카오 API

### 🖼썸네일
![02-full](https://user-images.githubusercontent.com/83056872/128024702-65863a4e-2e00-4f9e-af5e-d6a5db0078c9.jpg)

### ✍중요
**영화소개 메뉴에서 구글차트 기능**

![구글차트](https://user-images.githubusercontent.com/83056872/128025982-76dc8aad-1536-423c-a3f2-e49c61be97cb.JPG)
```html
<script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
<script type="text/javascript">
google.charts.load('current', {'packages':['corechart']});
google.charts.setOnLoadCallback(drawChart);

function drawChart() {
    /* 데이터(배열) */
    var data = google.visualization.arrayToDataTable([
    ['평점', 'count'], /* 이부분은 화면에 나오지 않고 항목을 식별 */
    ['1점',     10],
    ['2점',      20],
    ['3점',  50],
    ['4점', 90],
    ['5점',    200]
    ]);

    var options = {
    title: '영화평점',
    pieHole: 0.4,
    /*is3D: true -- 이렇게 입력하면 3D차트 출력*/
    };
    var chart = new google.visualization.PieChart(document.getElementById('piechart'));

    chart.draw(data, options);
}
</script>
```

**영화관위치 메뉴에서 카카오 API**

![지도](https://user-images.githubusercontent.com/83056872/128026197-eaa39243-1dae-45c7-9bdf-414c690a5269.JPG)
```html
<script type="text/javascript" src="//dapi.kakao.com/v2/maps/sdk.js?appkey=1b64a4ecf605e8f55bd0b3f1be7b9340"></script>
    <script> 
        $(window).load(function() {
            var mapContainer = document.getElementById('kakaomap'), // 지도를 표시할 div 
            mapOption = { 
                    center: new daum.maps.LatLng(37.501779980567704, 127.02630826928426), // 지도의 중심좌표
                    level: 3 // 지도의 확대 레벨
                };

            var map = new daum.maps.Map(mapContainer, mapOption); // 지도를 생성합니다

            // 마커가 표시될 위치입니다 
            var markerPosition  = new daum.maps.LatLng(37.501779980567704, 127.02630826928426); 

            // 마커를 생성합니다
            var marker = new daum.maps.Marker({
                position: markerPosition
            });

            // 마커가 지도 위에 표시되도록 설정합니다
            marker.setMap(map);
        });
    </script>
```

**fotorama를 사용한 이미지 슬라이드**

![슬라이드](https://user-images.githubusercontent.com/83056872/128027341-4a2b0eca-8fd0-4b48-9fd7-3e6aa2b91cf0.JPG)
```html
<link href="https://cdnjs.cloudflare.com/ajax/libs/fotorama/4.6.4/fotorama.css" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/fotorama/4.6.4/fotorama.js"></script>
<div data-role="ui-content" class="bg-content">
    <div class="fotorama" data-nav="thumbs" data-loop="true" data-width="100%" data-autoplay="true"></div>
</div>
```

### 🏷URL
http://blanc22.dothome.co.kr/movie/
