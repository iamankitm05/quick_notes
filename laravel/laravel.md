# Laravel

#### 1. Create Project

```bash
# Create project with composer
composer create-project laravel/laravel project_name

# Create a project with laravel

# Install laravel
composer global require laravel/installer

# Create project 
laravel new project_name
```

#### 2. Setup APIs
```bash
php artisan install:api

composer require laravel/sanctum

php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
```
Routes
```php
Route::post('/logout', [AuthController::class, 'logout'])->middleware('auth:sanctum');
```

Login

```php
public function login(Request $request)
{
    $request->validate([
        'email'    => 'required|email',
        'password' => 'required'
    ]);

    if (!Auth::attempt($request->only('email', 'password'))) {
        return response()->json([
            'message' => 'Invalid credentials'
        ], 401);
    }

    $user = Auth::user();

    // Create token
    $token = $user->createToken('api_token')->plainTextToken;

    return response()->json([
        'message' => 'Login successful',
        'token' => $token,
        'user'  => $user
    ]);
}
```