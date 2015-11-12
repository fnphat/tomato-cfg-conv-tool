Tomato Firmware Configuration Conversion Tool
=============================================

Description
-----------

This tool converts from a [Tomato firmware](http://www.polarcloud.com/tomato) settings backup binary file to a JSON dictionary and vice versa. The format of the binary file from the Tomato firmware has been described [here](http://www.linksysinfo.org/index.php?threads/read-a-tomato-backup-config-file.33772). In short, the gunzipped file starts with the 'TCF1\r\x00\x00\x00' header followed by parameters separated by the null '\x00' character. Each parametr contains a key and a value separated by the first occurence of the '=' character.

You should be very cautious about restoring a backup binary file, you could brick your device! Of course, I am certainly not responsible for whatever damage you may cause by using this tool. Use at your own risk or do not use it!

Usage
-----
To convert a backup binary file to a JSON file:
```
#> python tomato-cfg-conv-tool.py bin2json tomato.cfg > settings.json
```

To convert a JSON file to a backup binary file:
```
#> cat settings.json | python tomato-cfg-conv-tool.py json2bin tomato--custom.cfg
```

Please have a look at the LICENSE file for more info on what is permitted to do with this code.