# laravel-tricks

#List All Middleware

function getMiddlewareList(){
    $collection = collect(Route::getRoutes())->map(function($r){
        if(isset($r->action['middleware']))
            return $r->action['middleware'];
    })->flatten();
    return array_unique($collection->toArray());
}
