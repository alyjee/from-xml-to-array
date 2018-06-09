# Conversion from xml to an array
A package inspired by vyuldashev/xml-to-array to convert an xml to array

Inspired by Vyuldashev's [xml-to-array](https://github.com/vyuldashev/xml-to-array) ❤️ 

## Install

You can install this package via composer.

``` bash
composer require alyjee/from-xml-to-array
```

## Usage

```php
use Alyjee\XmlToArray\XmlToArray;

$xml = '<items><Facilities><Facility Code="*EC"><![CDATA[Earliest check-in at 14:00]]></Facility><Facility Code="*LF"><![CDATA[1 lift]]></Facility><Facility Code="*RS"><![CDATA[Room Service from 18:00 to 21:00]]></Facility></Facilities></items>';

$result = XmlToArray::convert($xml);
```
After running this piece of code `$result` will contain:

```php
Array
(
    [items] => Array
        (
            [Facilities] => Array
                (
                    [Facility] => Array
                        (
                            [0] => Array
                                (
                                    [_attributes] => Array
                                        (
                                            [Code] => *EC
                                        )

                                    [_cdata] => Earliest check-in at 14:00
                                )

                            [1] => Array
                                (
                                    [_attributes] => Array
                                        (
                                            [Code] => *LF
                                        )

                                    [_cdata] => 1 lift
                                )

                            [2] => Array
                                (
                                    [_attributes] => Array
                                        (
                                            [Code] => *RS
                                        )

                                    [_cdata] => Room Service from 18:00 to 21:00
                                )

                        )

                )

        )

)
```
