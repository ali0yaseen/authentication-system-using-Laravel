# Laravel Auth Task (Sanctum)

## Installation
1. Install Laravel Sanctum
   composer require laravel/sanctum

2. Publish & Migrate
   php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
   php artisan migrate

3. Update Kernel (app/Http/Kernel.php)
   'api' => [
       \Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful::class,
       'throttle:api',
       \Illuminate\Routing\Middleware\SubstituteBindings::class,
   ],

4. Update User model (app/Models/User.php)
   use Laravel\Sanctum\HasApiTokens;

5. Done. Use the AuthController and api.php routes provided.
