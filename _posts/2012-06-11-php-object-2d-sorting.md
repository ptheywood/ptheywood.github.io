---
layout: post
title:  "PHP Object 2D Sorting"
date:   2012-06-11
categories: php oop
excerpt: "Welcome to the latest iteration of my personal website."
---

For a project at work I needed to sort an array of objects by multiple dimensions, so I experimented with `uasort` to figure out an easy way of doing this. This is here more for when I forget how to do it than anything else.

First let's create a super simple test class and some test data.

{% highlight php linenos %}
<?php
    Class Foo {
        public $x, $y, $z;

        public function __construct($x, $y, $z){
            $this->x = $x;
            $this->y = $y;
            $this->z = $z;
        }

        public function __toString(){
            return 'Foo('.$this->x.', '.$this->y.', '.$this->z.')';
        }

        public static function printArr($array){
            foreach($array as $obj){
                echo $obj;
                echo "\n";
            }
        }
    }

    // Sample data
    $data = array(
        new Foo(10,'abc',0),
        new Foo(15,'bcd',1),
        new Foo(15,'ab',2),
        new Foo(5,'abc',3),
    );
?>
{% endhighlight %}

Simple one dimensional sorting functions can then be written using a ternary if statement, where two objects `$a` and `$b` are compared to return `1`, `0` or `-1` to show if the object should be sorted higher, the same or lower than the other.

{% highlight php linenos %}
<?php
    function orderByY($a, $b){
        return ( $a->y == $b->y ) ? 0 : ( $a->y > $b->y ) ? 1 : -1 ;
    }

    $copy = $data;
    uasort($copy, 'orderByY');
    Foo::printArr($copy);
?>
{% endhighlight %}

Which would output the following:

    Foo(15, ab, 2)
    Foo(10, abc, 0)
    Foo(5, abc, 3)
    Foo(15, bcd, 1)


Combining 2 of these functions together gives way to the solution for sorting in 2D based on object properties.

{% highlight php linenos %}
<?php
    function orderByXThenY($a,$b){
        return (
            ($a->x > $b->x) ? 1 :                      //If a > b ->  1
                (($a->x < $b->x) ? -1 :           //If a < b -> -1
                    (($a->y > $b->y) ? 1:               //If a > b ->  1
                        (($a->y < $b->y) ? -1 : 0 )))   //If a < b -> -1 else 0 (equal)
        );
    }

    $copy = $data;
    uasort($copy, 'orderByXThenY');
    Foo::printArr($copy);
?>
{% endhighlight %}

Outputting the following:

    Foo(5, abc, 3)
    Foo(10, abc, 0)
    Foo(15, ab, 2)
    Foo(15, bcd, 1)