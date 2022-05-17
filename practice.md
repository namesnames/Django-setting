### 📌 어플리케이션 추가

> python manage.py startapp app1
   
   - app1 이라는 이름의 어플리케이션을 생성합니다.

![image](https://user-images.githubusercontent.com/88240193/168726309-24c3c1d0-cf17-45f5-8372-4428d1d6b977.png)

- INSTALLED_APPS
    - settings.py 파일의 INSTALLED_APPS 에 'app1' 을 추가해서 새로운 어플리케이션을 등록합니다.


---

### MVC 패턴에 따른 어플리케이션 설계

- 생성한 "app1" 어플리케이션의 기능으로, HTML 파일이 우리 눈에 보여지도록 설계할 것 입니다.
- 각각의 URL 요청에 따른 index.html 파일과 index2.html 파일의 내용이 화면에 보여지도록 구성해봅시다.

(html 파일들은 app1 어플리케이션 폴더안에 우리가 만든 templates 폴더에 위치해 있습니다.)

![image](https://user-images.githubusercontent.com/88240193/168787891-99e5e45c-987f-4e42-bf05-59eba8b28679.png)


#### views.py : 렌더링

- HTML 페이지를 웹브라우저 화면에 보여주는 논리를 담당하는 함수를 views.py 파일 안에서 구성합니다.
- 다양한 URL 요청이 들어올 수 있는데, 이에 대응하는 응답을 보내줄 수 있도록 함수를 정의하면 됩니다.

ex) 장고로 만든 웹서비스 주소가 http://127.0.0.1:8000/ 일때,
http://127.0.0.1:8000/1 
http://127.0.0.1:8000/abc/1
이렇게 다양한 요청이 들어올 수 있다.

우리는 아래와 같은 함수를 정의합니다.


~~~
def req1(request):  # 어떤 요청이 들어왔을때 
    return render(request, 'index.html') # 그 요청과 함께 index.html 이라고 하는 html 을 찍어  보내줘라! (리턴해줘라!) => 렌더링(rendering)

def req2(request):
    return render(request, 'index2.html')
~~~

#### urls.py 

- urls.py 파일에서 특정 url 에 대한 요청이 들어왔을시에 그에 대한 응답을 views.py 에서 정의한 함수가 실행되도록 설계합니다.

=> 형태 : path('/기본 경로에 뒤에 추가할 url 경로', Function)

~~~
path('', app1.views.req1) # "http://127.0.0.1:8000/" 이라는 웹서비스의 기본 URL 주소에 대해 요청이 들어왔을때 myapp.views.req1 함수 실행
path('my_index2/', app1.views.req2)   # "http://127.0.0.1:8000/my_index2" 주소에 대한 요청이 들어왔을 때 app1.views.req2 함수를 실행
~~~

---

- 위 내용들로 잘 구성되었다면, 기본 URL 주소에 대한 요청이 들어왔을때 req1 함수가 실행되어서 index.html 파일이 우리 웹브라우저에 보여지게 될 것입니다.
- 또한 http://127.0.0.1:8000/my_index2 주소에 대한 요청이 들어왔을때는 동일한 원리로 index2.html 파일이 우리 눈에 펼쳐집니다!
- 명령어 runserver 로 서버를 킨후 동작을 시켜봅시다.








