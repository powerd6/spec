# Creating content

Creating content means writing arbitrary sets of data into a distributable format.

Usually, this means writing text or encoding images into a JSON object.

## Encoding non-textual data

Not all data that is required for your content will be representable as plaintext.

Images, videos, and files are great examples of content that cannot simply be defined as text.

For this purpose, we encode all the data as [Data URIs encoded with base64](https://en.wikipedia.org/wiki/Data_URI_scheme).

For example, the following data URI string `data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAAHElEQVQI12P4//8/w38GIAXDIBKE0DHxgljNBAAO9TXL0Y4OHwAAAABJRU5ErkJggg==` represents the following image of a dot: 
![a red dot](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAAHElEQVQI12P4//8/w38GIAXDIBKE0DHxgljNBAAO9TXL0Y4OHwAAAABJRU5ErkJggg== "The Image")

In markdown, this looks like this:

```md
![a red dot](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAAHElEQVQI12P4//8/w38GIAXDIBKE0DHxgljNBAAO9TXL0Y4OHwAAAABJRU5ErkJggg== "The Image")
```