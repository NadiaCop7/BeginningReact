## Chapter 2
Every bit of react you encounter will be made up of those basic JS building blocks. Lets dissect a React component and then blend the two!


React CLASS component. With the introduction of hooks, we will be able to simplify components to be functional and still use and change state (useState, useReducer). Our code base still heavily contains class components, so we need to know how to read them. 

here is a class component skeleton:

```
class SomeComponent extends React.Component {
   render() {
     return(
        <div></div>
    );
};
```


Thats it!  Of course we need to add organs and muscle that do stuff for this skeleton. Those organs and muscles come in the form of all of the javascript stuff we just reviewed. For example:

```
class SomeComponent extends React.Component {

function doCodeStuff()  {    <————muscle, does stuff for your skeleton :)
        return code stuff
}

const stringThing = “I am a string”;   <———— organ, provides something you need :)

   render() {
     return(
        <div></div>
    );
};
```

You can also create variables, functions, etc within the render method, but keep in mind if you need it to be accessible in other functions etc, you should put it above the render method and call it with “this” when it is needed.

A note about `this`. The `this` keyword is used throughout our JS files and goes away with typescript for the most part. The simplest way to understand this, is that “this” is data that lives in this document, but outside of its respective scope. A function that is being called outside of its scope, say,  in the render/return,  it will look like the arrow below:

```
class SomeComponent extends React.Component {

function doCodeStuff()  {
        return code stuff
}

const stringThing = “I am a string”;

   render() {
     
     return(
        <div>{this.doCodeStuff()}</div>   <------------This is Here! :D 
    );
};
```

Since you are not new devs, no need to get into super detail…but calling on a function, array, object or variable will look very much the same except with its respective syntax. If you need a reminder, don’t hesitate to hit any of your team mates up! :) 

Thats it! This is your class component. It will always have a scope (denoted by curly braces) that include a render method, and that render method will return jsx (the code that has the html looking stuff). **NOTE:** Everything before the render method: 

```
class SomeComponent extends React.Component {

//////////////////// <————— this area 

   render() {
     return(
        <div></div>
    );
};
```

 and everything between the render and the return of this method: 

```
class SomeComponent extends React.Component {
   render() {
/////////////////// <————— and this area
     return(
        <div></div>
    );
};
```

Are javascript. You CAN return some jsx, but we will get to that later.  Now, everything in the return of the render:

```
class SomeComponent extends React.Component {
   render() {
     return(
        <div></div> <—————— right here
    );
};
```

is jsx, and looks and behaves a lot like html. Here you will use all your favorite html tags, and then some! `<div/>`, `<h1/>`, `<img/>` etc. and of course other components as tags, `<Page/>` `<LeadForm/>` for example. You can add attributes like you do in regular html…classname, id, etc…we will get more into detail on this in a bit. Also, this is the area that has special syntax, most notably curly braces to do the logical stuff or else it will render the view…. quite literally.

`<div>5 + 5</div>` will render 5 + 5 on your browser.

`<div>{5 + 5}</div>` will do math and render 10 on your browser. When you need logic to occur and have data at play, use curly braces :D 

**Attributes for attitude!**

What would we be without the things that make us unique? Like us, jsx tags have attributes to add to its character.  Lets start using some real world examples:

```
<PropertyDetails
  className="font-size--m sa-child sa-child--3"
  baseClass="property-info"
  property={this.props.property}
  isLDP={this.props.isLDP}
  snipe={this.props.snipe}
 />
 ```


`<PropertyDetails/>` is a react component that is being instantiated by using it in “html tag” form with some attributes. One you definitely know, `className`, is a regular attribute html uses, and it is NO different when used for styling on a react component. You can add an `img=“”` or `src=“”` attribute the same way, but the most common use of attributes on a jsx-html style instantiated component is to pass data between it to another component via… you’ve heard it a 1000 times, props! In the above example -the attributes called property, isLDP, and snipe are all being passed data as props. This makes sense if you consider how an object has key-value pairs, aka properties and their values. If you want another component to be able to use ones information, you can pass that data via props.

Lets break this down!

`property = {this.props.property}`

`property`= this is the attribute. You could technically name this anything when using javascript, you could say `myHouse={this.props.property}`, but shouldn’t. When getting to typescript you have to be very specific.

`this` = calling an item on “this” document.

`props` = the declaration that this is a prop (which will also require assigning it a type, either through PropTypes at the top of the file in JS, or type-interface in TS)

`property` = the actual data point. In this case, it will be the property object that comes back from the api and has ALL info you need to know about the property eg: address, beds, baths, city, agents etc. The data here won't always be an object type, but can be a primitive as well.

Note:
you can get more specific and deeper into the object with dot syntax. Lets say you wanted to JUST render the property address, you could write: 

`property={this.props.property.address}`

**Using JSX outside of the return()**

Now you know how I mentioned earlier that all code before the render is simple  JS variables and functions. Well cool story bro…on a file.jsx or file.tsx, you can return jsx in a  function! Reminder, jsx is the html looking stuff. 

Example: 

```
renderCarouselPageButton(direction, handleClickFunc) {
    if (!this.props.showSearchPagination) {
      return null;
    }

    return (
      <div
        className={`carousel__carousel-page-btn carousel__carousel-page-btn--${direction} font-weight--bold`}
        {...buttonize(handleClickFunc)}
      >
        <Icon className="icon--prev" name="keyboard-arrow-left" />
        <Icon className="icon--next" name="keyboard-arrow-right" />
      </div>
    );
  }
  ```

Examine the above and notice it is a named function with conditional logic, and returns jsx! It is no different than when you return on any other languages function. Here we return 2  instances of the Icon component in a div, with the curly braces giving us back data.

