[theory-study]: https://github.com/ohchangyeol/bitcamp-theory-study "theory study"
[aiacademy]: https://goai.co.kr "AIA aiacademy"

# ๐ Model1 -> Model2 Architecture ! 

[์๋ฐ๊ธฐ๋ฐ Web Platform Service(RestFul Server) ๊ตฌ์ถ Web, App ๊ฐ๋ฐ์ ์์ฑ๊ณผ์ ][aiacademy]๋ฅผ ๋ค์ผ๋ฉฐ  
MVCํจํด์ ๊ฐ๋ฐ ๋ฐฉ์์ ์์๋ณด์๋ค.

[๊ฐ์ ์ ๋ฆฌ][theory-study]์ ํด๋น๋๋ source.

## Overview
- ### MVC Pattern
    MVC ํจํด์ **Model, View, Controller**์ ์๊ธ์๋ฅผ ๋ฐ์ ๋ถ์ธ ์ํํธ์จ์ด ๋์์ธ ํจํด์ด๋ค.   

    **Model** : ๋ฐฑ๊ทธ๋ผ์ด๋์์ ๋์ํ๋ ๋ก์ง ์ฒ๋ฆฌ  
    **View** : ์ฌ์ฉ์๊ฐ ๋ณด๊ฒ ๋  ๊ฒฐ๊ณผ ํ๋ฉด์ ์ถ๋ ฅ  
    **Controller** : ์ฌ์ฉ์์ ์๋ ฅ์ฒ๋ฆฌ์ ํ๋ฆ์ ์ด ๋ด๋น  

    MVCํจํด์๋ **Model1**๋ฐฉ์๊ณผ **Model2** ๋ฐฉ์์ด ์์ผ๋ฉฐ ์ด๋ JSP๋ก ๊ตฌ์ฑํ  ์ ์๋ ์น ์ดํ๋ฆฌ์ผ์ด์์ ์ํคํ์ฒ์์ ๋ก์ง๊ณผ ์ถ๋ ฅ์ ๋ชจ๋์ฒ๋ฆฌํ๋์ง(Model1), JSP์์๋ ์ถ๋ ฅ๋ง ์ฒ๋ฆฌํ๋์ง(Model2)์ ๋ฐ๋ผ ๋ถ๋ฅ๋๋ค.
- ### Model1 Pattern
    Clientํํ ์์ฒญ์ ๋ฐ๊ฒ ๋๋ฉด Java Bean(DAO)์ ํธ์ถํ์ฌ ๋์ ์ธ ํ์ด์ง๋ฅผ ๊ตฌํํ๋ ๊ตฌ์กฐ.  

    ![011Model1](https://user-images.githubusercontent.com/48302622/153268123-b247e2d4-701f-4931-84c6-c61725bd063e.jpg)

    #### ํน์ง
    - ๊ฐ๋ฐ ์๋๊ฐ ๋น ๋ฅด๋ค.
    - presentation logic๊ณผ business logic์ด ํผ์ฌ๋์ด ์๋ค.
    - JSP๊ฐ ๋ณต์กํด์ ธ ์์ด ์ ์ง๋ณด์๊ฐ ์ด๋ ต๋ค (front-end์ back-end์ ์ญํ ๋ถ๋ด์ด ์ด๋ ต๋ค.)

    #### ๊ฐ์  ๋ฐฉํฅ 
    2layer architecture๋ฅผ ํ์ฉํด presentation logic๊ณผ business logic์ ๋ถ๋ฆฌ ํ๋ค.
    
- ### Model2 Pattern Refactoring01
        
    Servlet์ ํ์ฉํ์ฌ presentation logic๊ณผ business logic์ ๋ถ๋ฆฌ ํ๋ ๊ตฌ์กฐ

    ![012Model2](https://user-images.githubusercontent.com/48302622/153270080-eddf3d6c-5067-41a3-b93a-a9c5f887ae70.png)

    #### ํน์ง
    - ๊ฐ๋ฐ ํ์ฅ์ด ๋น๊ต์  ์ฉ์ดํ๋ค.
    - ์ ์ง๋ณด์๊ฐ ํธํ๋ค. 
    - ์์กด์ฑ์ด ๋๋ค.
    - Controller์ ์ญํ์ด ๋ง๋ค.
    
- ### Model2 Pattern Refactoring02

    ๊ณ์ธต ๊ตฌ์กฐ๋ฅผ ๋๋  Client์ ์์ฒญ์ ๋ฐ๋ผ ๋งคํ๋๋ Controller์ ์์์ ์ ๋ฌ ํ๋ ๊ตฌ์กฐ

    ![013Model2](https://user-images.githubusercontent.com/48302622/153270101-c0cecb3c-efb5-4b3e-a2c2-db133342de99.png)

    #### ํน์ง
    - Mapping์ ํตํด controller์ ์ญํ์ด ๋ชํํด์ ธ ์ ์ง๋ณด์๊ฐ ํธํ๋ค.
    - View์์ ์์กด์ฑ

- ### Model2 Pattern Refactoring03

    **Spring MVC pattern์ ์ค์ฌ**  
    DispatcherServlet์ ์ญํ์ด ๋จ์ผ ์ธ์์ ์ด ๋๋ฉฐ ์์ฒญ์ ๋ฐ๋ผ ์ ํฉํ controller๋ก mappingํ๊ณ  resolver๋ฅผ ํตํด View์์ ์์กด์ฑ ๊ด๊ณ๋ฅผ ๋ฎ์ถ๋ค.

    ![014Model2](https://user-images.githubusercontent.com/48302622/153270103-5341a856-9e23-4bc8-a3c0-86dc45dbcc12.png)

        

    
## Tech Stack

 - <img src="https://img.shields.io/badge/Java-8-007396?style=flat&logo=java&logoColor=white"/></a>&nbsp;
 - <img src="https://img.shields.io/badge/Tomcat-7.0.55-F8DC75?style=flat&logo=Apache Tomcat&logoColor=F8DC75"/></a>&nbsp;

## review
Model1๋ถํฐ Model2 ๊น์ง์ ๋ฌธ์ ์ ์ ํ์ธ ํ์ฌ ๊ทธ ๋ฌธ์ ๋ฅผ ๊ฐ์ ํ๋ ๋ฐฉํฅ๊ณผ ์์กด์ฑ์ ๋ํด ๊ณต๋ถํ๊ฒ ๋์ด ๋ณด๋์๋ ์๊ฐ์ด์๋ ๊ฐ๋ค.  
Spring MVC Pattern์ ๊ณต๋ถ ํ๊ธฐ์ ์ ๊ฐ๋ฐ์ ์ญ์ฌ?๋ฅผ ๊ณต๋ถํ๋ ์๊ฐ๊ฐ์์ ๋๋ฌด ์ข์๊ณ  ์ด๋ค๋ฐฉ์์ผ๋ก ๊ตฌํ์ด ๋๊ณ  ๊ณ์ธต ๊ตฌ์กฐ๋ฅผ ํ์ํ์ฌ ๊ฐ๋ฐ ๋ฐฉํฅ์ฑ์ ์ก๊ฒ ๋์๋ค.