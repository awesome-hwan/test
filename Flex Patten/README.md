# Flex Patten  

### 목적  

html의 마크업응용, flex 응용을 목적으로 하였다.  

### 기능  

> 반응형  

```  
@media screen and (max-width: 700px)
```  
미디어쿼리를 사용하여 700px을 전후로 화면구성을 변경  

> display: flex  

flex를 걸어줄 대상에대해 알고자함.  
order사용하여 위치 변경.


> module 비율  

```css
.module{
  width: 100%;
  height: 0;
  padding-bottom: 100%;
}
```  
위 패턴으로 가로: width, 세로: padding-bottom; 사용하여 모듈의 비율을 1:1, 2:1로 설정하였다.  



### Issue

```css  
/*.module__colwarpper는 display:flex*/
.module__colwarpper:nth-child(1) {
  order: 3;}
/*2번을 적지않으면 기본값이 0이되어 의도치않은 결과가 나오게된다.*/
.module__colwarpper:nth-child(2){
  order: 2;}
.module__colwarpper:nth-child(3){
  order: 1;}

```  

1과 3의 위치를 변경하려했을떄 2번의 order을 설정하지 않았을경우
order의 기본값은 0이 되어 2번이 맨 앞으로 오게되어 의도하지 않은 결과가 도출됨.  
