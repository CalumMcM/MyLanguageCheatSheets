### Comment

```css
/*
Multi line comment
*/
```



### justify-content

```css
/*CONTAINER MUST CONTAIN:*/
display: flex;
/* PLUS: */
justify-content: flex-start; /*Align items to left of container*/
justify-content: flex-end; /*Align items to right side of container*/
justify-content: center; /*Align items in the center of the container*/
justify-content: space-between; /*Display items with equal spacing between them*/
justify-content: space-around; /*Display items with equal spacing around them*/
```



### align-items

```css
/*CONTAINER MUST CONTAIN:*/
display: flex;
/* PLUS: */
align-items: flex-start;/*Items align to the top of the container*/
align-items: flex-end; /*Items align to the bottom of the container*/
align-items: center; /*Items align at vertical center of the container*/
align-items: baseline; /*Items display at baseline of the container*/
align-items: stretch; /*Items are stretched to fit container*/
```

### align-self

```css
/*CONTAINER MUST CONTAIN:*/
display: flex;
/* PLUS: */
align-self: flex-start;/*Item is align to the top of the container*/
align-self: flex-end; /*Item is align to the bottom of the container*/
align-self: center; /*Item is align at vertical center of the container*/
align-self: baseline; /*Item is display at baseline of the container*/
align-self: stretch; /*Item is stretched to fit container*/
```

### flex-direction

```css
/*CONTAINER MUST CONTAIN:*/
display: flex;
/* PLUS: */
flex-direction: row; /*Items are placed the same as the text direction*/
flex-direction: row-reverse; /*Items are placed opposite to the text direction*/
flex-direction: column; /*Items are placed top to bottom*/
flex-direction: column-reverse; /*items are placed bottom to top*/
```

### flex-wrap

```css
/*CONTAINER MUST CONTAIN:*/
display:flex;
/* PLUS: */
flex-wrap: nowrap; /*Every item is fit to a single line */
flex-wrap: wrap; /*Items wrap around to additional lines*/
flex-wrap: wrap-reverse; /*Items wrap around to additional lines in reverse*/
```

### flex-flow

```css
/*
This combines both flex-direction and flex-wrap.
*/
/*CONTAINER MUST CONTAIN:*/
display:flex;
/* PLUS: */
flex-flow: /*flex-direction value*/ /*flex-wrap value*/;
```

### order

```css
order: X; /*Will move the item X places to the right (if negative the left) */
```

### align-content

```css
/*Allows you to control how multiple lines are spaced apart from each other*/
*/
/*CONTAINER MUST CONTAIN:*/
display:flex;
/* PLUS: */
align-content: flex-start; /*Lines are packed at the top of the container*/
align-content: flex-end; /*Linea re packed at the bottom of the container*/
align-content: center; /*Lines are packed at the vertical center of the container*/
align-content: space-between; /*Lines display with equal spacing between them*/
align-content: space-around; /*Lines display with equal spacing around them*/
align-content: stretch; /*Lines are stretched to fit the container*/
```

### margin

```css

```

