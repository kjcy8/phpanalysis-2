# phpanalysis
基于phpanalysis的功能封装,方便使用php语言分词

## 安装插件
```
composer require lmz/phpanalysis
```


```
use Phpanalysis\PhpAnalysis;

PhpAnalysis::$loadInit = false;
$pa = new PhpAnalysis('utf-8', 'utf-8', true);

//载入词典
$pa->LoadDict();

//执行分词
$pa->SetSource('在西安国际港站，8台龙门吊正在同时吊装来自世界各地的集装箱。每天，从这里出发和抵达的中欧班列“长安号”有十余列，联通省内外20多座城市和45个“一带一路”沿线国家和地区。');
$pa->differMax = true;
$pa->unitWord = true;
$pa->StartAnalysis(true);

$okresult = $pa->GetFinallyResult(',', false);

print_r($okresult);
```
