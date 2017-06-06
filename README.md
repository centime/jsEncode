# jsEncode

Text to javascript encoder. Just run the js to get the text back.


No, it doesn't have any real purpose nor foreseen application. I guess you could maybe use it to send a fancy messages to a fellow hacker ?

For more useless js experiments, see [https://github.com/centime/reverJS](reverJS) and [https://github.com/centime/jsfsck](jsf$ck)


## Example

	> jsEncode('javascript is fun')
	'(-((_=($=+!![])-~$)-++_)*(+[$]+[_-~_]+[_-~$]+[$-$]+[\
	_-$]+[$-$]+[_-$]+[$-$]+[_]+[-~_-~$]+[$]+[-~_-~$]+[-~_\
	-~$]+[$-$]+[_+_]+[_-~_]))[_$=((_$=(!![]+[]))[$_=+[]]+\
	[[]+{}][$_][$]+[+[]+($$=([]+[])[(![]+{})[[$]+$_]+({}+\
	_$)[$]+([]+_$[_$])[$]+(!_$+_$)[$-~$]+_$[$_]+_$[$]+_$[\
	-~$]+(![]+{})[[$]+$_]+_$[$_]+({}+_$)[$]+_$[$]])][$_][\
	$+[$_]]+_$[$_]+_$[$]+([![]]+[][[]])[$+[$_]]+([][[]]+[\
	])[$]+(![]+[$_]+$$)[$+$+[$_]])]($_=$-~$+[(_)-~$])+($$\
	=[!![]+{}][$-$][$+[$]])+($*(+[_-~$]+[-~_-~$]+[_-~$]))\
	[_$]($_)+$$+($*(+[-~$]+[$-$]+[-~_]+[_]+[_-$]))[_$]($_)'

	> eval(jsEncode('javascript is fun'))
	'javascript is fun'

## Limitations

Currently supported:
	lowercases
	numbers
	spaces
	words of 10 chars max.

Could potentially be supported:
	long words
	more punctuation

## The code:

it's really just this simple function:

```js
/*------   https://github.com/centime/jsEncode    ------*/
jsEncode=(s)=>(r='',s.replace(/[^a-z0-9 ]/g,' ').split(' '
).forEach((w,i)=>(r+=(i==0?'':i>1?'+$$':'+($$=[!![]+{}][$\
-$][$+[$]])')+(w?(n=(i>0?'+($':'(-((_=($=+!![])-~$)-++_)')
+'*(',String(parseInt(w,36)).split('').forEach((l)=>n+='+\
['+['$-$','$','-~$','_-$','_','-~_','_-~$','-~_-~$','_+_',
'_-~_'][l]+']'),n+(i>0?'))[_$]($_)':'))[_$=((_$=(!![]+[])\
)[$_=+[]]+[[]+{}][$_][$]+[+[]+($$=([]+[])[(![]+{})[[$]+$_\
]+({}+_$)[$]+([]+_$[_$])[$]+(!_$+_$)[$-~$]+_$[$_]+_$[$]+_\
$[-~$]+(![]+{})[[$]+$_]+_$[$_]+({}+_$)[$]+_$[$]])][$_][$+\
[$_]]+_$[$_]+_$[$]+([![]]+[][[]])[$+[$_]]+([][[]]+[])[$]+\
(![]+[$_]+$$)[$+$+[$_]])]($_=$-~$+[(_)-~$])')):''))),r)

```
