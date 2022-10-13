# Learning-repository

# Markdown Commands

[https://www.markdownguide.org/](https://www.markdownguide.org/)  
[https://www.markdownguide.org/cheat-sheet/](https://www.markdownguide.org/cheat-sheet/)  
[https://www.markdownguide.org/basic-syntax/](https://www.markdownguide.org/basic-syntax/)  
[https://www.markdownguide.org/extended-syntax](https://www.markdownguide.org/extended-syntax)


# Headings

| Markdown                | HTML                        |
|-------------------------|-----------------------------|
| # Heading level 1       | `<h1>Heading level 1</h1>`  |
| ## Heading level 2      | `<h2>Heading level 2</h2>`  |
| ### Heading level 3     | `<h3>Heading level 3</h3>`  |
| #### Heading level 4    | `<h4>Heading level 4</h4>`  |
| ##### Heading level 5   | `<h5>Heading level 5</h5>`  |
| ###### Heading level 6  | `<h6>Heading level 6</h6>`  |


#### Rendered Output

# Heading level 1
## Heading level 2
### Heading level 3
#### Heading level 4
##### Heading level 5
###### Heading level 6

	

## Alternate Syntax

#### Markdown code

    Heading level 1
    =================

    Heading level 2
    ----------------


#### HTML

    <h1>Heading level 1</h1>
    <h2>Heading level 2</h2>


#### Rendered Output

Heading level 1
=================

Heading level 2
----------------



## Heading Comparision

# Heading level 1
Heading level 1
=================
## Heading level 2
Heading level 2
-----------------

### Do this

    # Here's a Heading

# Here's a Heading

### Don't do this

    #Here's a Heading

#Here's a Heading


### Do this

    Try to put a blank line before...

    # Heading

    ...and after a heading.

Try to put a blank line before...

# Heading

...and after a heading.

### Don't do this

    Without blank lines, this might not look right.
    # Heading
    Don't do this!

Without blank lines, this might not look right.
# Heading
Don't do this!

# Paragraphs

#### Markdown code

    I really like using Markdown.

    I think I'll use it to format all of my documents now on.


#### HTML

    <p>I really like using Markdown.</p>
    <p>I think I'll use it to format all of my documents from now on.</p>


#### Rendered Output

I really like using Markdown.

I think I'll use it to format all of my documents now on.

## Paragraph Best Practices

### Do this

    Don't put tabs or spaces in front of your pragraphs.

    Keep lines left-aligned like this.

Don't put tabs or spaces in front of your pragraphs.

Keep lines left-aligned like this.

### Don't do this

    This can result in unexpected formatting problems.

  Don't add tabs or spaces in front of paragraphs.

# Line Breaks

#### Markdown code

    This is the first line.  
    And this is the second line.


#### HTML

    <p>This is the first line.<br>
    And this is the second line.</p>


#### Rendered Output

This is the first line.  
And this is the second line.

## Line Break Best Practices

### Do this

    First line with two spaces after.  
    And the next line.

First line with two spaces after.  
And the next line.

    First line with the HTML tag after.<br>
    And the next line.

First line with the HTML tag after.<br>
And the next line.

### Don't do this

    First line with a backslash after.\
    And the next line.

First line with a backslash after.\
And the next line.

    First line with nothing after.
    And the next line.

First line with nothing after.
And the next line.

# Bold

#### Rendered Output

    I just love **bold text**.  
    I just love __bold text__.  
    Love**is**bold


#### HTML

    I just love <strong>bold text</strong>.
    I just love <strong>bold text</strong>.
    Love<strong>is</strong>bold


#### Rendered Output

I just love **bold text**.  
I just love __bold text__.  
Love**is**bold

## Bold Best Practices

### Do this

    Love**is**bold

Love**is**bold

### Don't do this

    Love__is__bold

Love__is__bold


# Italic

#### Markdown code

    Italicized text is the *cat's meow*.

    Italicized text is the _cat's meow_.

    A*cat*meow


#### HTML

    Italicized text is the <em>cat's meow</em>.
    Italicized text is the <em>cat's meow</em>.
    A<em>cat</em>meow


#### Rendered Output

Italicized text is the *cat's meow*.

Italicized text is the _cat's meow_.

A*cat*meow.


## Italic Best Practices

### Do this

    A*cat*meow

A*cat*meow

### Don't do this

    A_cat_meow

A_cat_meow


# Bold and Italic

#### m

    This text is ***really important***.

    This text is ___really important___.

    This text is __*really important*__.

    This text is **_really important_**.

    This is really***very***important text.


#### HTML

    This text is <em><strong>really important</strong></em>.
    This text is <em><strong>really important</strong></em>.
    This text is <em><strong>really important</strong></em>.
    This text is <em><strong>really important</strong></em>.
    This is really<em><strong>very</strong></em>important text.


#### Rendered Output

This text is ***really important***.

This text is ___really important___.

This text is __*really important*__.

This text is **_really important_**.

This is really***very***important text.


## Bold and Italic Best practices

### Do this

    This is really****very***important text.

This is really***very***important text.

### Don't do this

    This is really___very___important text.

This is really___very___important text.


# Blockquotes

    > Dorothy followed her through many of the beautiful rooms in her castle.

> Dorothy followed her through many of the beautiful rooms in her catle.


## Blockquotes with Multiple Paragraphs

    > Dorothy followed her through many of the beautiful rooms in her castle.
    >
    > The witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.


## Nested Blockquotes

    > Dorothy followed her through many of the beautiful rooms in her castle.
    >
    >> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

> Dorothy followed her through many of the beautiful rooms in her castle.
> 
>> the Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.


## Blockquotes with Other Elements

    > ####  The quarterly results look great!
    >
    > - Revenue was off the chart.
    > - Profits were higher than ever.
    >
    > *Everything* is going according to **plan**.


> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
> *Everything* is going according to **plan**.


## Blockquotes Best Practices

### Do this

    Try to put a blank line before...

    > This is a blockquote

    ...and after a blockquote.

Try to put a blank line before...

> This is a blockquote

... and after a blockquote.


### Don't do this

    Without blank lines, this might not look right.
    > This is a blockquote
    Don't do this!

With blank lines, this might not look right.
> This is a blockquote.
don't do this!


# Ordered Lists

#### Markdown code

    1. First item
    2. Second item
    3. Third item
    4. Fourth item


#### HTML

    <ol>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item</li>
        <li>Fourth item</li>
    </ol>


#### Rendered Output

1. First item
2. Second item
3. Third item
4. Fourth item


#### Markdown code

```
1. First item
1. Second item
1. Third item
1. Fourth item
```


#### HTML

    <ol>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item</li>
        <li>Fourth item</li>
    </ol>


#### Rendered Output

1. First item
1. Second item
1. Third item
1. Fourth item


#### Markdown code

```
1. First item
8. Second item
3. Third item
5. Fourth item
```

#### HTML

    <ol>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item</li>
        <li>Fourth item</li>
    </ol>


#### Rendered Output

1. First item
8. Second item
3. Third item
5. Fourth item


#### Markdown code

```
1. First item
2. Second item
3. Third item
    1. Indented item
    2. Indented item
4. Fourth item
```

#### HTML

    <ol>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item
            <ol>
            <li>Indented item</li>
            <li>Indented item</li>
            </ol>
        </li>
        <li>Fourth item</li>
    </ol>


#### Rendered Output

1. First item
2. Second item
3. Third item
    1. Indented item
    2. Indented item
4. Fourth item


## Order List Best Practices

### Do this

    1. First item
    2. Second item


1. First item
2. Second item


### Don't do this

    1) First item
    2) Second item


1) First item
2) Second item


# Unordered Lists

#### Markdown code

    - First item
    - Second item
    - Third item
    - Fourth item


#### HTML

    <ul>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item</li>
        <li>Fourth item</li>
    </ul>


#### Rendered Output

- First item
- Second item
- Third item
- Fourth item


#### Markdown code

```
* First item
* Second item
* Third item
* Fourth item
```


#### HTML

    <ul>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item</li>
        <li>Fourth item</li>
    </ul>


#### Rendered Output

* First item
* Second item
* Third item
* Fourth item


#### Markdown code

```
+ First item
+ Second item
+ Third item
+ Fourth item
```

#### HTML

    <ul>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item</li>
        <li>Fourth item</li>
    </ul>


#### Rendered Output

+ First item
+ Second item
+ Third item
+ Fourth item


#### Markdown code

```
- First item
- Second item
- Third item
    - Indented item
    - Indented item
- Fourth item
```

#### HTML

    <ul>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item
            <ul>
            <li>Indented item</li>
            <li>Indented item</li>
            </ul>
        </li>
        <li>Fourth item</li>
    </ul>


#### Rendered Output

- First item
- Second item
- Third item
    - Indented item
    - Indented item
- Fourth item


## Starting Unordered List Items with Numbers

#### Markdown code

    - 1968\. A great year!
    - I think 1969 was second best.


#### HTML Output

    <ul>
        <li>1968. A great year!</li>
        <li>I think 1969 was second best.</li>
    </ul>


#### Rendered Output


- 1968\. A great year!
- I think 1969 was second best.


## Unordered List Best Practices

### Do this

    - First item
    - Second item
    - Third item
    - Fourth item

- First item
- Second item
- Third item
- Fourth item


### Don't do this

    + First item
    * Second item
    - Third item
    + Fourth item


+ First item
* Second item
- Third item
+ Fourth item
