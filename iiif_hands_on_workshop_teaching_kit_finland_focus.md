# IIIF Hands-On Workshop Teaching Kit (Finland Focus)

## Overview
This teaching kit provides everything needed to run a 1–2 day hands-on IIIF workshop using Finnish cultural heritage materials. It includes slide outlines, datasets, manifests, and code examples.

---

# 1. Slide Deck (Instructor Outline)

## Slide 1: Title
- Hands-On IIIF Workshop
- Exploring Finnish Cultural Heritage

## Slide 2: What is IIIF?
- International Image Interoperability Framework
- Standard APIs for images and presentation

## Slide 3: Why IIIF Matters
- Interoperability
- Deep zoom
- Reuse across institutions

## Slide 4: IIIF APIs
- Image API
- Presentation API

## Slide 5: Key Concepts
- Manifest
- Canvas
- Annotation

## Slide 6: Finnish Data Sources
- National Library collections
- Museum collections

## Slide 7: Demo
- Load a manifest in a viewer

## Slide 8: Hands-On Activity
- Explore a Finnish newspaper

## Slide 9: Manifest Structure
- JSON structure
- label, items, metadata

## Slide 10: Editing a Manifest
- Change labels
- Add metadata

## Slide 11: Viewers
- Mirador
- Universal Viewer

## Slide 12: Embedding IIIF
- HTML + JS example

## Slide 13: Annotation
- What is annotation?

## Slide 14: Final Project
- Build a mini exhibit

---

# 2. Datasets (Finland-Themed)

## Dataset A: Historical Newspapers (National Library of Finland)
Example IIIF Manifests:
- https://digi.kansalliskirjasto.fi/iiif/manifest/binding/2247835
- https://digi.kansalliskirjasto.fi/iiif/manifest/binding/2675678

## Dataset B: Historical Maps (Finnish Heritage Agency / Finna)
Example IIIF Manifests:
- https://api.finna.fi/record?id=musketti.M012:HK7155:219-65-1&field[]=imagesExtended
- https://api.finna.fi/record?id=musketti.M012:HK7155:219-65-2&field[]=imagesExtended

## Dataset C: Photographs (Finna / Museums)
Example IIIF Manifests:
- https://api.finna.fi/record?id=hkm.HKMS000005:km0000n4g&field[]=imagesExtended
- https://api.finna.fi/record?id=hkm.HKMS000005:km0000abc&field[]=imagesExtended

## Dataset D: Books and Manuscripts (National Library of Finland)
Example IIIF Manifests:
- https://digi.kansalliskirjasto.fi/iiif/manifest/binding/1886487
- https://digi.kansalliskirjasto.fi/iiif/manifest/binding/1934562

---

# 3. Ready-to-Use IIIF Manifest

```json
{
  "@context": "http://iiif.io/api/presentation/3/context.json",
  "id": "https://example.org/iiif/manifest/finland-demo",
  "type": "Manifest",
  "label": { "en": ["Finnish Cultural Collection"] },
  "items": [
    {
      "id": "https://example.org/canvas/1",
      "type": "Canvas",
      "height": 2000,
      "width": 1500,
      "items": [
        {
          "id": "https://example.org/page/1",
          "type": "AnnotationPage",
          "items": [
            {
              "id": "https://example.org/annotation/1",
              "type": "Annotation",
              "motivation": "painting",
              "body": {
                "id": "https://example.fi/iiif/photo1/full/full/0/default.jpg",
                "type": "Image",
                "format": "image/jpeg"
              },
              "target": "https://example.org/canvas/1"
            }
          ]
        }
      ]
    }
  ]
}
```

---

# 4. Code Examples

## A. Basic HTML + Mirador Viewer

```html
<!DOCTYPE html>
<html>
<head>
  <script src="https://unpkg.com/mirador@latest/dist/mirador.min.js"></script>
</head>
<body>
<div id="viewer" style="height: 600px;"></div>
<script>
Mirador.viewer({
  id: "viewer",
  windows: [{
    manifestId: "https://example.org/iiif/manifest/finland-demo"
  }]
});
</script>
</body>
</html>
```

## B. Universal Viewer Embed

```html
<iframe src="https://universalviewer.io/uv.html#?manifest=https://example.org/iiif/manifest/finland-demo"
width="800" height="600"></iframe>
```

---

# 5. Hands-On Exercises

## Exercise 1: Explore a Manifest
- Open provided manifest
- Identify label, items, images

## Exercise 2: Modify Metadata
- Change title
- Add description

## Exercise 3: Build Your Own Manifest
- Use 2–3 Finnish images

## Exercise 4: Embed a Viewer
- Use provided HTML

## Exercise 5: Annotate an Image
- Add a simple annotation JSON

---

# 6. Final Project Template

Participants create:
- A IIIF manifest
- A webpage with embedded viewer
- At least 1 annotation

---

# 7. Instructor Notes

- Preload datasets to avoid network issues
- Provide manifest URLs in advance
- Pair beginners with advanced users

---

# 8. Additional Resources

- IIIF documentation: https://iiif.io
- Mirador docs: https://projectmirador.org
- Universal Viewer: https://universalviewer.io

---

# 9. Optional Extensions

- OCR integration
- AI-generated metadata
- Linked data enrichment

---

End of Teaching Kit

