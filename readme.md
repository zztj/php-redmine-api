# PHP Redmine API

> A simple Object Oriented wrapper for Redmine API, written with PHP5.
* 官方介绍[https://github.com/kbsali/php-redmine-api](https://github.com/kbsali/php-redmine-api)

>这里具体写下laravel下的自己的使用方法给可能需要的人，其他调用方法看官方[demo](https://github.com/kbsali/php-redmine-api/blob/master/example.php)
* 安装
````bash
$ composer require kbsali/redmine-api:~1.0
````
* 使用
````php
<?php
namespace App\Http\Controllers;
use Redmine\Client;
class DemoController extends Controller
{
    private $client;
    public function __construct()
    {
        $this->client = new Client('http://redmine.demo.com', 'demo', '123456');
    }
    public function index(){
        $projects = $this->client->project->all();
        dump($projects);
        $users = $this->client->user->all();
        dump($users);
    }
}
````