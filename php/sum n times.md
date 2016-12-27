From: https://vijayasankarn.wordpress.com/2016/12/27/sum-n-times-php/

```
function add_time(array $times) {
    $seconds = 0;
    foreach ($times as $time)
    {
        list($hour,$minute,$second) = array_pad(explode(':', $time),3,null);
        $seconds += $hour*3600;
        $seconds += $minute*60;
        $seconds += $second;
    }
    $hours = floor($seconds/3600);
    $seconds -= $hours*3600;
    $minutes  = floor($seconds/60);
    $seconds -= $minutes*60;

    return sprintf('%02d:%02d:%02d', $hours, $minutes, $seconds);
}
```

### Example:

```
$times = ["10:20:00", "10:10:10"];
echo add_time($times); // 20:30:10

$times = ["100:20:00", "10:10"];
echo add_time($times); // 110:30:00

$times = ["100:20:00", "10:10", "10"];
echo add_time($times); // 120:30:00

$times = ["00:10:10", "00:00:10"];
echo add_time($times); // 00:10:20
````
