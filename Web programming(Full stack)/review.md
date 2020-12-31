> 201216_1일차

​

http / https 차이점 

https는 서버와 클라이언트 사이에 주고받는 정보를 암호화하여 처리

​
-----------------------------------------
> 201223_2일차

​

1. 우리가 흔히 브라우저 탐색을 할 때 스크롤을 하거나, 어떤 것을 클릭하면서 화면의 위치를 바꿀 때, 브라우저는 어떻게 다시 화면을 그릴까요?

2. 위에서 표현된 그림처럼 다시 렌더링 되지 않을까요? 

​

1-1. Render Tree는 HTML의 변환된 파일인 DOM Tree와 CSS의 변환된 파일인 CSS Tree 파일을 합친 결과물입니다. 이는 우리가 보는 Web Page를 구성하는 구성요소이다. 즉, 브라우저를 통해서 Web Page에서 스크롤이나 탐색을 할 때 브라우저는 Web Page 구성요소인 Render Tree를 저장하고 있다가, 정보만 가져와서 Paint만 하면 된다.

2-1. 따라서 다시 렌더링되지 않는다.

​
HTML을 해석해서 DOM Tree를 만들고, CSS를 해석해서 역시 CSS Tree(CSS Object Model)을 만듭니다. 

이 과정에서 Parsing 과정이 필요하며 토큰 단위로 해석되는 방식은 일반적인 소스코드의 컴파일 과정이라고 보시면 됩니다.

DOM Tree와 CSS Tree, 이 두 개는 연관되어 있으므로 Render Tree로 다시 조합됩니다.

이렇게 조합된 결과는 화면에 어떻게 배치할지 크기와 위치 정보를 담고 있습니다.

이후에 이렇게 구성된 Render Tree정보를 통해서 화면에 어떤 부분에 어떻게 색칠을 할지 Painting과정을 거치게 됩니다.

​

HTML 문서 안에 HTML태그뿐 아니라 CSS, JavaScript코드가 존재합니다.

JavaScript 코드는 body 태그 닫히기 전에 위치하는 것이 렌더링을 방해하지 않아도 좋고, css코드는 head 안에 위치해서 렌더링 처리 시에 브라우저가 더 빨리 참고할 수 있게 하는 것이 좋습니다.

​

​

웹서버

웹 서버의 가장 중요한 기능은 클라이언트(Client)가 요청하는 HTML 문서나 각종 리소스(Resource)를 전달하는 것입니다.

​

HTML 태그

    <nav> 네이게이션 영역

    <ul>이란 unlisted? 순서가 상관없는 리스트


---------------------------------------

> 201229 3일차

JDK, Eclipse, apache Tomcat 설치 및 환경 설정 완료

--------------------------------
> 201230 4일차 

#### 5-1 서블릿이란?

자바 웹 어플리케이션의 구성요소 중 동적인 처리를 하는 프로그램의 역할입니다.

서블릿을 정의해보면 서블릿(servlet)은 WAS에 동작하는 JAVA 클래스입니다. 

서블릿은 HttpServlet 클래스를 상속받아야 합니다.

서블릿과 JSP로부터 최상의 결과를 얻으려면, 웹 페이지를 개발할 때 이 두 가지(JSP, 서블릿)를 조화롭게 사용해야 합니다.

예를 들어, 웹 페이지를 구성하는 화면(HTML)은 JSP로 표현하고, 복잡한 프로그래밍은 서블릿으로 구현합니다.

#### 5-2 Servlet 작성법

tlqkf 날라갔어..........

서블릿 2.5에서는 web.xml 선택?을 필수적으로 해줘야한다. 서블릿 3.1에서는 어노테이션 작업이 자동으로 된다.////////.........?........

#### 5-3 Servlet 라이프 싸이클
service(request, response) 메소드

HttpServlet의 service메소드는 템플릿 메소드 패턴으로 구현합니다.

클라이언트의 요청이 GET일 경우에는 자신이 가지고 있는 doGet(request, response)메소드를 호출
클라이언트의 요청이 Post일 경우에는 자신이 가지고 있는 doPost(request, response)를 호출
 
LifecycleServlet 수정 실습

Service(request, response)메소드 주석처리
HttpServlet의 doGet(request, response)메소드 오버라이딩
HttpServlet의 doPost(request, response)메소드 오버라이딩

#### 1번 프로젝트 시작

.....밑바닥에서 


엘리먼트가 배치되는 방식 (position:static, relative, absolute)

엘리먼트 배치가 순서대로만 위아래로 또는 좌우로 흐르면서 쌓이기만 하면, 다양한 배치를 하기 어렵습니다.

position 속성을 사용하면 상대적/절대적으로 어떤 위치에 엘리먼트를 배치하는 것이 수월합니다.

 

1. position 속성으로 특별한 배치를 할 수 있습니다.

position 속성은 기본 static입니다.

그냥 순서대로 배치됩니다.

 

2. absolute는 기준점에 따라서 특별한 위치에 위치합니다.

top / left / right / bottom 으로 설정합니다.

기준점을 상위엘리먼트로 단계적으로 찾아가는데 static이 아닌 position이 기준점입니다.

 

3. relative는 원래 자신이 위치해야 할 곳을 기준으로 이동합니다.

top / left / right / bottom로 설정합니다.

 

4 fixed는 viewport(전체화면) 좌측, 맨 위를 기준으로 동작합니다.

code 바로가기


엘리먼트가 배치되는 방식 (margin:10px)

margin으로 배치가 달라질 수 있습니다.

margin은 위 / 아래 / 좌 / 우 엘리먼트와 본인 간의 간격입니다.

따라서 그 간격만큼 내 위치가 달라집니다.


엘리먼트가 배치되는 방식 (float:left)

float 속성으로 원래 flow에서 벗어날 수 있고 둥둥 떠다닐 수 있습니다.

일반적인 배치에 따라서 배치된 상태에서 float는 벗어난 형태로 특별히 배치됩니다.

따라서 뒤에 block엘리먼트가 float 된 엘리먼트를 의식하지 못하고 중첩돼서 배치됩니다.

code 바로가기

float의 속성은 이런 특이성 때문에 웹사이트의 전체 레이아웃 배치에서 유용하게 활용됩니다.


엘리먼트가 배치되는 방식 (box-model)

블록 엘리먼트의 경우 box의 크기와 간격에 관한 속성으로 배치를 추가 결정합니다.

margin, padding, border, outline으로 생성되는 것입니다.

code 바로가기

box-shadow 속성도 box-model에 포함지어 설명할 수 있습니다.

box-shadow는 border 밖에 테두리를 그릴 수 있는 속성입니다.


엘리먼트의 크기

block엘리먼트의 크기는 기본적으로는 부모의 크기만큼을 가집니다.

예를 들어, width:100%는 부모의 크기만큼을 다 갖는 것과 같습니다.


box-sizing과 padding

padding 속성을 늘리면 엘리먼트의 크기가 달라질 수 있습니다.

box-sizing 속성으로 이를 컨트롤 할 수 있습니다.

box-sizing 속성을 border-box로 설정하면 엘리먼트의 크기를 고정하면서 padding 값만 늘릴 수 있습니다.

code 바로가기

 

layout 구현방법은?

전체 레이아웃은 float를 잘 사용해서 2단, 3단 컬럼 배치를 구현합니다.

최근에는 css-grid나 flex 속성 등 layout을 위한 속성을 사용하기 시작했으며 브라우저 지원범위를 확인해서 사용하도록 합니다.

특별한 위치에 배치하기 위해서는 position absolute를 사용하고, 기준점을 relative로 설정합니다.

네비게이션과 같은 엘리먼트는 block 엘리먼트를 inline-block으로 변경해서 가로로 배치하기도 합니다.

엘리먼트안의 텍스트의 간격과 다른 엘리먼트간의 간격은 padding과 margin 속성을 잘 활용해서 위치시킵니다.
