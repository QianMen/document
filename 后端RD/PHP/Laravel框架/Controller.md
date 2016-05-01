######获取表单提交的数据

```php
use Illuminate\Support\Facades\Request;

public function sample() {
  //获取输入的全部数据
  $all    = Request::all();
  //获取输入的某一个数据
  $single = Request::input('sample');
}
```
