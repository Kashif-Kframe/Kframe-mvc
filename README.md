# Kframe

Kframe
PHP MVC framework. A basic mvc pattern framework, most functions name are same like Laravel (inspired by Laravel) I want to improve it with github community, please contribute and make it strong as much as possible. Any contribution will be appreciated.

# Getting Started
  Kframe uses Composer to Manage Dependencies and You need to have Composer installed on your machine to continue If you don't already have composer, Download it here: http://getcomposer.org/
  
  After Installing Composer, Run command
  
    composer update

# Routing:
<<<<<<< HEAD
WE can define routes in route/route.php file as below.
   ```php 
    Route::get('/','HomeController@index');
   ``` 

=======
We can define routes in route/route.php file as below.
   ```php
    Route::get('/','HomeController@index');
   ```
# Builtin Facades:
There are some nice Facades like 

Captcha: There is available a Captcha Facade, so we can use this to render and verify captcha (helpers also available for this).

Toastr: There is a Facade for alert message in toastr.

Note:(first need to include a helper function called toastr() in html footer page) Then add Toastr Facade in any controller where you want to use it and then call its function like: 
  ```php
    Toastr::error('message') ,

    Toastr::success('message') , 

    Toastr::warning('message')

    Toastr::info('message') 
  ```


Mail Facade:

e.g:
   ```php
    Mail::set('view', $data, function($mail) {
        $mail->to('test@gmail.com', 'test');
        $mail->subject('HTML Testing Mail');
        $mail->body('This is body');
        $mail->from('test@gmail.com','test');
        $mail->send();
    });
   ```

# Builtin Pagination:
There are two type bootstrap base pagination provided by framework.
You can call on query builder as well as on model.

1. paginate()

2. simplePaginate();

Example:
   ```php  
    DB::table('users')->paginate(10);
   ```
    Or
   ```php
    $this->model('users')->paginate(10);
   ```
    
Then include below snippet to render the pagination on view page like:
   ```php
    <?php echo $render->links?>
   ```
    
# CSRF
There is a csrf token verification helper called csrf_toke() 
provided to add in each post form (it will include an input field with csrf token value)

example: 
   ```php
    <?php echo csrf_token(); ?>
   ```

    
# Helpers:
There are many default helper functions, like

captcha(): to render the captcha in html form directly.

verifyCaptcha(): to verify captcha.

# Direct access deny:

Include index.html in every directory to deny the directory listing.

Also add .htaccess in bootstrap directory to perverting direct access of autoload file

in autoload.php file define a constant called "root_path".

then add a line "define('root_path') OR exit('No direct script access allowed')" in each file at the top

# Commands:

Available commands:

For Auth Scaffolding:

    php kframe make:auth auth

Note: above command will create controllers in controllers/Auth, also will create authenticate route in route file 


For create a model:

    php kframe make:model model name
    
For create a Controller:

    php kframe make:controller controller name
   
# Register Custom Helper:
For register custom helpers file in framework, make a directory under application, create a php file in this directory then for register this helper globally in framework include name in 'config/app.php' helpers like:
   ```php 
    'helpers' =>  array('helpers/my_helper'),
   ```

For more then one:
   ```php
    'helpers' =>  array('helpers/my_helper','helpers/my_other_helper'),
   ``` 
    
# Register Custom Libraries:
For register custom library file in framework, make a directory under application, create a php file in this directory then for register this library globally in framework include name in 'config/app.php' libraries like:
   ```php
    'libraries' =>  array('libraries/my_library'),
   ```
    
 For more then one:
   ```php
    'libraries' =>  array('libraries/my_library','libraries/other_library'),
   ```
