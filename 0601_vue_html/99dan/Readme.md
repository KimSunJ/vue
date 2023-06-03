# Inflearn Vue 강의

## Vue 시작하기

```html
<!-- 개발버전, 도움되는 콘솔 경고를 포함. -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<!-- 상용버전, 속도와 용량이 최적화됨. -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

Vue나 React같은 Single page application을 만들 때에는 위의 주소가 바뀌지 않는다.
<br/>
하나의 페이지에서 무엇이든 해결해야한다.
<br/>
어떤 부분이 어떻게 바뀌는 가 와 그것을 데이터로서 관리하는 것이 제일 중요한 부분

```html
<div v-if="liked"></div>
<button v-on:click="onClickButton"></button>
<!-- v-on:click="" -->
<!-- v-는 뷰가 부모 태그에 통제하는 데이터나 메서드에 접근할 수 있다고 보면 된다. -->
```

vue의 강점: data만 관리해주면 화면은 알아서 vue가 바꿔준다.

```html
<script>
    const app = new Vue({
        el: '#root',
        // vue가 el 속성으로 데이터를 관리하는 중
        data: {
            변수명: false,
            // 데이터만 바꾸면 화면에서 vue가 알아서 수정해주는 것
        },
        methods: {
            onClickButton() {
                this.변수명 = true;
                // liked라는 속성을 (바뀌는 값) false에서 true로 변환해주는 것
                // 데이터만 관리한다.
            },
        },
    });
</script>
<!-- 이름을 꼭 지켜줘야하는 부분 el : '통제할 태그의 id', data : '관리하고 싶은 변수들을 넣는 것', methods: '어떻게 변경할 것인지' -->
```

```html
<!-- <div v-if="liked + 1 == 5"></div> 와 같이 자바스크립트 식 구문을 작성할 수 있다.-->
<div v-if=""></div>
<div v-else-if=""></div>
<div v-else-if=""></div>
<button v-else v-on:click=""></button>
<!-- v-if와 v-else는 동등한 형제면 적용을 받는다, 형제 태그면서 '인접'해야한다. | 형제 태그이지만 인접하지 않으면 v-if, v-else가 적용되지 않는다. -->
<button v-else v-on:click="onClickButton()"></button>
<!-- v-는 안에서 자바스크립트와 같이 사용할 수 있다. -->
```
