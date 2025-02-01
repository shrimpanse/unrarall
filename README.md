## unrarall


unrarall attemps to extract all supported archive files in a given directory 
(and its sub-directories) and once successfully extracted can execute 
pre-defined cleaning and processing functions (see the list shown in `--help`).
It is meant to be more error proof and quicker than cleaning by hand. 
You can also set an output folder, use different backends, perform sfv checks 
automatically, etc...

If there's something you would like to have done by unrarall then you can 
implement your own hooks (see [HACKING](HACKING)).

> [!NOTE]  
> This fork implements zip and 7zip handling. There is also a new cleanup hook
  for setting a new owner or new permissions to extracted files 
  (`set_user_rights`).

> [!CAUTION]  
> I consider this more of a quick hack because I haven't written any tests yet. 
  Further work amd refactoring is needed.

## SUPPORTED FILE TYPES / EXTENSIONS

| File type | Mime type                                                      | Extensions             |
| --------- | -------------------------------------------------------------- | ---------------------- |
| RAR       | application/vnd.rar, application/x-rar                         | .rar, .partX.rar, .001 |
| ZIP       | application/zip, application/x-zip-compressed, multipart/x-zip | .zip                   |
| 7-ZIP     | application\/x-7z-compressed                                   | .7z, 7z.001            | 

## INSTALL

1. Mmake sure you set the "executable" permission. This
   can be done using the following command:

```
chmod u+x unrarall
```

2. Place the script wherever you want and rename it to whatever you want. 
   To use it globally putting it in `/usr/local/bin` is recommended.

## USAGE

Run unrarall with all cleanups on current directory
```
unrarall --clean=all .
```

Run with an output directory on the current directory
```
unrarall --output /tmp/mystuff .
```

Run `unrarall -h` to get the help for much more details.

Enjoy.

## ACKNOWLEDGEMENTS

Fork of the excellent [unrarall](https://github.com/arfoll/unrarall) by [arfoll](https://github.com/arfoll)  
Original name and idea comes from "jeremy" see -
http://askubuntu.com/questions/7059/script-app-to-unrar-files-and-only-delete-the-archives-which-were-sucessfully

