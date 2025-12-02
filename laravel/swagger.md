# Swagger

[Swagger Documentation Website](https://zircote.github.io/swagger-php/)


### 1. Install Swagger-PHP Library

You’ll need the Swagger-PHP library to generate Swagger documentation. Install it using Composer:


```bash
composer require zircote/swagger-php
```

### 2 Generate Swagger Annotations

In your controller methods, use Swagger annotations to document your API. Here’s an example of how to annotate a controller method:

```php
/**
 * @SWG\Get(
 *     path="/users",
 *     summary="Get a list of users",
 *     tags={"Users"},
 *     @SWG\Response(response=200, description="Successful operation"),
 *     @SWG\Response(response=400, description="Invalid request")
 * )
 */
public function index()
{
    // Your API logic here
}
```

### 3. Install darkaonline package 

```bash
composer require darkaonline/l5-swagger

# Now, publish the Swagger configuration:
php artisan vendor:publish --provider "L5Swagger\L5SwaggerServiceProvider"
```

### 4. Generate Swagger Documentation

```bash
php artisan l5-swagger:generate
```