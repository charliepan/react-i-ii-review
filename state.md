### Remember

Answer these on your own, then compare answers as a group

1.  What is state?
  The state is like the attributes/properties of a component
2.  Where do you set initial state?
  In the constructor
3.  What method do you use to update state?
 this.setState()
### Understand

Discuss this question in pairs if you have a 4-person group

4.  Explain what's happening in this component.
Counting the number of answered questions when button is pressed.
Adding 1 to the questionsAnswered state when the button is pressed.
```jsx
import React, { Component } from "react";

class LeadMentor extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questionsAnswered: 0
    };

    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({ questionsAnswered: this.state.questionsAnswered + 1 });
  }
  render() {
    <div className="lead-mentor-container">
      <h1>Michael Scott</h1>
      <h3>{this.state.questionsAnswered}</h3>
      <h3>questions answered today</h3>
      <button onClick={this.handleClick}>Increase Answers</button>
    </div>;
  }
}
```

### Apply

Try these on your own, but work together if you start to get stuck.

5.  Create a `Student` component that keeps track of the number of questions the student has asked, with a button that adds 1 to the total when it's clicked
```jsx
import React, { Component } from "react";

class Student extends Component {
  constructor() {
    super();

    this.state = {
      questionsAsked: 0
    };

    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({ questionsAsked: this.state.questionsAsked + 1 });
  }
  render() {
    <div>
      <h1>Dwight Strutt</h1>
      <h3>{this.state.questionsAsked}</h3>
      <h3>questions asked today</h3>
      <button onClick={this.handleClick}>Increase Questions</button>
    </div>;
  }
}
```
6.  Now add a text input where the student can type in their questions with a button to add them to a list of questions that is displayed below the number of questions asked.

```jsx
import React, { Component } from "react";

class Student extends Component {
  constructor() {
    super();

    this.state = {
      questionsAsked: 0,
      userInput: '',
      questions: []
    };

    this.handleClick = this.handleClick.bind(this);
    this.handleChange = this.handleChange.bind(this);
  }
  handleClick() {
    this.setState({ questionsAsked: this.state.questionsAsked + 1,  });
  }

  handleChange(val){
    this.setState({userInput: val});
  }

  render() {
    <div>
      <h1>Dwight Strutt</h1>
      <h3>{this.state.questionsAsked}</h3>
      <h3>questions asked today</h3>
      <input onChange={(e)=>this.handleChange(e.target.value)} placeholder='Enter you question'/>
      <button onClick={this.handleClick}>Increase Questions</button>
      {questions}
    </div>;
  }
}
```

### Analyze, Evaluate, Create

Discuss these questions as a group

7.  Could your `Student` component be refactored into a functional component? Why or why not?

8.  What are the pros and cons of using a class method for an event handler vs. using an arrow function inline?

9.  The render() method is called every time a component's state is updated. For a text input, that means the render method is called for every keypress. Why isn't this bad for performance?
