---
layout: post
title: 서버 배포
category : Intro
tags : [기타]
---


# 서버 배포 
## linux centos  7 기준 
### 클라우드 서버에 프로젝트 올려보기
#### 2017.11.22
#####- linux 서버에 톰캣, jdk를 설치한다. (보통 /opt/newFile, grep ./etc/*-release centos 버전 확인)  -> 드래그 scp 경로 /opt/newFile

#####- gtar xvzf apaache****.tar.gz(tar파일 압축 풀기)

#####- mv apache-tomcat-8.5.*  tomcat(파일 이름이 길어서 tomcat으로 바꾸기)

#####- cd ../../ 두개 이전의 디렉토리로 이동 cd ../webapps 한개 전 디렉토리에있는 webapps

#####- tomcat의 JAVA_HOME을 콘솔마다 지정해줘야 함 (export JAVA_HOME=/opt/newFile/java)

#####- bin 디렉토리에 있는 상태에서 ./startup.h 하면 톰캣 실행 ./shutdown.sh 하면 톰캣 종료

#####- tomcat/conf/server.xml을 vim server.xml을 통해 들어가면 Connector port=8080 redirectPort=8443 등을 볼 수 있음

#####- vim 에서 :q!하면  수정된것을 적용하지 않고 강제 종료 가능

#####- tomcat/webapps에 있는 기본폴더를 rm -rf ./* 를 통해 지운다

#####- tomcat/webapps에 프로젝트 war파일을 올린다.

#####- tomcat을 다시시작한다.(tomcat에 있는 상태라면 bin/startup.sh)