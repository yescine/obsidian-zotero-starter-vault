---
year: {{date | format("YYYY")}}
year: note/zotero
authors: {{authors}}
DOI: {{DOI}}
Collections: {{collections[0].fullPath |dump}}  
Related: {{related}}  
Tags: {{hashTags}}, #Literature
---

## {{title}}

### Formatted Bibliography

{{bibliography}}
{% if abstractNote %}

### Abstract

{{abstractNote}}
{% endif %}

### Annotations

{% for annotation in annotations %}
#### anno {{loop.index}}
{% if annotation.imageRelativePath %}
![[{{annotation.imageRelativePath}}]]{% endif %}
{% if annotation.annotatedText %}
{{annotation.annotatedText}}
{% endif %}
{% if annotation.comment %}
{{annotation.comment}}
{% endif %}

##### meta data
- types: {{annotation.type}}
- page {{annotation.page}}
- color: {{annotation.color}}
- colorCategory {{annotation.colorCategory}}
- tags {{annotation.tags | dump }} {% for tag in annotation.tags%}
	- #zotero_annotations/{{tag.tag}} {% endfor %}

{% endfor %}