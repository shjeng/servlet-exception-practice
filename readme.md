<h1>스프링 MVC 2편 - 예외 처리와 오류 페이지</h1>

<h2>서블릿 예외 처리 - 필터</h2>

<strong>DispatcherType</strong>
* 고객이 처음 요청하면 'dispatcherType=REQEUST'이다. 이렇듯 서블릿 스펙은 실제 고객이 요청한 것인지, 서버가 내부에서 오류 페이지를 요청하는 것인지 'DispatcherType'으로 구분할 수 있는 방법을 제공한다.
* 'REQUEST': 클라이언트 요청
* 'ERROR': 오류 요청
* 'FORWARD': MVC에서 배웠던 서블릿에서 다른 서블릿이나 JSP를 호출할 때 'RequestDispatcher.forward(request, response);'
* 'INCLUDE': 서블릿에서 다른 서블릿이나 JSP의 결과를 포함할 때 'RequestDispatcher.include(request, response);'
* 'ASYNC': 서블릿 비동기 호출 

<p>
    'filterRegistrationBean.setDispathcerTypes(DispatcherType.REQUEST, DisPatcherType.ERROR);' <br>
    이렇게 두 가지를 모두 넣으면 클라이언트 요청은 물론이고, 오류 페이지 요 청에서도 필터가 호출된다. <br> 
    아무것도 넣지 않으면 기본 값이 'DispatcherType.REQUEST'이다. 즉 클라이언트의 요청이 있는 경우에만 필터가 적용된다. 특별히 오류 페이지 경로도 필터를 적용할 것이 아니면 기본 값을 그대로 사용하면 된다.
    <br>
    오류 페이지 요청 전용 필터를 적용하고 싶으면 'DispatcherType.ERROR'만 지정하면 된다.'
</p>
<hr>