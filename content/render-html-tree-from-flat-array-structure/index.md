---
title: "Render HTML tree from flat array structure"
description: "First step is to convert flat array into Hierarchy. “Render HTML tree from flat array structure” is published by React Engineer"
date: "2018-09-06T09:46:45.647Z"
categories: 
  - React
  - Html5 Development
  - Flatarrayhierarchy

published: true
canonical_link: https://medium.com/@reactjavascript/render-html-tree-from-flat-array-structure-be6b3a35e24f
redirect_from:
  - /render-html-tree-from-flat-array-structure-be6b3a35e24f
---

![](./asset-1.png)![](./asset-2.png)

First step is to convert flat array into Hierarchy

```
const hierarchy = products.reduceRight((child, obj) => {
 if (child) {
  return [Object.assign({}, obj, { child })];
 }
 return [obj];
 }, null);
```

This will return

![](./asset-3.png)

---

```
const renderHierarchy = child => child.map(hierarchy => (
 <Node node={hierarchy}>
 {hierarchy.child}
 </Node>
));
```

**Node.jsx**

```
import React from ‘react’;
import PropTypes from ‘prop-types’;

const propTypes = {
 children: PropTypes.array,
 node: PropTypes.object,
};

const defaultProps = {
 children: null,
 node: <div />,
};

export default function Node({ children, node }) {
 let childnodes = null;

// the Node component calls itself if there are children
 if (children) {
 childnodes = children.map(childnode => (
 <Node node={childnode} >
 {childnode.child}
 </Node>
 ));
 }

// return our list element
 // display children if there are any
 return (
 <li key={node.id}>
 <span>{node.name}</span>
 { childnodes ?
 <ul>{childnodes}</ul>
 : null }
 </li>
 );
}

Node.propTypes = propTypes;
Node.defaultProps = defaultProps;
```

**Test your output**

![](./asset-4.png)
