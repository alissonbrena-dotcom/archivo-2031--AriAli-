# Informe de la investigación — ARCHIVO 2031 · equipo P

| Hallazgo | Dónde estaba | Técnica de Git | Comando exacto | Referencia |
|---|---|---|---|---|
| FRAG-01 | `bitacora/frag-01.txt`, borrado por el commit `a58ea88` "limpieza de archivos temporales" en la rama principal de la cinta | Localizar el borrado y leer el archivo en el commit anterior | `git log --diff-filter=D --name-only refs/cinta/heads/main` → `git show f51ad24:bitacora/frag-01.txt > bitacora/frag-01.txt` | `f51ad24` |
| FRAG-02 | En el mensaje del tag anotado `respaldo/pre-incidente`, no dentro de ningún archivo | Leer el objeto tag, que es una referencia que no es una rama | `git cat-file -p refs/tags/respaldo/pre-incidente` | `7a812f6` |
| Glifo `assets/sello.svg` | Árbol del commit apuntado por ese mismo tag anotado | Listar el árbol de la referencia y extraer el blob | `git ls-tree -r --name-only refs/tags/respaldo/pre-incidente` → `git show refs/tags/respaldo/pre-incidente:assets/sello.svg > assets/sello.svg` | `1aadf6f` |
