# Scavenger Hunt

## Description
There is some interesting information hidden around this site http://mercury.picoctf.net:55079/. Can you find it?


## Solution 


in view-source:http://mercury.picoctf.net:55079/
```html
	<!-- Here's the first part of the flag: picoCTF{t -->
```

in http://mercury.picoctf.net:55079/mycss.css

```css
/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

```
in http://mercury.picoctf.net:55079/myjs.js

```javascript
/* How can I keep Google from indexing my website? */
```
oh is clue in robots.txx

```
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?
```

in .htaccess
```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.
```

in http://mercury.picoctf.net:55079/.DS_Store

```
Congrats! You completed the scavenger hunt. Part 5: _74cceb07}
```

flag is  picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}

