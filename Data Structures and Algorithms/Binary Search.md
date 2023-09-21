#Computer-Science #programming #Algorithm 
## PHP
```php
    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer
     */   
function search($nums, $target) {
    $low=0;
    $high=sizeof($nums)-1;
    echo "Initial low= ",$low," Initial high= ",$high;
        while ($low<=$high) {
            $mid=floor(($low + $high)/2);
            if ($target==$nums[$mid]) {
                return $mid;
            }
            elseif($target>$nums[$mid]){
                $low=$mid+1;
            }
            elseif($target<$nums[$mid]){
                $high=$mid-1;
            }
        }      
    return -1;
}
```

