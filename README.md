# movie_list
> 소개
멋쟁이 사자처림 프론트엔드스쿨2기 영화페이지 클론코딩을 SASS를 연습하기 위해 style설정을 SASS로만 구현했습니다.
> 프로젝트 이미지
> 프로젝트 주소

</br>

## 1. 제작 기간 & 참여 인원
- 2일 / 개인프로젝트

</br>

## 2. 사용 기술
#### `Front-end`
  - HTML/CSS
  - SASS

</br>

## 3. 핵심 기능


### font 및 line-height 모듈화
- @mixin을 사용하여 많이쓰는 font스타일을 모듈화하여 시간을 절약하고 사용하기 편하게 구현했다.

<details>
<summary><b>코드보기</b></summary>

```SCSS
@mixin font-style-13() {
    font-size: 13px;
    font-weight: 400;
    line-height: 19px;
}
@mixin font-style-14() {
    font-size: 14px;
    font-weight: 500;
    line-height: 20px;
}

@mixin font-style-16() {
    font-size: 16px;
    font-weight: 900;
    line-height: 23px;
}

@mixin font-style-24 {
    font-size: 24px;
    font-weight: 700;
    line-height: 28px;
}
````
</div>
</details>


  ### 미디어쿼리를 사용한 반응형페이지 
- 모바일,테블릿,PC일떄의 화면크기를 각 변수의 할당하여 @mixin으로 그리드박스의 column 갯수를 변화하시켜 UI가 꺠지지 않도록 구현했다.

<details>
<summary><b>코드보기</b></summary>

```SCSS
$breakpoint-mobile: 545px;
$breakpoint-tablet: 758px;
$breakpoint-desktop: 1024px; 
  
@mixin min {
    @media (max-width: #{$breakpoint-mobile}) {
        @content;
    }
}

@mixin mobile {
    @media (min-width: #{$breakpoint-mobile}) and (max-width: #{$breakpoint-tablet - 1px}) {
        @content;
    }
}

@mixin tablet {
    @media (min-width: #{$breakpoint-tablet}) and (max-width: #{$breakpoint-desktop - 1px}) {
        @content;
    }
}

@mixin desktop {
    @media (min-width: #{$breakpoint-desktop}) {
        @content;
    }
}
````
</div>
</details>
  
</br>
   
</br>

## 3. 회고
### 어려웠던점
  - SASS로만 Style를 구현하는게 쉽지 않았다.
  - 미디어쿼리를 SASS로 구현하는게 어려웠다. 
  - 하지만 SASS로 미디어쿼리를 구현하면 코드의 길이도 줄어들고 후에 유지보수에서도 변수만 변경해주면 해결 할 수 있어서 좋았다.

### 배운점
  - 기본적인 SASS 사용법을 익힐 수 있었따.
  - 자주 반복되는 스타일을 @mixin으로 모듈화하고 @include로 불러내어 효율성과 유지보수성을 높이는 방법을 배웠다.
  - CSS도 SASS를 변수를 설정하여 연산을 사용하거나 조건문을 사용하면 조건에 따른 스타일 지정도 할 수 있음을 배웠다.
