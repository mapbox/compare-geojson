# osm-compare


![](https://img.shields.io/npm/v/@mapbox/osm-compare.svg)
[![Circle CI](https://circleci.com/gh/mapbox/osm-compare.svg?style=svg)](https://circleci.com/gh/mapbox/osm-compare)


Compare functions are small atomic functions that are designed identify what changed during a feature edit on OpenStreetMap. Compare functions can be broadly split up into two categories:

1. Property (tags) checking compare function
2. Geometry checking compare functions

Compare functions take as inputs the following:

1. `oldVersion` - GeoJSON of the feature's old version
2. `newVersion` - GeoJSON of the feature's new version
3. `callback` - A function to call after processing.

Compare functions output the following:

1. `error` - Error if any during processing or `null`.
2. `result` - Object containing key value pairs representing findings of the compare function or an empty object.

```sh
# Format of compare function result where value can be primary data types or objects
{
    'result:comparator_name': value
}

# Format of compare function if no result, (default)
{
    'result:comparator_name': {}
}

```

## Install

```sh
# Install osm-compare from the Mapbox namespace.
npm install @mapbox/osm-compare
```


### Docs

- [How do I create a new compare function](https://github.com/mapbox/osm-compare/blob/master/docs/new-compare-function.md)
- [Sample compare function](https://github.com/mapbox/osm-compare/blob/master/example)
- [What does each compare function do](https://github.com/mapbox/osm-compare/blob/master/comparators/README.md)


### How do I build an npm package?
- We use [Semantic Versioning Specification](http://semver.org/) for versioning releases.
- Create an appropriate version of the npm package with `npm version [major|minor|patch]`.
- Push the package tag commit with `git push --tags`
- [Publish the NPM package](https://www.npmjs.com/package/osm-compare) with `npm publish`
