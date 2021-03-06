TaxHub
=========

Application web de gestion centralisée des taxons basée sur le référentiel TAXREF (http://inpn.mnhn.fr/programme/referentiel-taxonomique-taxref) du MNHN.

Elle permet de gérer la liste des taxons présents dans chaque structure, d'y greffer des informations spécifiques, de définir des listes de taxons et des filtres en fonction des besoins.

Elle est utilisée pour la structuration des taxons dans GeoNature (https://github.com/PnEcrins/GeoNature) à partir de sa version 1.4.0.

Elle permet aussi de gérer les descriptions et les médias des taxons pour leur affichage dans GeoNature-atlas.

.. image :: docs/images/taxons-liste.jpg

.. image :: docs/images/taxon-details.jpg

Documentation
=============

La documentation d'installation de TaxHub est disponible sur http://taxhub.readthedocs.io.

TaxHub peut aussi être installé à partir du script d'installation globale de GeoNature : http://geonature.readthedocs.io/fr/latest/install_all/README.html.

Principes
=========

Voici le modèle conceptuel de la base de données de TaxHub (à mettre à jour) :

.. image :: docs/images/MCD_taxonomie.png

Une partie correspond au TAXREF complet tel que fourni par le MNHN. Son contenu ne doit pas être modifié.

Une partie correspond à la partie spécifique à chaque structure. Il faut commencer par renseigner la table ``bib_noms`` en selectionnant les taxons qui nous intéressent dans le TAXREF.

Il faut ensuite y greffer des informations spécifiques grace à ``bib_attributs`` (patrimonialité, marqueurs, autres selon les besoins) et définir des sous-listes de taxons (amphibiens, ....) dans ``bib_listes`` en fonction des besoins.

Technologies
------------

- Langages : Python, HTML, JS, CSS
- BDD : PostgreSQL, PostGIS
- Serveur : Debian ou Ubuntu
- Framework python : flask
- Framework JS : AngularJS
- Framework CSS : Bootstrap

Gestion des droits
------------------

Elle est centralisée dans l'application `UsersHub <https://github.com/PnEcrins/UsersHub>`_. Il faut donc disposer d'une application ``TaxHub`` dans UsersHub et y intégrer des groupes et/ou utilisateurs.

Niveaux de droits :

* 2 = Gestion des médias uniquement
* 3 = Idem 2 + Gestion des attributs de `GeoNature-atlas <https://github.com/PnEcrins/GeoNature-atlas>`_
* 4 = Idem 3 + Possibilité d'ajouter des taxons dans ``bib_noms``, de les mettre dans des listes et de renseigner tous leurs attributs (notamment ceux utilisés par `GeoNature <https://github.com/PnEcrins/GeoNature>`_)
* 6 = Administrateurs

Auteurs
-------

- Amandine Sahl
- Gil Deluermoz
- Damien Frazzoni
- Claire Lagaye
- Christophe Chillet
- Samuel Priou
- Thomas Lebard
- Camille Monchicourt

License
-------

* OpenSource - GPL V3
* Copyright (c) 2014-2018 - Parc National des Écrins - Parc national des Cévennes


.. image:: http://geonature.fr/img/logo-pne.jpg
    :target: http://www.ecrins-parcnational.fr

.. image:: http://geonature.fr/img/logo-pnc.jpg
    :target: http://www.cevennes-parcnational.fr
