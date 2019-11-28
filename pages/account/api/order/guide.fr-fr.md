---
title: 'Commande des services'
slug: ovh-api-order
excerpt: 'Obtenir les prix des services et effectuer des commandes'
section: 'OVH APIv6'
---

**Dernière mise à jour le 27/11/2019**

## Objectif

Nous allons décrire comment obtenir les prix des services puis leurs commandes chez OVH via les routes d'API /order & /me.

La route d'API **/order** regroupe les actions de commande communes à tous types de services chez OVH.

## Prérequis

* Être connecté aux [API OVH](https://api.ovh.com/console){.external}.
* Avoir [créé ses identifiants pour l'API OVH](https://docs.ovh.com/gb/en/customer/first-steps-with-ovh-api/){.external}.

## En pratique

### Ressources

* catalog : Identifiant unique du service chez OVH 
* cart : Panier qui regroupe
* cartServiceOption : 

### Déroulement des opérations

#### Récupérer la liste des prix pour un services

Il existe une route d'API par cataloge produits.

- Elles ne requièrent pas d'être authentifier pour y accéder.
- Les prix affichés dans les catalogues sont les prix publiques en vigueur dans la filiale.

Il est possible de connaître la filiale auquel un compte est associé, via :

> [!api]
>
> @api {GET} /me
>

Pour extraire la valeur, il est possible d'appliquer le filtre JSON suivant :

```
.ovhSubsidiary
```

Pour les exemples suivant nous prendrons la valeur suivante :

```
ovhSubsidiary=FR
```

##### Public Cloud

> [!api]
>
> @api {GET} /order/catalog/formatted/cloud?ovhSubsidiary=FR
>

##### Private Cloud

> [!api]
>
> @api {GET} /order/catalog/formatted/privateCloud?ovhSubsidiary=FR
>

##### Serveur dédier

> [!api]
>
> @api {GET} /order/catalog/formatted/dedicated?ovhSubsidiary=FR
>

### Faire une commande

Les étapes suivantes ne requièrent pas d'être authentifier dans un premier temps.
Cela sera néanmoins nécessaire préalablement à tout règlement pour obtenir les moyens de paiement ainsi que le compte pour lequel la commande est effectuée.

#### Création du panier

Commencer par créer un panier dans la filiale souhaiter.

Au besoin vous pouvez définir une date d'expiration et une description.

> [!api]
>
> @api {POST} /order/cart
>

Récupérez et sauvegardez le **cartId** obtenu.

#### Ajouter les services

L'ajout des services se fait via les routes d'API propre à chacun des services.

Pour chacun des services qui doit être ajouté, préciser les paramètres suivants :

* duration
* planCode
* pricingMode
* quantity

Ils devront prendres les valeurs possible indiquées dans les catalogues respectifs.

##### Public Cloud

Ajouter un projet Public Cloud

##### Private Cloud

Ajouter un Private Cloud

##### Serveur dédier

Ajouter un serveur dédier

#### Assigner le panier

Après avoir constituer le panier, à partir de **cartId** utiliser la route suivante pour assigner celui au compte qui effectue l'action.

> [!api]
>
> @api {POST} /order/cart/{cartId}/assign
>

#### Valider le panier

La validation du panier permet transformer celui-ci en bon de commande (BC) qui sera à régler.

Il est possible de régler le bon de commande directement à cet étape en utilisant le boolean **autoPayWithPreferredPaymentMethod**, sous réserve que le compte ait définit un moyen de paiement par défaut et que celui soit valide.

> [!api]
>
> @api {POST} /order/cart/{cartId}/checkout
>

Récupérez et sauvegardez le **orderId** obtenu.

#### Paiement du bon de commande

Le paiement du bon de commande se fait au niveau du compte et donc au niveau de l'API sous **/me** .

##### Obtenir les numero des bon de commandes

Récupérer le cas échéant la liste des **orderId** des bon de commande sur le compte via l'appel suivant.

> [!api]
>
> @api {GET} /me/order
>

## Aller plus loin

Échangez avec notre communauté d’utilisateurs sur <https://community.ovh.com/>.
