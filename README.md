# Template customization


## public
I hope you have seen this template `public` folder on the downloaded package `Appo - React App Landing Page` from ThemeForest.

In this `public` folder you can see `index.html` file. This file structure is like this-

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!--meta, title, google fonts, all css linking here-->
</head>

<body>

  <div id="root"></div>
 
 <!--all js linking here-->
</body>

</html>
```

All HTML content will be load into this `div`:
```html
<div id="root"></div>
```


## entry points

##### index.js
Template `index.js` structure looks like this-
```js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();

```

##### app.js
Template `app.js` structure looks like this-
```js
import React from 'react';

// importing MyRouts where we located all of our theme
import MyRouts from './routers/routes'

function App() {
  return (
    <div>
      <MyRouts />
    </div>
  );
}

export default App;

```


## themes

`themes` folder included on `src` folder. You can check our folder structure on `src` folder menu.
This is `theme` folder structure-
```text
|-- themes
    |-- theme-one.js ( default theme)
    |-- theme-two.js ( demo theme 2)
    .....
    |-- theme-nine.js ( demo theme 9 )
```

`theme` folder contains all of our 9 demos.


## routes
In `routers` folder we used `routes.js`. Where we linked all the route for our all theme. For routing we used react-router-dom.

Routes: `routers/routes.js`

```js
import React from "react";
import { BrowserRouter as Router, Route, Switch } from "react-router-dom";

// importing all the themes
import ThemeOne from "../themes/theme-one";
import ThemeTwo from "../themes/theme-two";
import ThemeThree from "../themes/theme-three";
import ThemeFour from "../themes/theme-four";
import ThemeFive from "../themes/theme-five";
import ThemeSix from "../themes/theme-six";
import ThemeSeven from "../themes/theme-seven";
import ThemeEight from "../themes/theme-eight";
import ThemeNine from "../themes/theme-nine";
import AboutUs from "../components/innerSection/about/about-us";
import Pricing from "../components/innerSection/pricing/pricing";
import Reviews from "../components/innerSection/reviews/reviews";
import Faq from "../components/innerSection/faq/faq";
import Login from "../components/innerSection/login/login";
import Signup from "../components/innerSection/signup/signup";
import Download from "../components/innerSection/download/download";
import ThankYou from "../components/innerSection/thankyou/thankyou";
import Forgot from "../components/innerSection/forgot/forgot";
import Newsletter from "../components/innerSection/newsletter/newsletter";
import ErrorOne from "../components/innerSection/error/errorOne/error-one";
import ErrorTwo from "../components/innerSection/error/errorTwo/error-two";
import Contact from "../components/innerSection/contact/contact";
import Maintenance from "../components/innerSection/maintenance/maintenance";
import ComingSoon from "../components/innerSection/comingSoon/coming-soon";
import BlogTwoColumn from "../components/blogs/blog-two-column";
import BlogThreeColumn from "../components/blogs/blog-three-column";
import BlogLeftSidebar from "../components/blogs/blog-left-sidebar";
import BlogRightSidebar from "../components/blogs/blog-right-sidebar";
import BlogDetailsLeftSidebar from "../components/blogs/blog-details-left-sidebar";
import BlogDetailsRightSidebar from "../components/blogs/blog-details-right-sidebar";

class MyRouts extends React.Component {
  render() {
    return (
      <div>
        <Router>
          <Switch>
            <Route exact path="/" component={ThemeOne} />
            <Route exact path="/theme-two" component={ThemeTwo} />
            <Route exact path="/theme-three" component={ThemeThree} />
            <Route exact path="/theme-four" component={ThemeFour} />
            <Route exact path="/theme-five" component={ThemeFive} />
            <Route exact path="/theme-six" component={ThemeSix} />
            <Route exact path="/theme-seven" component={ThemeSeven} />
            <Route exact path="/theme-eight" component={ThemeEight} />
            <Route exact path="/theme-nine" component={ThemeNine} />
            <Route exact path="/about-us" component={AboutUs} />
            <Route exact path="/pricing" component={Pricing} />
            <Route exact path="/reviews" component={Reviews} />
            <Route exact path="/faq" component={Faq} />
            <Route exact path="/login" component={Login} />
            <Route exact path="/signup" component={Signup} />
            <Route exact path="/download" component={Download} />
            <Route exact path="/thankyou" component={ThankYou} />
            <Route exact path="/forgot" component={Forgot} />
            <Route exact path="/newsletter" component={Newsletter} />
            <Route exact path="/error-one" component={ErrorOne} />
            <Route exact path="/error-two" component={ErrorTwo} />
            <Route exact path="/contact" component={Contact} />
            <Route exact path="/maintenance" component={Maintenance} />
            <Route exact path="/coming-soon" component={ComingSoon} />
            <Route exact path="/blog-two-column" component={BlogTwoColumn} />
            <Route exact path="/blog-three-column" component={BlogThreeColumn} />
            <Route exact path="/blog-left-sidebar" component={BlogLeftSidebar} />
            <Route exact path="/blog-right-sidebar" component={BlogRightSidebar} />
            <Route exact path="/blog-details-left-sidebar" component={BlogDetailsLeftSidebar} />
            <Route exact path="/blog-details-right-sidebar" component={BlogDetailsRightSidebar} />
          </Switch>
        </Router>
      </div>
    );
  }
}
export default MyRouts;

```


## components
Under `components` folder we wrote all of our components individually. 
We have written these components to make the developer’s life easy. 
By using these basic components, For example in our components directory there is `headerSection`, `welcomeSection` , `footerSection` folder where we wrote our different styled component. For example `welcomeSection` component-

### Component folder structure
```text
|-- components
    ....
    |-- welcomeSection ( hero component folder )
        - welcomeOne.js ( main demo welcome section )
        - welcomeTwo.js ( demo two welcome section )
        ...... ( and other )
        
    |-- contactSection ( contact folder )
        - contact.js
    .
    ..
    ...    
```

### Contact Section component
`contactSection/contact.js`
```js
import React, { Component } from 'react';
import axios from 'axios';

const BASE_URL = "https://my-json-server.typicode.com/themeland/appo-json-2/themeOneContactSection";

class contactSection extends Component {
    state = {
        data: {}
    }
    componentDidMount(){
        axios.get(`${BASE_URL}`)
            .then(res => {
                this.setState({
                    data: res.data
                })
                // console.log(this.state.data)
            })
        .catch(err => console.log(err))
    }
    render() {
        return (
            <section id="contact" className="contact-area bg-gray ptb_100">
                <div className="container">
                    <div className="row justify-content-center">
                        <div className="col-12 col-md-10 col-lg-6">
                            {/* Section Heading */}
                            <div className="section-heading text-center">
                                <h2 className="text-capitalize">{this.state.data.heading}</h2>
                                <p className="d-none d-sm-block mt-4">{this.state.data.headingText}</p>
                                <p className="d-block d-sm-none mt-4">{this.state.data.headingTextTwo}</p>
                            </div>
                        </div>
                    </div>
                    <div className="row">
                        <div className="col-12">
                            {/* Contact Box */}
                            <div className="contact-box text-center">
                            {/* Contact Form */}
                            <form id="contact-form" method="POST" action="assets/php/mail.php">
                                <div className="row">
                                    <div className="col-12 col-md-6">
                                        <div className="form-group">
                                        <input type="text" className="form-control" name="name" placeholder="Name" required="required" />
                                        </div>
                                        <div className="form-group">
                                        <input type="email" className="form-control" name="email" placeholder="Email" required="required" />
                                        </div>
                                        <div className="form-group">
                                        <input type="text" className="form-control" name="subject" placeholder="Subject" required="required" />
                                        </div>
                                    </div>
                                    <div className="col-12 col-md-6">
                                        <div className="form-group">
                                        <textarea className="form-control" name="message" placeholder="Message" required="required" defaultValue={""} />
                                        </div>
                                    </div>
                                    <div className="col-12">
                                        <button className="btn btn-bordered mt-3 mt-sm-4" type="submit">Send Message</button>
                                    </div>
                                </div>
                            </form>
                            <p className="form-message" />
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        );
    }
}

export default contactSection;
```

## theme installtion
To install the theme you have to install [react](https://create-react-app.dev/) than go to the theme root dir where `package.json` located and use
```bash
npm install
```
it will install the packages.

After install process now you can run local server- local server port is 'http://localhost:3000' For developement start use
```bash
npm start
```
## Build your theme
```bash
npm run build
```

## For deployment -- static server
First install
```bash
npm install -g serve
serve -s build
```
If you want to know more about static deployment please visit [Create react app deployment](https://create-react-app.dev/docs/deployment)

Enjoy your theme :)
