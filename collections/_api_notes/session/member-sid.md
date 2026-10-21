---
api_type: session
kind: member
name: sid
label: "L'identifiant de session"
---
Chaque session possède un identifiant unique.

{: .tip }
> On le retrouve dans l'URL des REDY sous la forme `/WSID<sid>/easy/...`. C'est d'ailleurs grâce à cet identifiant qu'il est possible de construire des URL directes vers des éléments du REDY.

Exemple d'utilisation en liaison : Vous désirez afficher dans une iframe les tableaux de bord du REDY. Vous pouvez construire l'URL de l'iframe en utilisant un joker et une liaison vers le champ `sid` de la session.

{% raw %}
```
/WSID{{sid}}/easy/dashboard
```
{% endraw %}

Ensuite, sur l'additionnelle pour compléter l'URL, vous ajoutez une liaison vers le champ `sid` de la session.

Exemple  de l'acteur :
{% raw %}
```
SYNAPPS-STUDIO-ACTOR|{"type":"display/iframe","key":"iframe1","properties":{"url":"/WSID{{sid}}/easy/dashboard","height":"680px","width":"1280px"},"additionalDefs":{"sid":{"type":"text"}},"bindings":{"additionals.sid":{"sourceType":"session","path":"sid"}}}
```
{% endraw %}
