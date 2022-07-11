### <span class="color-yellow-400">Additional Features</span>

Swift has additional features that were not commonly covered:
1. _Large object support_
2. _Metadata_
3. _CORS_

---

### <span class="color-yellow-400">Large object support</span>

- Swift places a limit on the size of a single uploaded object (default: 5 GB).
- However, Swift can store and allowing the download of virtually unlimited-size objects.
- This is possible by uploading _object segmentation_.
- An object is broken into equal-size segments and data transfers can be done in parallel.
- Once the uploads are completed, a _manifest_ file, which shows how the segments form a single large object, is uploaded.

---

### <span class="color-yellow-400">Metadata</span>

- Swift allows custom metadata to be attached to accounts, containers, or objects that are set and retrieved in the form of custom headers.
- Metadata may be provided at the time of creating an object (using `PUT`) or updated later (using `POST`). It may be retrieved independently of the
object using the `HEAD` method.
- Eg: custom tag such as patient name, x-ray date for a medical image file.

---

### <span class="color-yellow-400">CORS</span>

- _Cross-origin resource sharing_ is a specification that allows a browser to make a request to domains other than where it came from.
- Swift supports this, and this feature makes it possible to host your web pages on one domain and request objects from a Swift cluster on another
domain.