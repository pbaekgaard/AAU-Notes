a) The case f is expanded and we add the 
```
case f
	if(s.peek() == "l") {
		consume("loat");
	}
```

Consume is defined to s.advance through out those letters.

b) 

```
case i
	if(s.peek() == "n") {
		consume("nt");
	}
```

c)
To enable entering exponential scientific form, we further elaborate the scandigits procedure to check for the *e*.


4. 
```
procedure Prog()
	call Dcls()
	call Stmts()
	call MATCH(ts, $)
end	
```

```
procedure Dcls()
	if ts.peek() = floatdcl or ts.peek() = intdcl
	then
		call Dcl()
		call Dcls()
	else
		if ts.peek() = '$'
		then
			/* Do Nothing */
		else
			call ERROR()
end
```
```
procedure Dcl()
	if ts.peek() = floatdcl
	then
		call MATCH(ts, floatdcl)
		call MATCH(ts, id)
	else
		if ts.peek() = intdcl
			call MATCH(ts, intdcl)
			call MATCH(ts, id)
		else
			call ERROR()
end	
```