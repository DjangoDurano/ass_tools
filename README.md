# **Ass Tools**

## **requirements:**

- install requirements.txt


    pip install -r requirements.txt


## **split_out_new_style.py**


**Description:**
- splits out a style from aegisub tags and creates a new style

**Functions:**
- creating new style from tags in ass line
- checks if style exists even if style name is not the same
- skip line if two font tags (\fn) are set, no font tag is set
- at this point following tags will be also set (Bold, Italic, Fontsize, Border, Color incl. Alpha)
- creates a new ass with these styles
- delete tags from ass line after creating new style
- if tags not correct line will be skipped

**Example:**

``{\i0\b0\fnTahoma\bord1}Test.``

This will create follow style:

```
Style: New_style 1,Tahoma,20,&H00FFFFCA,&H000000FF,&H000000FF,&H000000FF,0,0,0,0,100,100,0,0,1,1,2,2,10,10,10,1
```

**Usage:**

1. **Use in another script**

```python
from split_out_new_style import SplitStyle

new_style = SplitStyle(style_name='Your prefer style name')

new_style.spilt(source='path to ass', output_file='output path incl. filename')
```
- **style_name:** set own name or leave it blank → name "New Style" || style names will be numbered sequentially
- **output_file:** set own path to output file, leave it blank → source_path/split_ass.ass

2. **Use standalone**


    python split_out_new_style.py source

- answer questions for own style name and output file

