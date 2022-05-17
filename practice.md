### 📌 어플리케이션 추가

- python manage.py startapp app1
   
   - app1 이라는 이름의 어플리케이션을 생성합니다.

![image](https://user-images.githubusercontent.com/88240193/168726309-24c3c1d0-cf17-45f5-8372-4428d1d6b977.png)

- INSTALLED_APPS
    - settings.py 파일의 INSTALLED_APPS 에 'app1' 을 추가해서 새로운 어플리케이션을 등록합니다.


---

### MVC 패턴에 따른 어플리케이션 설계

- 생성한 "app1" 어플리케이션의 기능으로, HTML 파일이 우리 눈에 보여지도록 설계할 것 입니다.
- URL 요청에 따른 index.html 파일과 index2.html 파일의 내용이 화면에 보여지도록 구성해봅시다.

(html 파일들은 app1 폴더안의 templates 에 위치해 있습니다. )

![image](https://user-images.githubusercontent.com/88240193/168787891-99e5e45c-987f-4e42-bf05-59eba8b28679.png)


#### views.py : 렌더링

- HTML 페이지를 웹브라우저 화면에 보여주는 논리를 담당하는 함수를 views.py 파일에 구성합니다.


#### urls.py 

- urls.py 파일에서 특정 url 에 대한 요청이 들어왔을시에 그에 대한 응답을 views.py 에서 정의한 함수가 실행되도록 설계합니다.
















