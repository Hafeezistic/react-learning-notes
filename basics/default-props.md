# Default Props

```jsx
import React from "react"

function Card(props) {
    const styles = {
        backgroundColor: props.cardColor,
        height: 100,
        width: 100
    }
    
    return (
        <div style={styles}></div>
    )
}

// Default Props
Card.defaultProps = {
    cardColor: "blue"
} 

export default Card
```

This works the same way when it comes to class components. but you can also define a **static** class property inside the class:

```jsx
class Card extends React.Component {
    static defaultProps = {
        cardColor: "blue",
        height: 100,
        width: 100
    }
    
    render() {
        const styles = {
            backgroundColor: this.props.cardColor,
            height: this.props.height,
            width: this.props.width
        }
        
        return (
            <div style={styles}></div>
        )
    }
}
```