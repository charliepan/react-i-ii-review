### Remember

Use https://reactjs.org/docs/react-component.html#the-component-lifecycle and http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/ to answer these on your own then compare answers as a group

1.  Each component has several `lifecycle methods` that you can override to do what?
  Life and death of a react component - change the order way things appear
2.  What are the 4 categories of lifecycle methods? (these are the headings from the first link)
Initialzation, Mounting, Updating, and Unmounting
3.  What are the names of the 5 commonly used lifecycle methods? (these are in bold in the first link)
constructor(), componentDidMount() - after the first time is render, render() - when state or props changes, componentDidUpdate(), componentWillUnmount() - before react takes it off
### Understand

Discuss this question in pairs if you have a 4-person group

4.  What's going on in this code?
"Dwight saved the day!" everytime the button is pressed
```jsx
import React, { Component } from "react";

class Mentor extends Component {
  componentDidUpdate() {
    console.log("Dwight saved the day!");
  }
  render() {
    return (
      <div>
        <h1>Dwight Schrute</h1>
        <h2>{this.props.questions.length}</h2>
        <h3>questions to answer</h3>
        <button onClick={this.props.answerQuestion}>Answer a question!</button>
      </div>
    );
  }
}
```

### Apply

Try these on your own, but work together if you start to get stuck.

5.  Update the `Mentor` component above so that the message that is currently being console.log'd is displayed below the number of questions to answer instead.
```jsx
import React, { Component } from "react";

class Mentor extends Component {
  componentDidUpdate() {
    return <p>Dwight saved the day!</p>;
  }
  render() {
    return (
      <div>
        <h1>Dwight Schrute</h1>
        <h2>{this.props.questions.length}</h2>
        <h3>questions to answer</h3>
        <button onClick={this.props.answerQuestion}>Answer a question!</button>
      </div>
    );
  }
}
```