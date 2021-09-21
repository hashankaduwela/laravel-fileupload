composer create-project laravel/laravel --prefer-dist laravel-file-upload

cd laravel-file-upload

DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=laravel_db
DB_USERNAME=root
DB_PASSWORD=

php artisan make:model File -m

routes
Route::get('/upload-file', [FileUpload::class, 'createForm']);
Route::post('/upload-file', [FileUpload::class, 'fileUpload'])->name('fileUpload');

php artisan make:controller FileUpload

storage/public/uploads

php artisan serve

http://127.0.0.1:8000/upload-file

https://www.positronx.io/laravel-file-upload-with-validation/