## DOM / Parse&Response
#### HTML = Hypertext Marking Language
#### <a href="" target="_blank"> 
#### target="_blank" means to open up the link in a new tab
<br/>

#### <a href=""><img src=""></a>
#### clicking on the image leads to the link 
<br/>

## Static files
#### HTML has evolved a lot over the years as computers and networks have gotten faster. CSS became important in presenting such information and websites to the users. User experience.
<br/>

#### CSS Syntax. CSS is a set of 'rules' which in include a 'selector' and one or more 'properties' and 'values' as well as some punctuation. 
#### body { font-family: arial, sans-serif; font-size: 100%; }
<br/>

#### Applying CSS to our HTML - inline / embedded / external 
#### <p style='border-style:solid;'>
#### <head><style> body {font-family: arial, sans-serif;}</style></head>
#### <head><link rel='stylesheet' href='styles.css'></head>
<br/>

#### span is an inline tag. div is a block tag. 
#### id tags are for chunks. classes can happen more than once. 
#### #first{} .shout{} #first p{}
<br/>

#### <img src="" style="float:right">
#### Taking the image out of its original flow and reserving the space on the right for the image. 
#### <hr clear="all" />
#### hr tag stands for horizontal rule. Used to insert a horizontal rule to divide and separate document sections. clear="all" means to clear any floats. 
#### <br clear="all" />
#### br tag is used to insert a line break.
<br/>

#### Advanced Colors. #rgb numbers. Higher numbers for higher amounts of that color. 0 ~ 9, then a (=10), b, c, d, e, f (=15). 00 - FF. For example, #ffffff = white, #000000 = black, #ff0000 = red, #00ff00 = green, #0000ff = blue. 
<br/>

#### Default fonts are Times Roman. body {font-family: "Trebuchet MS", Helvetica, Arial, sans-serif;}
#### the most left font is the most favorite preferred font. If that font doesn't exist, the list moves on the right. Fallback fonts are usually sans-serif. 
<br/>

#### Styling for links. 
#### a {font-weight: bold;} => before a visit
#### a:link {color:black;} => before a visit? 
#### a:visited {color: gray;} => after it has been visited
#### a:hover {text-decoration: none;} => when your mouse is over it but you have not clicked
#### a:active {color: aqua;} => you have clicked it and you have not yet see the new page
<br/>

#### <nav><ul><li><a href="" class=""></a><li><a href="" class=""></a></li></nav>
#### A nav tag is a html tag. 
<br/>

#### <link href="http://fonts.google.api..." rel="stylesheet">
#### To use a font from somewhere else. 
<br/>

#### <input type="color" onchange="alert(this.value);">
#### A color picker. 
<br/>

#### <p style="border-style: dashed; border-color: blue !important;>
#### The CSS rule that is closest to the tag wins unless a 'further away' tag marks itself as 1important. 
<br/>

#### padding, border, margin 
<br/>

#### Positioning.
#### <div style="position: relative; left: -20px; top: 20px;">
#### Relative positioning. A relative position moves a block away from where it would normally lay out. 
#### <div style="position: fixed; bottom: 20px; left: 30%;">
#### Fixed text is relative to the window. Maintains its position even when the window is resized or scrolled. A link that never goes away. 
#### <div style="position: absolute; top: 40px; left: 30%;">
#### Absolute text is relative to its parent element. In this case, the div is positioned relative to the body tag. Maintains its position even when the window is resized or scrolled. 
#### Fixed and absolute elements are 'plucked out' from the normal render stream and take up no vertical space. 
<br/>

#### Z-index. 
#### What happens when things overlap? Z-index higher number comes on top. 
#### <div style="z-index:100">
<br/>

#### How Databases Work
#### SQL is used to make Database engines. Keeping the data organized and making it simple. 
#### Before: Computers did not have enough data storage. Database was recorded onto a tape. Read record off tape and compare it with the transaction physical cards and then updated data would be recorded onto a tape again. Process took a long time. 
#### Then: Disk drives were invented. Faster than tape as the speed was the speed that the disk spun. How do we record and use this to organize data? 
#### SQL (Structured Query Language) came out of a government/ industry partnership. Formed from the need to have a standard for reading and organizing data from different industries and companies. SQL is the language we use to issue commands to the database (CRUD). 
<br/>

#### Relational Databases model data by storing rows and columns in tables. The power of the relational database lies in its ability to efficiently retrieve data from those tables and in particular where there are multiple tables and relationships between those tables involved in the query. 
#### 3 major database management systems: Postgres, Oracle, MySQL (Simpler but very fast and scalable). 
#### Database Model. A database model or database schema is the structure or format of a database, described in a formal language supported by the database management system. In other words, a "database model" is the application of a data model when used in conjunction with a database management system. 
#### SQL - Create data, Retrieve data, Update data, Delete data
<br/>

#### Making a Database
#### Create a simple table
#### CREATE TABLE Users( id integer NOT NULL PRIMARY KEY AUTOINCREMENT, name VARCHAR(128), email VARCHAR(128) );
#### .tables
#### .schema Users
<br/>

#### INSERT INTO Users (name, email) VALUES ('Kristin', 'kf@umich.edu')
#### The insert statement inserts a row into a table. 
<br/>

#### DELETE FROM Users WHERE email='ted@umich.edu'
#### Deletes a row in a table based on selection criteria. 
<br/>

#### UPDATE users SET name='Charles' WHERE email='csev@umich.edu'
#### Allows the updating of a field with a where clause. 
<br/>

#### SELECT * FROM Users
#### SELECT * FROM Users WHERE email='csev@umich.edu'
#### Select statement retrieves a group of records - you can either retrieve all the records or a subset of the records with a WHERE clause.
<br/>

#### SELECT * FROM Users ORDER BY email
#### SELECT * FROM Users ORDER BY name DESC 
#### You can add an ORDER BY clause to SELECT statements to get the results sorted in ascending or descending order. 
<br/>

#### Object Relational Mapping (ORM)
#### Allows us to map tables to objects and columns. We use those objects to store and retrieve data from the database. Improved portability across database dialects. 
<br/>

#### Defining a table
#### SQL: CREATE TABLE Users (name VARCHAR(128), email VARCHAR(128));
#### models.py: from django.db import models 
#### class User(models.Model): name = models.CharField(max_length=128) email = models.CharField(max_length=128)
#### These two are the same code. 
<br/>

#### python manage.py makemigrations 
#### python manage.py migrate
#### makemigrations are making a drawing. Then migrate is actually applying the drawing to the database. 
<br/>

#### python manage.py shell 
#### from usermodel.models import User 
#### u = User(name='Kristen', email='kf@umich.edu')
#### u.save()
#### print(u.id)
#### print(u.email) 
<br/>

#### u = User(name='Sally', email='a2@umich.edu')
#### u.save() 
<br/>

#### User.objects.values()
#### User.objects.filter(email='csev@umich.edu').values()
#### User.objects.values() is like the SELECT clause. filter() is like the WHERE clause. 
<br/>

#### User.objects.filter(email='ted@umich.edu').delete()
#### User.objects.values()
<br/>

#### User.objects.filter(email='csev@umich.edu').update(name='Charles')
#### User.objects.values()
<br/>

#### User.objects.values().order_by('email')
#### User.objects.values().order_by('-name')
<br/>

#### makemigrations command reads all the models.py files in all the applications, end creates/ evolves the migration files. Guided by the applications listed in settings.py. Migrations are portable across databases. 
#### migrate command reads all the migrations folders in the application folders and creates / evolves the tables in the database. 
<br/>

#### Many to One Relationships 
#### Foreign Key: 테이블의 필드 중 다른 테이블의 레코드를 식별할 수 있는 키. 각 레코드에서 서로 다른 테이블 간의 '관계'를 만드는 데 사용. 
#### N:1 or 1:N (ex. Comment(N) - Article(1))
#### class Comment(models.Model): article = models.ForeignKey(Article, on_delete=models.CASCADE)
#### to는 참조하는 모델 class 이름, on_delete는 참조하는 모델 class가 삭제 될 때 연결된 하위 객체의 동작을 결정. CASCADE는 부모 객체가 삭제 됐을 때 이를 참조하는 객체도 삭제. 
<br/>

#### Model-View-Controller 
#### In MVC, the model represents the information (the data) of the application and the business rules used to manipulate the data. The view corresponds to elements of the user interface such as text, checkbox items, and so forth. The controller manages details involving the communication to the model of user actions. 
#### Browser-> HTTP Request -> Handle input -> Store Data -> Retrieve Data -> Build HTML -> HTTP Response 
<br/>

#### Views and Templates
#### Views are the core of our application. Django looks at incoming request URL and uses urls.py to select a view -> View from views.py handles any incoming data in the request and copy it to the database through the model. Then it retrieves data to put on the pages from the database through the model. Finally, it produces the HTML that will become the response and return it to the browser. 
<br/>

#### Reading the URL. When Django receives an HTTP request, it parses it, and uses some of the URL for routing purposes and passes parts of the URL to your code. 
#### ....com/views/funky -> View within application
#### ....com/views/danger?guess=42 -> Key/ value parameter (GET)
#### ....com/views/rest/24 -> URL Path Parameter
<br/>

#### 3 patterns for views (in urls.py): 
#### 1. Requests are routed to a pre-defined class from Django itself
#### 2. Requests are routed to a function in views.py that takes the http request as a parameter and returns a response
#### 3. Requests are routed to a class in views.py that has get() and post() methods that take the http request as a parameter and returns a response
<br/>

#### Viewing the Views 
#### 1. Pre-defined. 
#### views/urls.py
#### path('', TemplateView.as_view(template_name='views/main.html')) 
#### views/templates/views/main.html 
#### Doesn't require a lot of code. Just send back the html file. 
<br/>

#### 2. Function in views.py.
#### path('funky', views.funky), 
#### In the views.py... 
#### from django.http import HttpResponse
#### from django.http import HttpResponseRedirect
#### def funky(request): 
####    response = """<html><body><p>This is the funky function sample</p></body></html>"""
####    return HttpResponse(response)
#### A HttpResponse is like a body of text. 
<br/>

#### path('danger', views.danger), 
#### In the views.py...
#### from django.http import HttpResponse
#### from django.http import HttpResponseRedirect
#### def danger(request):
####    response = """<html><body><p>Your guess was """+request.GET['guess']+"""</p></body></html>"""
####    return HttpResponse(response)
#### A request.GET is a dictionary of the key-value pairs that are on the URL. To pull the 42, dict[key] so you put in ['guess'] to get the value 42. 
#### Why is the view named danger? It is dangerous to take data from the user and include it in the HTTP Response without 'escaping' the output. HTML + JavaScript is a programming language and you don't want your users 'sending code' to other user's browsers. Cross-Site Scripting (XSS). So we need to protect against this. 
#### Another view function...
#### from django.utils.html import escape
#### def game(request): 
####    response = """<html><body><p>Your guess was """+escape(request.GET['guess'])+"""</p>
####    return HttpResponse(response)
#### After getting the value of guess, it calls a function escape which processes any dangerous characters. Automatic filter that prevents data from turning into code that might damage system. 
<br/>

#### path('rest/<int:guess>', views.rest), 
#### ....com/views/rest/41 
#### the 41 is <type:paramter-name>
#### This is basically saying that the parameter after the word rest is an integer, and please pass it in as the parameter guess. 
#### In the views.py...
#### from django.http import HttpResponse
#### from django.utils.html import escape
#### def rest(request, guess):
####    response = """<html><body><p>Your guess was """+escape(guess)+"""</p></body></html>"""
####    return HttpResponse(response)
<br/>

#### 3. Class Views - Inheritance
#### path('main', views.MainView.as_view()),
#### In views.py...
#### from django.http import HttpResponse
#### from django.utils.html import escape
#### from django.views import View
#### class MainView(View):
####    def get(self, request):
####        response = """<html><body><p>Hello world MainView in HTML</p></body></html>"""
####        return HttpResponse(response)
<br/>

#### path('remain/<slug:guess>', views.RestMainView.as_view()), 
#### In views.py...
#### from django.http import HttpResponse
#### from django.utils.html import escape
#### from django.views import View
#### class RestMainView(View):
####    def get (self, request, guess):
####        response = """<html><body><p>Your guess was """+escape(guess)+"""</p></body></html>""" 
####        return HttpResponse(response)
<br/>

#### HTTP Status Codes 
#### 200 OK 
#### 404 Not Found 
#### 302 Found/ Moved (redirect) - I know where you are supposed to be, but it isn't here. You can send a redirect response instead of a page response to communicate a location header to the browser. The location header includes a URL that the browser is supposed to forward itself to. 
<br/>

#### Sending a Redirect from a View 
#### path('bounce', views.bounce)
#### In views.py...
#### from django.http import HttpResponse
#### from django.http import HttpResponseRedirect
#### def bounce(request): 
####    return HttpResponseRedirect('https://...)
#### This function sends you to a different location. 
<br/>

#### Templates to Organize HTML 
#### Concatenation and escaping can get tiresome and lead to very obtuse looking view code. 
#### path('game/<slug:guess>', views.GameView.as_view())
#### In views.py...
#### from django.shortcuts import render
#### from django.views import View
#### class GameView(View): 
####    def get(self, request, guess):
####        x = {'guess': int(guess)}
####        return render(request, 'tmpl/cond.html', x)
#### In template cond.html...
#### <html><head></head><body><p>Your guess was {{guess}}</p> {% if guess <body 42 %} <p>Too low</p> {% else %} <p> Just right</p> {% endif %} </body></html>
<br/>

#### If there are many applications with templates in each application, we use a technique called 'namespace' so that each application can load its own templates. 
#### For namespace to work, we need to put templates in a path that includes the application name twice. ex) favs/templates/favs/detail.html 
<br/>

#### DTL - Django template language 
#### Substitution {{ zap }}, {{ zap|safe }}
#### Calling code {% url 'cat-detail' cat.id %}, {% author.get_absolute_url %}
#### Logic {% if zap > 100 %}, {% endif %}
#### Blocks {% block content %}, {% endblock %}
<br/>

#### def guess(request): 
####    context = {'zap': '42'}
####    return render(request, 'tmpl/guess.html', context)
#### In tmpl/guess.html...
#### <body><p>Your guess was {{ zap }}</p>
<br/>

#### def loop(request): 
####    f = ['apple', 'orange', 'banana', 'lychee']
####    n = ['peanut', 'cashew']
####    x = {'fruits': f, 'nuts': n, 'zap': '42'}
####    return render(request, 'tmpl/loop.html', x)
#### In tmpl/loop.html... 
#### <ul> {% for x in fruits %} <li>{{ x }}</li>{% endfor %}</ul>
#### {% if nuts %}<p>Number of nuts: {{ nuts|length }}</p>{% endif %}
<br/>

#### def nested(request): 
#### x = {'outer': {'inner': '42'}}
#### return render(request, 'tmpl/nested.html', x)
#### In nested.html...
#### <body><p>Your guess was {{ outer.inner }}</p>
<br/>

#### Template Inheritance 
#### Inheritance - When we make a new template, we can extend an existing template and then add our own little bit to make our new class. Another form of store and reuse. Don't Repeat Yourself. 
#### Render Data + Base Template + Template => Rendered Output
<br/>

#### template/base.html 
#### <html>...<body>{% block content %}{% endblock %}</body></html>
#### template/cond.html 
#### {% extends "template/base.html" %}
#### {% block content %}<p>Your guess was {{ guess }}</p>{% endblock %}
<br/>

#### URL Mapping / Reversing 
#### urls.py 
#### app_name = 'route'
#### urlpatterns = [ path('second', views.SecondView.as_view(), name='second-view'), ]
#### route:first-view => application name: view name 
#### <a href="{% url 'route:second-view' %}></a>
<br/>

#### Other applications and parameters
#### 'gview:cat' 42 => application name: view name parameter 
#### urls.py urlpatterns = [path('hello/', include('hello.urls', namespace='nshello'))] 
#### you can either refer to it as hello:second-view or nshello:second-view. Both are fine. 
<br/>

#### In urls.py ... 
#### path('second', views.SecondView.as_view(), name='second-view'),
#### In views.py ... 
#### from django.shortcuts import render 
#### from django.urls import reverse, reverse_lazy 
#### from django.views import View 
#### class SecondView(View): 
####    def get(self, request): 
####        u = reverse_lazy('gview:cats')
####        u2 = reverse_lazy('gview:dogs')
####        u3 = reverse('gview:dog', args=['42'])
####        ctx = {'x1': u, 'x2': u2, 'x3: u3}
####        return render(request, 'route/second.html', ctx)
#### reverse, and reverse_lazy are from the django.urls library. Reverse and reverse_lazy says delay it to look it up. 
<br/>

#### Generic Views 
#### Generic Views - List / Detail 
#### In views.py... 
#### class CatListView(View):
####    def get(self, request): 
####        stuff = Cat.objects.all()
####        cntx = {'cat_list': stuff}
####        return render(request, 'gview/cat_list.html', cntx)
#### class DogListView(View):
####    model = Dog 
####    def get(self, request): 
####        modelname= self.model._meta.verbose_name.title().lower()
####        stuff = self.model.objects.all()
####        cntx = { modelname+'_list': stuff}
####        return render(request, 'gview/' +modelname+' _list.html', cntx)
#### from django.views import generic 
#### class HorseListView(generic.ListView): 
####    model = Horse 
#### generic views allow us to produce lots of similar pages without cutting, pasting, and editing boiler plate. Quicker development. Consistent User Experience. Less lines of code. 
<br/>

#### Form Processing 
#### Forms gather data and send it to the server. 
#### Two ways the browser can send parameters to the web server. GET - parameters are placed on the URL which is retrieved. POST - the URL is retrieved and parameters are appended to the request in the HTTP connection. 
#### Browser has a form <input type="text" name="guess" id="yourid" />
#### Browser sends a HTTP Request to the Web Server -> GET / POST 
#### POST is used when data is being created or modified. GET is used when you are reading or searching things. GET should never be used to insert, modify or delete data. GET urls should be 'idempotent' and the same URL should give the same thing each thing you access it. 
<br/>

#### Forms in HTML
#### <p><label for="inp01">Account:</label>
#### <input type="text" name="account" id="inp01" size="40"></p>
#### type refers to textbox, id refers to the label tag with the field to know that the account and the textbox is connected. name is the key for the value. 
#### <input type="password"></p>
#### type password shows it in asterisks.  
#### <input type="radio" name="when" value="am">AM<br>
#### type radio is choosing an option, if name=when, only one selected. 
#### <input type="checkbox" name="class1">py4e - Python <br>
#### <input type="checkbox" name="class2" value="si539" checked>si<br/>
#### type checkbox is you can choose multiple options. if no value, then just class1=on, if value, class2=si539. 
#### <p><label for="inp06>Which soda: 
#### <select name="soda" id="inp06"><option value="0">--Please Select--</option></select></p> 
#### This is a drop down. 
#### <p><label for="inp06>Tell us: <br/><textarea rows="10" cols="40" id="inp08" name="about">I love ~ </textarea></p>
#### This is a textarea. 
#### <input type="submit" name="dopost" value="Submit" />
#### <input type="button" onclick="location.href='http://www.dj4e.com/'; return false;" value="Escape"> 
#### Submit / Escape buttons. 
#### Select your favorite color: 
#### <input type="color" name="favcolor" value="#0000ff"><br/> 
<br/>

#### Cross-Site-Request-Forgery(CSRF)
#### CSRF Attack is that a rogue site generates a page that includes form that posts data to a legitimate site where the user is logged in via a session cookie. The form is submitted to the legitimate site and the cookie is included. The legitimate site accepts the request because of the cookie value. 
#### CSRF Defense is that the legitimate site chooses a large random number and puts it in the session. When the legitimate site generates a POST form, it includes the CSRF Token as a hidden input field. When the form is submitted the CSRF Token is sent as well as the cookie. The site looks up the session and rejects the request if the incoming CSRF Token does not match the session's CSRF Token. 
#### Django has built in support to generate, use, and check CSRF Tokens. 
<br/>

#### from django.middleware.csrf import get_token 
#### or 
#### {% csrf_token %} inside form in the template. 
<br/>

#### In views.py...
#### class ClassyView(View): 
####    def get(self, request): 
####        return render(request, 'getpost/guess.html')
####    def post(self, request):
####        guess = request.POST.get('guess')
####        msg = checkguess(guess)
####        return render(request, 'getpost/guess.html', {'message': msg})
<br/>

#### POST/ Refresh/ -> Once you do a POST request and receive 200 status + a page of HTML, if you tell the browser to refresh, the browser will re-send the POST data a second time. The user gets a browser pop-up that tries to explain what is about to happen. 
#### POST-Redirect-GET-Refresh 
<br/>

#### Cookies (Browser Concept) - Session (Server Concept)
#### A server might have many different connections to browsers. Need a way to distinguish between different connections. Thus, you use a cookie to mark who is who. Cookies include a state of the connection data. 
#### browser requests a Web page -> server sends back a page + cookie -> browser requests another page. 
#### def cookie(request):
####    print(request.COOKIES)
####    resp = HttpResponse('C is for cookie and that is good enough for me...')
####    resp.set_cookie('zap', 42) # No expired date = until browser close
####    resp.set_cookie('sakaicar', 42, max_age=1000) # seconds until expire 
####    return resp 
<br/>

#### Django Sessions
#### Before urls.py, Session Middleware accepts the request and checks for the cookie to look for the session stored in the database. 
#### In most server applications, as soon as we start a session for a new browser we create a session. We set a session cookie to be stored in the browser, which indicates the session id in use - gives this browser a unique "mark". The creation and destruction of sessions is handled by a Django middleware that we use in our applications. 
#### Session Identifier - a large, random number that we place in a browser cookie the first time we encounter a browser. Used to pick from the many sessions that the server has active at any one time. For example, shopping cart or login information is stored in the session in the server. 
#### settings.py -> Middleware -> 'django.contrib.sessions.middleware.SessionMiddleware', 
#### Stored in the database. When python manage.py migrate -> sessions.0001_initial... => This is the sessions data. 
#### The incoming request object has a request.session attribute that we can treat like a dictionary that persists from one request to the next request. As long we have the session middleware enabled in settings.py and the database table, and the browser allows cookies, we just store and read reqeust.session in our views and pretend it is magic. 
<br/>

#### def sessfun(request):
####    num_visits = request.session.get('num_visits', 0) + 1 
####    request.session[num_visits'] = num_visits 
####    if num_visits > 4: del(request.session['num_visits'])
####    return HttpResponse('view count='+str(num_visits))
#### Cookie is the thing that looks that up and session is where we store the information. 
<br/>

#### Data Modelling - One to Many 
#### model.py - define the structure of our database. 
#### Model Design is an art form of its own with particular skills and experience. Our goal is to avoid the really bad mistakes and design clean and easily understood models. Model design starts with a sample data set and draws a picture. 
#### Database Normalization (3NF). There is tons of database theory / math and we simplify this to a few rules. Do not replicate data. Add a special unique key column to each table which we will make references to - by convention, many programmers and frameworks call this column 'id'. Use integers for making links between tables - integers are fast and small. 
<br/>

#### Designing a Data Model
#### 










