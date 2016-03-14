Take snapshots of React Native views and cache to device storage.


# DEPRECATION NOTE

This feature is being introduced to React Native core as of version 0.22.0.

https://github.com/facebook/react-native/commit/ac12f986899d8520527684438f76299675dc0daa

## Installation

```
% npm i --save react-native-view-snapshot
```

In XCode, in your project, add the .m and .h files to your Library folder.

## Usage

For a full example, build the included ViewSnapshotExample project.

This library exposes a single method, *saveSnapshotToPath*. Example usage:

```
var ViewSnapshotter = require('react-native-view-snapshot');

ViewSnapshotter.saveSnapshotToPath(React.findNodeHandle(this.refs.someView), somePath, (error, successfulWrite) => {
    if (successfulWrite) {
        this.setState({catSaved: true})
    } else {
      console.log(error)
    }
});
```

## Use cases

* storing performant copies of complex static views, such as a set of layered PNGs with alpha transparency
* sharing/uploading of snapshots specific view hierarchies, such as an image with a text overlay
