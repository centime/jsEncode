# jsIsFun

Small js experiment, similar to [https://github.com/centime/reverJS](reverJS) and [https://github.com/centime/jsfsck](jsf$ck) in that it has no real purpose or application.

I guess you could still use it if you want to send a fancy "private" message.


## Example

	> jsIsFun('javascript is fun')
	'_$=((_$=(!![]+[]))[_=+[]]+[[]+{}][_][$=+!![]]+[+[]+\
	($$=([]+[])[(![]+{})[[$]+_]+({}+_$)[$]+([]+_$[_$])[$\
	]+(!_$+_$)[$-~$]+_$[_]+_$[$]+_$[-~$]+(![]+{})[[$]+_]\
	+_$[_]+({}+_$)[$]+_$[$]])][_][$+[_]]+_$[_]+_$[$]+([!\
	[]]+[][[]])[$+[_]]+([][[]]+[])[$]+(![]+[_]+$$)[$+$+[\
	_]]),$_=$-~$+[(_=$-~$+$)-~$],$$=[!![]+{}][$-$][$+[$]\
	],(+!![]*(+[$]+[_-~_]+[_-~$]+[$-$]+[_-$]+[$-$]+[_-$]\
	+[$-$]+[_]+[-~_-~$]+[$]+[-~_-~$]+[-~_-~$]+[$-$]+[_+_\
	]+[_-~_]))[_$]($_)+$$+(+!![]*(+[_-~$]+[-~_-~$]+[_-~$\
	]))[_$]($_)+$$+(+!![]*(+[-~$]+[$-$]+[-~_]+[_]+[_-$])\
	)[_$]($_)'

	> eval(jsIsFun('javascript is fun'))
	'javascript is fun'

## Limitations

Only lowercase letters, numbers, and spaces are supported. If your text contains other characters, the ouput will not match it exactly.

## The code:

it's really just this simple function:

```js
jsIsFun=(s)=>(r='_$=((_$=(!![]+[]))[_=+[]]+[[]+{}][_]\
[$=+!![]]+[+[]+($$=([]+[])[(![]+{})[[$]+_]+({}+_$)[$]\
+([]+_$[_$])[$]+(!_$+_$)[$-~$]+_$[_]+_$[$]+_$[-~$]+(!\
[]+{})[[$]+_]+_$[_]+({}+_$)[$]+_$[$]])][_][$+[_]]+_$[\
_]+_$[$]+([![]]+[][[]])[$+[_]]+([][[]]+[])[$]+(![]+[_\
]+$$)[$+$+[_]]),$_=$-~$+[(_=$-~$+$)-~$],$$=[!![]+{}][\
$-$][$+[$]],',s.split(' ').forEach((w,i)=>r+=(i>0?'+$\
$':'')+(n=(i>0?'+':'')+'(+!![]*(',String(parseInt(w,36
)).split('').forEach((l)=>n+='+['+['$-$','$','-~$','_\
-$','_','-~_','_-~$','-~_-~$','_+_','_-~_'][l]+']'),n+
'))[_$]($_)')),r) /*-----  github.com/centime  -----*/
```
