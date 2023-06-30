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




