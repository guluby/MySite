# Markdown Notes
> Taking notes of Markdown syntax    
> Source: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#h4
## **Header**
>Header size controlled by number of #, `# Header, ## Header etc`

## __Emphasis__

>*Italic*, `Add asterisks or underscores to text, *text* or _text_`

>**Bold**, `Add double asterisks or underscores, **text** or __text__`

>**_Bold and Italic_**, `Combine italic and bold **_text_**`

>~~Strikethrough~~, `Two tildes, ~~text~~`


## **Code and syntax highlighting**

```python
s = "Python syntax highlighting"
print(s)
```

## **Page break**   

**Code:**
```
---
```
**Results:**

---


## __List__
#### _Numbered list_ 
**Code:** _number before dot does not matter_
```
1. First ordered list item
1. Another list item
     * Unordered sub-list. * can be + or -  
```
**Results:**
>1. First ordered list item
>1. Another item  
  >   * Unordered sub-list., * can be + or -  


#### _List with indentation_

**Code:** leading and trailing spaces are shown with with dots: ⋅
```
1. list item⋅⋅
⋅⋅⋅Line break need to use two trailing spaces.⋅⋅
⋅⋅⋅Text continue 
```
**Results:**
>1. list item  
 Line break need to use two trailing spaces.  
 Text continue
 

## **Links**
**Code:**
```
  [inline style link](www.google.com)  
  [inline style link with title tag](www.google.com "Google Homepage")  
  [relative reference to a repository file](../githubusername/master/file)  
  [Reference link later][link text]
  
  [link text]: http://www.google.com
```  


**Results:**
> [inline style link](www.google.com)  
  [inline style link with title tag](www.google.com "Google Homepage")  
  [relative reference to a repository file](../githubusername/master/file)  
  [Reference link later][link text]
  
  [link text]: http://www.google.com
  

## **Image**

**Code:**
```
![text](link)
Inline-style:
![description](https://github.com/usrname/project/master/src/picture.png "Description text")

Reference-style:
![description][picture]

[picture]:(https://github.com/usrname/project/master/src/picture.png "Description text"
```

**Results:**

Inline-style:
![description](https://github.com/usrname/project/master/src/picture.png "Description text")

Reference-style:
![description][picture]

[picture]:(https://github.com/usrname/project/master/src/picture.png "Description text"

## **Table**

**Code:**
```
item1 | item2 | item3
--- | --- | ---
*Still* | `renders` | **markdown syntax**
1 | 2 | 3
```

**Results:**  

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **markdown syntax**
1 | 2 | 3

