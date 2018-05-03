# Cozy Code Guidelines

## Generic code style

```
"eslintConfig": {
    "extends": ["eslint-config-cozy-app"]
  },
  "prettier": {
    "semi": false,
    "singleQuote": true
  },
```

Let the formatters do their jobs.

## Promises vs async/await

Always use async / await when applicable.

## Class constructors

Avoid `constructor` if you can by leveraging `transform-class-properties`

❌  Bad :

```
class MyComponent extends Component {
  constructor () {
    super()
    this.state = { counter: 0 }
  }
}
```

✅  Good

```
class MyComponent extends Component {
  this.state = { counter: 0 }
}
```

## Binding event handlers

Avoid binding event handlers in `constructor`, leverage `transform-class-properties`
and arrow functions.

❌  Bad :

```
class MyComponent extends Component {
  constructor () {
    super()
    this.onClick = this.onClick.bind(this)
  }

  onClick (ev) {
    ...
  }
}
```

✅  Good

```
class MyComponent extends Component {
  this.onClick = (ev) => {
    ...
  }
}
```

## What is Cozy?

![Cozy Logo](https://raw.github.com/cozy/cozy-setup/gh-pages/assets/images/happycloud.png)

[Cozy](http://cozy.io) is a platform that brings all your web services in the
same private space.  With it, your web apps and your devices can share data
easily, providing you with a new experience. You can install Cozy on your own
hardware where no one profiles you.

## Community

You can reach the Cozy Community by:

* Chatting with us on IRC #cozycloud on irc.freenode.net
* Posting on our [Forum](https://forum.cozy.io)
* Posting issues on the [Github repos](https://github.com/cozy/)
* Mentioning us on [Twitter](http://twitter.com/mycozycloud)
