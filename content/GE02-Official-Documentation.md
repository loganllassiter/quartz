---
title: GE 02 Technical Documentation
---

***
###### Logan Lassiter
###### Naomi Rodriguez
###### Irving Reyes Bravo

***
## Table of Contents

[Getting Started](GE02-Official-Documentation.md#^5c2d37)

[2.1 Create Virtual Environment and Django Project](GE02-Official-Documentation.md#^2f7398) `Logan`

[2.2 Create Local Git and GitHub Repository](GE02-Official-Documentation.md#^51a15e) `Logan`

[2.3 Create Portfolio App](GE02-Official-Documentation.md#^37a45a) `Irving`

[2.4 Define URI path and view](GE02-Official-Documentation.md#^4bb8fe) `Irving`

[2.5 Create HTML Template](GE02-Official-Documentation.md#^c457bf) `Naomi`

[2.6 Add static files](GE02-Official-Documentation.md#^b92dca) `Naomi`
***

## Getting Started

^5c2d37

***
## 2.1 Create Virtual Environment and Django Project

^2f7398

<sup>These instructions show examples of working on a Mac for the commands. Note how you must run the commands in your environment.</sup>

#### Activation and Installation of Django 4.2

#### 1. Open the terminal and check your python version.

* Inside of the terminal, enter these commands:

	```bash
	$ python3 --version
	```

	<sub>You should be using python version 3.11</sub>
	
	![](attachments/Pasted%20image%2020240215124120.png)

* Inside of the portfolio directory, run commands:
	```bash
	$ source djvenv/bin/activate
	$ pip install Django==4.2
	$ python -m django --version
	```
	<sup> These commands will let you activate the Django virtual environment, install Django version 4.2, and confirm that you have the right version installed
	</sup> 
	
	![](attachments/Pasted%20image%2020240215124132.png)
	![](attachments/Pasted%20image%2020240215124140.png)
***
## 2.2 Create Local Git and Github Repository

^51a15e
#### 1. Prepare existing local directory to be added to GitHub

* If you do not have an existing local directory to use for your Github repository create one
	```bash
	$ mkdir [directory-name]
	```
	![](attachments/Pasted%20image%2020240215124154.png)
	
	Here is a guide to [create a repo from an existing local directory](https://docs.github.com/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github)
* Use the following commands (if you run into trouble revert to linked guide):
	```bash
	$ cd [your-local-directory]
	$ git init -b main
	$ touch .gitignore
	$ git add .
	$ git commit -m "First commit"
	```
	1. change directory to the local directory you want to use for your repo
	2. initialize the main branch
	3. create .gitignore file (more on .gitignore below)
	4. stage the files for initial commit
	5. commits/saves changes and prepares them to be pushed
	   
	![](attachments/Pasted%20image%2020240215124207.png)
#### 2. Create and link GitHub repo with local directory.
* Create a new repository on GitHub.com
	*  Make the repository private
	*  Do not initialize ReadMe, license, .gitignore files
	* You may need to setup authentication with GitHub, follow the HTTPS guide [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github#https)
* Copy the repository URL and open your local project directory in the terminal.
* Use the following commands:
	```bash
	$ git remote add origin [copied-repo-URL]
	$ git remote -v
	```
	1. links local directory to GitHub Repo
	2. verifies link was successful
	
	![[Pasted image 20240214132419.png]]

#### 3. Push changes in local directory to GitHub.com
* Run the following command:
	```bash
	$ git push -u origin main
	```
	
	![](attachments/Pasted%20image%2020240215123900.png)
#### .gitignore

You can setup [gitignore](https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files) files so, that Git ignores files you do not want added to GitHub.

[Here](https://gist.github.com/octocat/9257657) is an example of a gitignore file.
***
## 2.3 Create Portfolio App

^37a45a

***
## 2.4 Define URI path and view

^4bb8fe

***
## 2.5 Create HTML Template

^c457bf

In PyCharm:
* Create a folder called templates in portfolio_app
* In templates, create a folder called portfolio_app
  
  ![](attachments/Pasted%20image%2020240215130935.png)
*  Create a base_template.html file in the templates/portfolio_app folder
  
	  ![](attachments/Pasted%20image%2020240215131155.png)

* In the base_template file, paste the following code:
	```html
	{% load static %}
	<!DOCTYPE html>  
	<html lang="en">  
	 <head>  
	   <title>UCCS CS Students</title>  
	   <meta charset="utf-8">  
	   <meta name="viewport" content="width=device-width, initial-scale=1">  
	   <title>Bootstrap demo</title>  
	   <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9" crossorigin="anonymous">  
	 </head>  
	  
	  
	 <body>  
	   <div class="container-fluid">
	
	
		 <!-- Navbar-->
		 <nav class="navbar navbar-expand-lg bg-body-tertiary">  
		   <a class="navbar-brand" href="#">Navbar</a>
	
		   <div class="container-fluid">  
			 <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">  
			   <span class="navbar-toggler-icon"></span>  
			 </button>  
			 <div class="collapse navbar-collapse" id="navbarNavAltMarkup">  
			   <div class="navbar-nav">
				 <!--  {% url 'index' %}  is defined in url path to dynamically create url -->
				 <a class="nav-link active" aria-current="page" href="{% url 'index' %}">Home</a>  
				 <a class="nav-link" href="#">Menu 2</a>  
				 <a class="nav-link" href="#">Menu 3</a>
				 {% if user.is_authenticated %}
				   <a class="nav-link" href="{% url 'logout' %}?next={{ request.path }}">Logout {{user}}</a>
				 {% else %}
				   <a class="nav-link" href="{% url 'login' %}?next={{ request.path }}">Login</a>
				 {% endif %}
			   </div>  
			 </div>  
		   </div>  
		 </nav>  
		   <div class="col-sm-10">
			 <!-- add block content from html template -->
			 {% block content %}  
			 {% endblock %}
		   </div>  
		 </div>  
	   </div>  
	 </body>  
	</html>
	```
* Create an index.html file in the templates/portfolio_app folder
  
  ![](attachments/Pasted%20image%2020240215132429.png)
  
* Paste the following code into it:
	<sub>This will be the home page for the app.</sub>
		
	```html
	<!-- inherit from base.html-->
	{% extends "portfolio_app/base_template.html" %}
	
	<!-- Replace block content in base_template.html -->
	{% block content %}
	<h1>Computer Science Portfolios</h1>  
	  
	<h2>More to come from [and your name goes here]</h2>
	
	{% endblock %}
	```


	<sub>**I did have to modify portfolio_app/urls.py file otherwise a *NoReverseMatch* at / Error occurs with line 35 in base_template.html**</sub>
	
	![](attachments/Pasted%20image%2020240215135123.png)
* *Remember to have your server running:*
	```python
	python manage.py runserver
	```
* Open http://localhost:8000, you should see your index.html file displayed.
  
	![](attachments/Pasted%20image%2020240215135716.png)
  
* Version and update sprint01 and remote repository (I used git).
  ![](attachments/Pasted%20image%2020240215135837.png)

***
## 2.6 Add static files

^b92dca

In your portfolio folder
1. Create a static folder
2. Create an images folder in the static folder
3. Add a logo to the images folder. I used [UCCS logo](https://brand.uccs.edu/sites/g/files/kjihxj1416/files/inline-images/uccs-signature-email.gif)
   
   ![](attachments/Pasted%20image%2020240215140104.png)

In the *django_project* file
1. Open settings.py and add the os library
   
   ![](attachments/Pasted%20image%2020240215140254.png)
2.  Add the following code below the STATIC_URL = ‘static/’ line
	```python
	STATIC_URL = 'static/'
	
	STATICFILES_DIRS = [
		os.path.join(BASE_DIR, 'static')
	]
	
	MEDIA_URL = '/images/'
	```
	
3.  In base_template.html, paste:
	```html
	{% load static %}
	
	<!DOCTYPE html>  
	<html lang="en">  
	 <head>  
	   <title>UCCS CS Students</title>  
	   <meta charset="utf-8">  
	   <meta name="viewport" content="width=device-width, initial-scale=1">  
	   <title>Bootstrap demo</title>  
	   <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9" crossorigin="anonymous">  
	 </head>  
	  
	  
	 <body>  
	   <div class="container-fluid">
	
	
	     <!-- Navbar-->
	     <nav class="navbar navbar-expand-lg bg-body-tertiary">  
	       <img src="{% static 'images/uccs_logo.gif' %}">  
	       <div class="container-fluid">  
	         <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">  
	           <span class="navbar-toggler-icon"></span>  
	         </button>  
	         <div class="collapse navbar-collapse" id="navbarNavAltMarkup">  
	           <div class="navbar-nav">
	             <!--  {% url 'index' %}  is defined in url path to dynamically create url -->
	             <a class="nav-link active" aria-current="page" href="{% url 'index' %}">Home</a>  
	             <a class="nav-link" href="#">Menu 2</a>  
	             <a class="nav-link" href="#">Menu 3</a>
	             {% if user.is_authenticated %}
	               <a class="nav-link" href="{% url 'logout' %}?next={{ request.path }}">Logout {{user}}</a>
	             {% else %}
	               <a class="nav-link" href="{% url 'login' %}?next={{ request.path }}">Login</a>
	             {% endif %}
	           </div>  
	         </div>  
	       </div>  
	     </nav>  
	  
	  
	       <div class="col-sm-10">
	         <!-- add block content from html template -->
	         {% block content %}  
	         {% endblock %}
	       </div>  
	     </div>  
	   </div>  
	 </body>  
	</html>
	```
	
	<sup>The only changes made were the top of the document has `{% load static %}`
	Line 20 is replaced with `<img src="{% static 'images/uccs_logo.gif' %}">`
	</sup>

* Open http://localhost:8000 and your logo will be added to the Navbar
  
	![](attachments/Pasted%20image%2020240215142342.png)

* Version sprint01 branch and update your remote repository.

* Update your main branch by merging it with sprint01 branch code and tag the code as GE02. Do not delete sprint01 branch.
  
	 ![](attachments/Pasted%20image%2020240215143104.png)

Here is a guide on merging branches [link](https://docs.github.com/en/desktop/working-with-your-remote-repository-on-github-or-github-enterprise/syncing-your-branch-in-github-desktop)
* Or in the terminal:
	```bash
	git checkout main
	git merge sprint01
	git commit -m "merge sprint01 to main"
	git push origin main
	```
***
