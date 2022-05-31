function quickSort($arr)
{
    if (empty($arr)) return [];
    $pilot = $arr[0];
    $left = [];
    $right = [];
    for ($i = 1; $i < count($arr); $i++) {
        if ($arr[$i] < $pilot) {
            $left[] = $arr[$i];
            continue;
        }
        $right[] = $arr[$i];
    }
    return array_merge(quickSort($left), [$pilot], quickSort($right));
}

function insertionSort($arr)
{
    $length = count($arr);
    for ($i = 1; $i < $length; $i++) {
        for ($j = $i; $j > 0; $j--) {
            if ($arr[$j] < $arr[$j-1]) {
                $temp = $arr[$j];
                $arr[$j] = $arr[$j-1];
                $arr[$j-1] = $temp;
                continue;
            }
            break;
        }
    }
}

function bubbleSort($arr) {
    $length = count($arr);
    for ($i = 0; $i < $length -1; $i++) {
        for($j = $i+1; $j < $length; $j++) {
            if ($arr[$i] < $arr[$j]) {
                $temp = $arr[$i];
                $arr[$i] = $arr[$j];
                $arr[$j] = $temp;
            }
        }
    }
}

function selectionSort($arr) {
    $length = count($arr);
    for($i = 0; $i < $length -1; $i++) {
        $minIndex = $i;
        for ($j = $i + 1; $j < $length; $j++) {
            if ($arr[$minIndex] > $arr[$j]) {
                $minIndex = $j;
            }
        }
        if ($minIndex != $i) {
            $temp = $arr[$i];
            $arr[$i] = $arr[$minIndex];
            $arr[$minIndex] = $temp;
        }
    }
    return $arr;
}
