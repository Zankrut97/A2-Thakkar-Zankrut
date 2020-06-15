# Assignment 2

This Assigment focuses on understanding and applying the usability and design principles for overall asethetics of the web application by developing the front-end part. During the implementation of the assignment following four main pages were developed, they are Home/landing page, which shows all the features of the web application and also all other pages can be navigated through the Home page. Sign-in page, user can login to the web application using email-id and password, all validations are performed but on click of sign-in button it is not redirected to other page.Blogs page all the blogs in form of card and content of each blog can be viewed by clicking on the card also user can search particular blog. Jobs page shows all the Job post and user search job based on the role and additional details can be viewed by clicking the card. Additionally "Page not found" page is created and  user will be redirected if they try to visit the page which not exixts. Also for the other pages which are not developed by me will show a message.


* Date Created: 14 Jun 2020
* Last Modification Date: 14 Jun 2020

## Authors

* Thakkar Zankrut Bhavinkumar (zn834201@dal.ca) B00856858


## Getting Started

*Github repository link

https://github.com/Zankrut97/A2-Thakkar-Zankrut

*The project is deployed on Heruko.The pages developed can be accessed from the below links

* Home Page - https://a2-thakkar-zankrut.herokuapp.com/home
* Sign-in Page - https://a2-thakkar-zankrut.herokuapp.com/sign-in
* Blogs Page - https://a2-thakkar-zankrut.herokuapp.com/blogs
* Jobs Page - https://a2-thakkar-zankrut.herokuapp.com/jobs
* Page not found - https://a2-thakkar-zankrut.herokuapp.com/ad

### Prerequisites
 
*For running the project, following things should be downloaded installed on the local machine 

*nodejs

download link - https://nodejs.org/en/download/

After installing nodejs install npm (package manager) to install required packages

*angular cli

install using npm 
npm install -g @angular/cli

*visual studio code

download link - https://code.visualstudio.com/download

### Installing

1) Download the nodejs from the above given link.
2) Check the if the installation was successful using following command in the CMD
	node -v
	npm -v
3)Intall angular cli using command
	npm install -g @angular/cli
4) check if the installation was successful using
	ng --version
5)Install visual studio code, which is a code editor using above given link.


###Steps to run

1) After intalling the above mentioned tools and software
2) Create a new directory and clone the github project using the repository link
3) Open the project in the Visual Studio Code
4) Open terminal and from the root directory of the project execute to update all the reequires packages
	npm update
5)  After that execute to run the project and view in browser 
	ng serve -o

## Deployment

The project is deployed usning Heruko.

steps
1) Go to Heruko and sign in with your account- https://www.heroku.com/
2) Create new app and give app name and region and click on create app
3) Choose Gihub integration as our code can be directly used from our github repositiry
4) Select Repository and branch
5)select option "Enable Automatic Deploys" it will automaically build and deploy the project after new changes pushed to the repository.
6)install express on our machine using
	npm install express
7)Build the project
	ng build
8)Create a server.js file and use static file from the "dist" and give port as 8080
9)Add start script in our package.json
	"start": "ng serve"
10) run server.js and check everything is working as required
	node server.js
11) After checking, push the code to github repository
12)Heruku will build the project and deploy it.
13)Go to heruko dashboarda and click on open app
	
## Built With

* [Angular](https://angular.io/docs) - web framework used
* [Bootstrap](https://getbootstrap.com/docs/4.5/getting-started/introduction/) - Bootstrap components and classes are used for responsiveness
* [Angular Material](https://material.angular.io/guide/getting-started) - Used for styling and form validation
* [node.js] (https://nodejs.org/en/download/)- package manager

##Design Justification

*Fonts:
Google Lato - for some title to make it more expessive.
https://fonts.google.com/specimen/Lato
Roboto -standard fonts of the website and it matches the overall theme of the web app

*Background color 
Major color used for the web app is (#fee3b8) to enhance some parts of the web app. As the overall theme of was to keep the minimalist design I have used this light shade.


## Sources Used

### blogsfilter.pipe.ts

Lines 8 - 14
---------------

```
 transform(blogs: any, keyword: any): any {
    if (keyword === undefined) return blogs;

    return blogs.filter(function (blog) {
      return blog.title.toLowerCase().includes(keyword.toLowerCase())
    })
```

The code above was created by adapting the code in [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) as shown below: 

```
    transform(items: any[], term: string): any {
        // I am unsure what id is here. did you mean title?
        return items.filter(item => item.id.indexOf(term) !== -1);
    }

```

- The code in [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) was implemented by creating a pipe file for blogs component.
- [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) Code was used to filter out the blogs based on the search term
- [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) Code was modified by adding the null check as well as filtering the list using the id of the blog which is obtained uisng angular routing parameter.


### jobsfilter.pipe.ts

Lines 8 - 14
---------------

```
transform(jobs: any, keyword: any): any {
    if (keyword === undefined) return jobs;

    return jobs.filter(function (job) {
      return job.post.toLowerCase().includes(keyword.toLowerCase())
    })
  }

```
The code above was created by adapting the code in [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) as shown below: 

```
 transform(items: any[], term: string): any {
        // I am unsure what id is here. did you mean title?
        return items.filter(item => item.id.indexOf(term) !== -1);
    }
```

- The code in [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) was implemented by creating a pipe file for jobs component.
- [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) Code was used to filter out the jobs based on the search term
- [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) Code was modified by adding the null check as well as filtering the list using the id of the blog which is obtained uisng angular routing parameter.

### header-navbar.component.html

Lines 3 - 40
---------------

```
<header class="head my-3">
        <nav class="navbar navbar-expand-lg navbar-light">
            <a class="navbar-brand d-flex align-items-center" routerLink="/home">
                <img class="navbar-logo" src="/assets/briefcase.svg" alt="website-icon">
                <span class="header-name" style="font-family: Lato;">TrackMyJobs</span>
            </a>
            <button class="navbar-toggler border-0 " type="button" data-toggle="collapse" data-target="#header-navbar">
                <span><img class="toggle-img" src="/assets/icons8-menu.svg" alt=""></span>
            </button>
            <div class="collapse navbar-collapse justify-content-end" id="header-navbar">
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <a class="nav-link nav-link-menu" routerLink="/home" routerLinkActive="nav-active">{{home}}</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link nav-link-menu" routerLink="/blogs" routerLinkActive="nav-active">{{blog}}</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link nav-link-menu" routerLink="/jobs" routerLinkActive="nav-active">{{jobs}}</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link nav-link-menu" routerLink="/contact"
                            routerLinkActive="nav-active">{{contact}}</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link nav-link-menu" routerLink="/about"
                            routerLinkActive="nav-active">{{about}}</a>
                    </li>
                </ul>
                <div class="my-2 my-lg-0">
                    <button class="btn btn-primary mr-sm-2 signin" type="button"
                        [routerLink]="['/sign-in']">{{sign_in_btn}}</button>
                    <button class="btn btn-outline-primary my-2 my-sm-0 signup" type="button"
                        [routerLink]="['/sign-up']">{{sign_up_btn}}</button>
                </div>
            </div>
        </nav>
    </header>
```
The code above was created by adapting the code in [Bootstrap - Navbar](https://getbootstrap.com/docs/4.0/components/navbar/) as shown below: 

```
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Action</a>
          <a class="dropdown-item" href="#">Another action</a>
          <div class="dropdown-divider"></div>
          <a class="dropdown-item" href="#">Something else here</a>
        </div>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Disabled</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
```

- The code in [Bootstrap - Navbar](https://getbootstrap.com/docs/4.0/components/navbar/) was implemented by creating a responsive navbar.
- [Bootstrap - Navbar](https://getbootstrap.com/docs/4.0/components/navbar/) Code was used create a responsive nav bar.
- [Bootstrap - Navbar](https://getbootstrap.com/docs/4.0/components/navbar/) Code was modified by adding the adding the navigation links and the using angular components to get the menu items from the typescript file,


### sign-in.component.html

Lines 19 - 27
---------------

```
 <mat-form-field appearance="outline" style="width: 100%; border-radius:25px !important;">
                                <mat-label>Email</mat-label>
                                <input #email="ngModel" matInput required ngModel name="email" placeholder="abc@abc.com"
                                    pattern="^[A-z0-9._%+-]+@[A-z0-9.-]+\.[A-z]{2,4}$">
                                <mat-icon matSuffix>email</mat-icon>
                                <mat-error *ngIf=" !email.touched && email.invalid">Email is required</mat-error>
                                <mat-error *ngIf=" email.touched && email.invalid">
                                    <div *ngIf="email.errors.required">Email is required</div>
                                    <div *ngIf="email.errors.pattern">Enter valid Email id(abc@abc.com)</div>
                                </mat-error>

```
The code above was created by adapting the code in [Angular - Form Validation](https://angular.io/guide/form-validation) as shown below: 

```
<input id="name" name="name" class="form-control"
      required minlength="4" appForbiddenName="bob"
      [(ngModel)]="hero.name" #name="ngModel" >

<div *ngIf="name.invalid && (name.dirty || name.touched)"
    class="alert alert-danger">

  <div *ngIf="name.errors.required">
    Name is required.
  </div>
  <div *ngIf="name.errors.minlength">
    Name must be at least 4 characters long.
  </div>
  <div *ngIf="name.errors.forbiddenName">
    Name cannot be Bob.
  </div>

</div> 

```

- The code in [Angular - Form Validation](https://angular.io/guide/form-validation) was implemented by creating a email and password validation
- [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) Code was used to validate the email and password in sign-in component
- [stackoverflow.com](https://stackoverflow.com/questions/44769748/angular-4-pipe-filter) Code was modified by adding the validation based on pattern for email and min-length for password. Also used angular <mat-error> to show the error.


### blogs.component.html

Lines 15 - 29
---------------

```
 <div class="row" style="margin-top:25px;">
            <div class="col-lg-3 col-md-4 col-sm-6" *ngFor="let blog of blogs | blogsfilter:blogSearch"
                (click)="onBlogCard(blog)">
                <div class="card" style="margin:10px;box-shadow: 0.5rem 1rem 1rem 0.5rem rgba(0, 0, 0, 0.1);">
                    <img style="margin:5px;" class=" card-img-top" width="150" height="150" src={{blog.img}}
                        alt="Blog-image">
                    <div class="card-body">
                        <h4 style="font-weight: 600;" class="card-title">{{blog.title}}</h4>
                        <p class="card-text">{{blog.description}}
                        </p>
                        <button (click)="onBlogCard(blog)" class="btn btn-primary">View More</button>
                    </div>
                </div>
            </div>
        </div>
```
The code above was created by adapting the code in [Bootstrap - Card](https://getbootstrap.com/docs/4.0/components/card/) as shown below: 

```
<div class="card" style="width: 18rem;">
  <img class="card-img-top" src="..." alt="Card image cap">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

- The code in [Bootstrap - Card](https://getbootstrap.com/docs/4.0/components/card/) was implemented by creating a card for blogs and jobs
- [Bootstrap - Card](https://getbootstrap.com/docs/4.0/components/card/) Code was used to create card for blogs and jobs post.
- [Bootstrap - Card](https://getbootstrap.com/docs/4.0/components/card/) Code was modified by adding creating dynamic and responsive cards from the list of blogs and jobs using angular


## Acknowledgments
*Navigation menu was created usin Bootstrap(https://getbootstrap.com/docs/4.5/components/navbar/)
* All the cards were created using the Bootstrap card (https://getbootstrap.com/docs/4.0/components/card/) 
* Sign-up page was developed using the reference(https://startbootstrap.com/snippets/login/)
* All the form field were created using angular material forms (https://material.angular.io/components/form-field/overview)
*text used was generated using lorem-ipsum generator(https://loremipsum.io/)


##References
[1] Angular, “Angular Material,” Angular Material, 2020. [Online]. Available: [2] https://material.angular.io/. [Accessed: 14-Jun-2020].
[3] Start Bootstrap, “Bootstrap 4 Login Page Snippet,” Start Bootstrap, 2019. [Online]. Available: [4] https://startbootstrap.com/snippets/login/. [Accessed: 14-Jun-2020].
[5] The Net Ninja, “Angular 2 Tutorial #22 - Custom Filter Pipe,” YouTube. 2020
[6] Codevolution, “Angular Forms Tutorial,” YouTube. 2020.
[7] “Lorem Ipsum,” Lorem Ipsum, 2020. [Online]. Available: https://loremipsum.io/. [Accessed: 14-Jun-2020].





