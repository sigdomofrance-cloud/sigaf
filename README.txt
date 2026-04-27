POC SIG + BIM synchronisé
=========================

Contenu :
- index.html : viewer SIG + BIM synchronisé.
- sample_domofrance_bim.ifc : petite maquette IFC d'exemple interrogeable par entités.
- components.json : métadonnées et volumes 3D liés aux GUID IFC.

Lancement recommandé :
1. Dézipper le dossier.
2. Ouvrir un terminal dans le dossier.
3. Lancer : python -m http.server 8000
4. Ouvrir : http://localhost:8000/index.html

Fonctions :
- Carte SIG avec parcelle + emprise bâtiment.
- Viewer BIM 3D avec composants sélectionnables.
- Filtres par niveau, catégorie, recherche texte.
- Synchronisation SIG/BIM : sélection BIM -> zoom emprise bâtiment.
- Lecture du fichier IFC texte et comptage des entités IFC.

Note technique :
Ce POC est volontairement léger et autonome. La géométrie 3D est rendue depuis components.json pour garantir un test immédiat dans le navigateur. Le fichier IFC fourni contient les entités BIM correspondantes avec leurs GlobalIds. Pour une version industrielle, il faudra remplacer le rendu volumétrique par un vrai parseur IFC WebAssembly type web-ifc / IFC.js / ThatOpen Components, ou convertir les IFC en glTF/3D Tiles côté serveur.
