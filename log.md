wordpress/wp-includes/wp-db.php

function _do_query

$this->result =  下面添加

```php
<?php
  $log_str = $_SERVER['PHP_SELF'].PHP_EOL."[".date("H:i:s")."]".$query.PHP_EOL.str_repeat('-',50).PHP_EOL;
  error_log($log_str, 3, WP_CONTENT_DIR."/Log/".date("Y_m_d").".log");
```
注意 wordpress/wp-content/Log/ 的权限 和 缓存


