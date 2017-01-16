# Templates for Laravel 5 CRUD Generator by Appzcoder - with no dependencies

## Installation of Crud Generator and where to put these files

1. Run
    ```
    composer require appzcoder/crud-generator
    ```

2. Add the service provider to **config/app.php**.
    ```php
    'providers' => [
        ...

        Appzcoder\CrudGenerator\CrudGeneratorServiceProvider::class,
    ],
    ```
    
3. Run ```composer dump-autoload```

4. Publish vendor files of this package. (Note: You should have configured database for this operation.)
    ```
    php artisan vendor:publish --provider="Appzcoder\CrudGenerator\CrudGeneratorServiceProvider"
    ```
    
5. Copy the folder **resources/crud-generator** into your Laravel application.

6. In your laravel app, in the file config/crudgenerator.php activate custom templates:
	```
	  'custom_template' => true,	
	```
7. Restart your local dev server (stop running server and type **php artisan serve**  in the terminal)

8. For more documentation and how to use, visit: https://github.com/appzcoder/crud-generator
