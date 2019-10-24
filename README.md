# Blog_NaN

## APP (4)
- Blog
- Contact
- User
- Mainconfig

### Proposition de model

#### app1
````
#BLOG

class Cathegorie(models.Model):
    titre =  models.CharField(max_length = 255 )

    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)

class Tags(models.Model):
    titre =  models.CharField(max_length = 255 )

    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)

class Article(models.Model):
    auteur =  models.ForeignKey('User', on_delete = models.CASCADE, related_name = 'auteur')
    cathegorie =  models.ForeignKey('Cathegorie', on_delete = models.CASCADE, related_name = 'article_cathegorie')
    titre =  models.CharField(max_length = 255 )
    description =  models.CharField(max_length = 255 )
    contenue =  models.HTMLField()
    image = models.ImageField(upload_to='image/', blank=True)
    image_accueil = models.ImageField(upload_to='image/', blank=True)

    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)

class Commentaire(models.Model):
    article =  models.ForeignKey('Article', on_delete = models.CASCADE, related_name = 'article_commentaire')
    nom =  models.CharField(max_length = 255 )
    email =  models.EmailField(max_length = 255 )
    sujet =  models.CharField(max_length = 255 )
    message =  models.CharField(max_length = 255 )

    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)
````
#### app2
````
#Contact

class Contact(models.Model):
    nom =  models.CharField(max_length = 255 )
    email =  models.EmailField(max_length = 255 )
    sujet =  models.CharField(max_length = 255 )
    message =  models.CharField(max_length = 255 )

    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)

class Newsletter(models.Model):
    email =  models.CharField(max_length = 255 )

    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)
    ````
````
#### app3
```
#User

class User(models.Model):
    nom = models.CharField(max_length=255)
    prenom =models.CharField(max_length=255)
    isMembre =models.BooleanField(default = False)
    photo = models.ImageField(upload_to='profile', default='useravatar.png')
    fb_link=models.URLField(blank=True)
    tw_link=models.URLField(blank=True)
    goo_link=models.URLField(blank=True)
    insta_link=models.URLField(blank=True)
    description =models.CharField(max_length=255, null='True')
    
    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)
```

#### app4
```
#MainConf

class Config(models.Model):
    lien_map =models.CharField(max_length=255)
    logo = models.ImageField(upload_to='profile', default='useravatar.png')
    
    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)
    
 class Header(models.Model):
    nom = models.CharField(max_length=255)
    titre =models.CharField(max_length=255)
    image = models.ImageField(upload_to='header', default='useravatar.png')
    
    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)
    
class Sociaux(models.Model):
    titre = models.CharField(max_length=255)
    icon =models.CharField(max_length=255)
    lien =models.CharField(max_length=255)
    
    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)
    
class Footer(models.Model):
    titre = models.CharField(max_length=255)
    description =models.CharField(max_length=255)
    
    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)
    
class portofolio(models.Model):
    image = models.ImageField(upload_to='profile', default='useravatar.png')
    
    date_add = models.DateTimeField(auto_now_add = True)
    date_upd = models.DateTimeField(auto_now = True)
    statut = models.BooleanField(default = True)
```
