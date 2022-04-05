---
layout: post
title: React-Router
subtitle: React Router
categories: React
tags: [TIL, React]
---

![image](https://user-images.githubusercontent.com/73337811/161745898-5767d7a2-9d59-44a8-81d6-6407c562aa89.png)


# React-Router

`
초반 개념부터 확실히 다질 필요가 있어서 리액트 기초부터 다시 공부하기로 마음 먹었다.
유튜브의 리액트 기초강의들을 다시 볼까, 했지만
https://mjn5027.tistory.com/ 코딩스토리님의 블로그 글이 잘 정리되어있는 걸 보고 글과 예제를 통해 기초개념을 다시 익히고 있다.
이글 역시 https://mjn5027.tistory.com/30 요 글을 보고 작성하는 글이다. 감사합니다 :)
`

## React Router
리액트는 spa방식으로 하나의 페이지에서 상황에 따라 필요 데이터만을 load해준다. React-Router는 url의 값에 따른 page를 load해서 보여주는 기능을 맡고 있다.

```javascript

<>
<BrowserRouter>
    <Route path="/" exact component={Home} />
    <Route path="/about" component={About} />
    <Route path="/memo" component={Memo} />
</BrowserRouter>  
</>

```

Route 태그는 반드시 Router 계열 태그 안에 작성해야하고,
url 경로를 설정해준다.
ex) path="/memo" component={Memo}인 경우,
path가 /memo인 url이 호출될 경우 Memo 컴포넌트를 할당해 load 해준다.

Route 태그는 기본적으로 props에 match, history, location을 넘겨줘서 호출되는 컴포넌트에서 history를 인자로 받아낼 수 있다.

그리고 history.goBack()
go(), blick(), replace() 들과 함께 history가 가지고 있는 자체 함수라고 한다.
