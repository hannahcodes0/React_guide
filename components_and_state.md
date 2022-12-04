While props and state both hold information relating to the component, they are used differently and should be kept separate.

Props
function Welcome(props) {
return <h1>Hello {props.name}</h1>;
}
props (short for properties) are a Component's configuration, its options if you may. They are received from above and immutable as far as the Component receiving them is concerned. During a component’s life cycle props should not change.

A Component cannot change its props, but it is responsible for putting together the props of its child Components.

A component can also have default props, so if a prop isn’t passed through it can still be set.

We can make the name property optional by adding defaultProps to the Welcome class:

class Welcome extends React.Component {
render() {
return <h1>Hello {this.props.name}</h1>;
}
}

Welcome.defaultProps = {
name: "world",
};
State
When a component needs to keep track of information between renderings the component itself can create, update, and use state.

The state starts with a default value when a Component mounts and then suffers from mutations in time (mostly generated from user events). It's a serializable\* representation of one point in time—a snapshot.

A Component manages its own state internally, but—besides setting an initial state—has no business fiddling with the state of its children. You could say the state is private.
