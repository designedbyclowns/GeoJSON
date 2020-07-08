# GeoJSON

This is a Swift package for working with [GeoJSON](https://geojson.org) data. It contains necessary types conforming to `Codable` for easy de-/encoding of data.

## Usage

### Encoding

Create a `Document` (alias of `FeatureCollection`) or just a single `Feature` to create a GeoJSON file. 

```swift
let document = Document(features: [
    Feature(
        geometry: .point(Point(longitude: 125.6, latitude: 10.1)),
        properties: [
            "name": "Dinagat Island"
        ]
    )
])

let json = try JSONEncoder().encode(document)
```

### Decoding

It works the same way in the other direction. Use a standard `JSONDecoder` to decode GeoJSON data into a fitting type.

```swift
let document = try JSONDecoder().decode(Document.self, from: json)
```

## Installation

This package is available via Swift Package Manager, add its clone URL to your project to get started.
