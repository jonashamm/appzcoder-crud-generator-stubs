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
	
**Steps 7 and 8 are not a good practice, but I had no success so far in overwriting package functions the "right" way:**
	
7. In **vendor/appzcoder/crud-generator/src/Commands/CrudViewCommand.php** change this line:
	```
	$labelText = "'" . ucwords(strtolower(str_replace('_', ' ', $item['name']))) . "'";
	```
	to 
	```
	$labelText = ucwords(strtolower(str_replace('_', ' ', $item['name'])));
	```
	
8. Again in **vendor/appzcoder/crud-generator/src/Commands/CrudViewCommand.php** add the following line to the function templateFormVars:
	```
	File::put($newFormFile, str_replace('%%crudNameSingular%%', $this->crudNameSingular, File::get($newFormFile)));
	```
9. Restart your local dev server (stop running server and type **php artisan serve**  in the terminal)

10. For more documentation and how to use, visit: https://github.com/appzcoder/crud-generator
