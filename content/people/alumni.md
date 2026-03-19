---
title: Alumni
type: landing

sections:
  - block: markdown
    content:
      title: Alumni
      text: |
        | Name | Position | Active | Current Affiliation |
        |------|----------|--------|---------------------|
        {{</* range $.Site.Data.alumni */>}}
        | {{ .name }} | {{ .position }} | {{ .active }} | {{ .affiliation }} |
        {{</* end */>}}
---

<!--
NOTE: The table above uses Hugo templating to auto-generate from data/alumni.yaml.
If that doesn't render in your theme, you can use the simpler approach below
and just maintain the Markdown table directly. That's honestly fine for a list
that only changes once or twice a year.
-->
