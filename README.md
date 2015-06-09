模板用法：
<?php
    // Setup custom Twig view
    $twigView = new \Slim\Extras\Views\Twig();

    // Instantiate application
    $app = new \Slim\Slim(array(
        'view' => $twigView
    ));
?>

中间件用法：
<?php
$app = new \Slim\Slim();
$app->add(new \Slim\Extras\Middleware\HttpBasicAuth('username', 'password'));
?>

日志用法：
<?php
$app = new \Slim\Slim(array(
    'log.writer' => new \Slim\Extras\Log\DateTimeFileWriter(array(
        'path' => './logs',
        'name_format' => 'Y-m-d',
        'message_format' => '%label% - %date% - %message%'
    ))
));
?>
确认 `logs/`和`templates/cache` 可写.
