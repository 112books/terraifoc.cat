---
title: "{{ replace .Name "-" " " | title }}"
language: {{ if in .Dir "en/" }}en{{ else }}ca{{ end }}
---
