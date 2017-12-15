---
layout: post
title: HttpServletRequest
category : 기타
tags: [기타]
---


##HttpServletRequest 정리


###클라이언트 IP 등의 정보를 가져오거나, 쿠키, 헤더, GET/POST로 전송한 값을 가져오는데 주로 사용하는 것이 바로 Request입니다.

###Features
 - 이 Request 객체는 javax.servlet.http 패키지에 속한 HTTPServletRequest 인터페이스로서 javax.servlet.ServletRequest 인터페이스에서 상속을 받았습니다.
 - Protocol : <%=request.getProtocol()%>
 - Secure Channel : <%=request.isSecure()%>
 - Scheme : <%=request.getScheme()%>
 - Request's URI : <%=request.getRequestURI()%>
 - Context Path : <%=request.getContextPath()%>
 - Servlet Path : <%=request.getServletPath()%>
 - Method : <%=request.getMethod()%>
 - Session ID : <%=request.getRequestedSessionId()%>
 - Session ID from Cookie : <%=request.isRequestedSessionIdFromCookie()%>
 - Session ID from URL : <%=request.isRequestedSessionIdFromURL()%>
 - Session ID is still valid : <%=request.isRequestedSessionIdValid()%>
 - 그리고 다음은 Header 정보를 보는 방법입니다. 
   <%
 Enumeration eHeader = request.getHeaderNames();
 while (eHeader.hasMoreElements()) {
  String hName = (String)eHeader.nextElement();
  String hValue = request.getHeader(hName);

  out.println(hName + " : " + hValue);
 }
  %>

Request 객체를 통해서 쿠키 정보를 보는 방식이구요~
<%
 Cookie cookies[] = request.getCookies();
 for (int i=0; i < cookies.length; i++) {
  String name = cookies[i].getName();
  String value = cookies[i].getValue();

  out.println(name + " : " + value);
 }
%>

HTML 폼을 통해 넘어온 데이터를 받는 부분입니다. 
<%
 Enumeration eParam = request.getParameterNames();
 while (eParam.hasMoreElements()) {
  String pName = (String)eParam.nextElement();
  String pValue = request.getParameter(pName);

  out.println(pName + " : " + pValue);
 }
%>

미리 설정한 attribute를 가져오는 부분이구요..
<%
 Enumeration eAttr = request.getAttributeNames();
 while (eAttr.hasMoreElements()) {
  String aName = (String)eAttr.nextElement();
  String aValue = request.getHeader(aName);

  out.println(aName + " : " + aValue);
 }
%>
 - 클라이언트의 정보를 보여줍니다.
    Local IP : <%=request.getLocalAddr()%>
    Local Name : <%=request.getLocalName()%>
    Local Port : <%=request.getLocalPort()%>
 - 지역 정보입니다. 대부분 한국을 의미하는 ko가 나올 것 같네요..
    Locale : <%=request.getLocale()%>
 - 서버의 기본 정보(IP, Name, Port)를 보여줍니다. 
    Local IP : <%=request.getLocalAddr()%>
    Local Name : <%=request.getLocalName()%>
    Local Port : <%=request.getLocalPort()%>
 
    

    
  