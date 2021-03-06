# week07day04-react

## Multiple Page Application vs Single Page Application

### MPA
<p>Multiple-page applications work in a traditional way. Every change eg. display the data or submit data back to server requests rendering a new page from the server in the browser.</p>

![multiple-page-application](images/multiple-page-application.jpg)


<p>For almost every action that changes what the browser displays, the web app navigates you to a whole different page. This is a big deal, users will see as pages get torn down and redrawn. This has a big impact on how you maintain your app state.</p>


### SPA
<p>Single-page Application never navigate to different pages or ever even reload a page. In SPA, the different views of your app are loaded and unloaded into the same page itself.
</p>

![single-page-application](images/single-page-application.jpg)

[Simple SPA](https://www.kirupa.com/react/examples/react_router/index.html#/)

## Virtual DOM
<p>Because actual DOM modifications are really slow, you never modify the DOM directly. Instead, you modify an in-memory Virtual DOM. The Virtual DOM gives us a javascript representation of the actual DOM. When changes are made to the view we want to show, we update the Virtual DOM first(Manipulating the Virtual DOM is extremely fast), which then checks the diffs between what was changed to what is currently rendered, and changes ONLY the pieces that need to be changed, rather than re-rendering the entire page.</p>

![virtual-dom](images/virtual-dom.jpg)


## Components
<p>Components are pieces of our application that we can define once and reuse all over the place. With components, there is more integration and less separation of HTML, CSS, and JavaScript. Instead of creating a few large files, you will organize your web app into small, reusable components that encompass their own content, presentation, and behavior.</p>


![components](images/comonents.png)

### Discussion: Identifying Components

Take a look at [CraigsList](https://boston.craigslist.org/search/aap) (note: right click to open in a new tab!).

Each listing is a component. How can you identify this?
- Listings look identical in structure, but have different information populating them
- Listings are dynamically generated based on the user's search

### Lab: Identifying Components

Now, go to [Amtrak.com](https://www.amtrak.com/home) (note: right click to open in a new tab!). We want to look at the listing page, so put in any "From" (for example, New York - Penn Station), any "To" (for example, Boston - South Station), and pick any date. Hit "Find Trains". Now look at the listing page:

![Amtrak](https://git.generalassemb.ly/storage/user/5747/files/754db814-30fb-11e8-88c2-04ed98ab1834)

Scrolling down it, identify the visual "components" the website is comprised of. We suggest drawing this out on paper!

As you're drawing this out, think about the following questions...

* Where do you see "nested components;" that is, where are there components inside another component? Where do you see just one "layer" instead?
* Are there any components that share the same structure?
* For components that share the same structure, what is different about them?

## JSX

#### Element
```js
const element = <h1>Hello, world!</h1>;
```

#### Multiple Elements
- wrap in `()`
- must have 1 single parent element
```js
const introductionElements = (
  <header>
    <h1>Hello, world!</h1>
    <h2>Welcome to my app</h2>
  </header>
);
```

#### Self Closing Tags
- need to end the tag with `/>` to close the tag
```js
const selfClosingExamples = (
  <div>
    <img src="path.jpg" />
    <br />
    <hr />
  </div>
);

```
 
#### Interpolation 
```js
const name = 'Maha';
const element = <h1>Hello, {name}</h1>;
```

#### Interpolation with functions
```js
const formatName = (user) => user.firstName + ' ' + user.lastName;

const user = {
  firstName: 'Ahmed',
  lastName: 'Tahir'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

```

#### Ternary Operator instead of `if` statement
```js
const name = 'Sami';

const element = (
  <h1>
    {name === 'Sami' ? 'Hello Sami the wise' : 'Hello ' + name}
  </h1>
)

```

#### Classes
- use `className`
```js
const element = <h1 className='intro intro-alert'>Hello World</h1>;
```

#### Comments
```js
const name = 'Sami';

const element = (
  <h1>
    {/* 
      Checks if the user is Sami for a custom message
      If not Sami then just says Hello and the user name
    */}  
    {name === 'Sami' ? 'Hello Sami the wise' : 'Hello ' + name}
  </h1>
)

```
- [JSX visual compiler](https://babeljs.io/repl/)

## React Site Examples

- [React](examples/03.react-site-intro)
- [React with JSX](examples/04.react-site-babel)
- [React with JSX & Classes](examples/05.react-site-babel-classes)

## Create React App

- [Create React App](https://github.com/facebook/create-react-app)
