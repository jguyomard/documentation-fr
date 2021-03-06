Notes de la version Chiba 1
###########################

Nouveautés
==========

* Le comportement publiable (``Behaviour_Publishable``) supporte maintenant la publication avec dates de début et de fin.

Application Formulaire
----------------------

* Ajout d'une barre de progression sur les formulaire multi-page

Blog / News
-----------

* Affichage des posts par auteur

Développeur
===========

* Amélioration du front-office

    * Activation du ``Profiling`` par défaut dans l'environement ``DEVELOPMENT``.
    * La configuration ``novius-os.cache`` est à ``true`` par défaut.
    * Les configurations ``novius-os.cache_duration_page`` et ``novius-os.cache_duration_function`` sont à 600 secondes par défaut, sauf en ``PRODUCTION`` à 3600 secondes.
    * Nouveaux événements ``front.pageFound`` et ``front.response``.
    * Nouvelles méthodes sur le ``Controller_Front`` : getContext, disableCaching, setCacheDuration, setStatus, setHeader, getCustomData, setCustomData, sendContent, addCacheSuffixHandler.
    * Le status et les headers sont sauvés dans le cache.
    * Mécanisme de ``Suffix Handler`` permettant d'ajouter des suffixes au cache en fonction de paramètres GET ou de ce que vous voulez (par des ``callables``).
    * Mécanisme pour exécuter du code tout en utilisant le cache.

* Properties des Models

    * Les properties des Models sont désormais définies dans les applications natives
    * Implémentation d'un mécanisme de cache des properties, via le cache FuelPHP. Ce cache s'auto regénère si une property,
      existante en base mais inconnue du Model, est appellée via le ``get()`` ou le ``set()``.

* Les migrations sont maintenant dispatchées par application
* Nouvelle clé ``requires`` dans le ``metadata`` des applications permettant de définir qu'une application en nécessite une autre.
* Possibilité d'utiliser ``href="##..."`` dans les enhancers ou les templates; les occurences seront remplacées par ``href="#..."`` sans être préfixées par le ``base_url``.
* CRUD: Quand la clé ``disabled`` retourne une chaine, elle est affichée en tooltip. Les clés ``disabled`` et ``visible`` peuvent maintenant être contenir un scalaire simple, une fonction de callback ou un tableau de callbacks.
* Les miniatures d'images sont désormais sécurisées : il n'est plus possible d'en générer un grand nombre pour surcharger le serveur


* Permissions

    * Possiblité de  définir des permissions par application via un fichier de configuration
    * Nouvelle API pour vérifier les permissions sur un utilisateur ou un rôle
    * Nouvelle configuration ``novius-os.users.enable_roles`` pour activer les rôles multiples sur les utilisateurs


Deprecated
----------

* Ne plus utiliser la classe ``Nos\Renderer_Media`` mais ``Nos\Media\Renderer_Media``.
* Dans la définition des ``launchers`, ne plus utiliser la clé ``url`` mais la clé ``action``.
* Dans la configuration des renderer, ne plus utiliser la clé ``widget`` mais la clé ``renderer`` et modifier le nom de la classe appellée.
* Dans la configuration des renderer, ne plus utiliser la clé ``widget_options`` mais la clé ``renderer_options``.
* Ne plus utiliser la classe ``\Config::extendable_load()`` mais ``\Config::loadConfiguration()``.
* Dans la configuration du behaviour ``Orm_Behaviour_Publishable``, ne plus utiliser la clé ``publication_bool_property`` mais la clé ``publication_state_property``.
