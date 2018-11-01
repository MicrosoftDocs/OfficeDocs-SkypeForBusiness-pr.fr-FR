---
title: 'Lync Server 2013 : Topologies Active Directory prises en charge'
TOCTitle: Topologies Active Directory prises en charge
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398173(v=OCS.15)
ms:contentKeyID: 49296232
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologies Active Directory prises en charge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 prend en charge les mêmes topologies des services de domaine Active Directory que Microsoft Lync Server 2010 et Microsoft Office Communications Server 2007 R2. Les topologies suivantes sont prises en charge :

  - Forêt unique avec domaine unique

  - Forêt unique avec un arbre unique et plusieurs domaines

  - Forêt unique avec plusieurs arbres et des espaces de noms disjoints

  - Plusieurs forêts dans une topologie de forêt centrale

  - Plusieurs forêts dans une topologie de forêt de ressources

  - Plusieurs forêts d’une topologie de forêts de ressources Lync avec Exchange Online

L’illustration suivante identifie les icônes utilisées dans les illustrations de cette section.

**Légende des illustrations de topologie**

![Légende des illustrations de topologie](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Légende des illustrations de topologie")

## Forêt unique, domaine unique

La topologie Active Directory la plus simple prise en charge par Lync Server, à savoir une forêt de domaine unique, est une topologie courante.

L’illustration suivante montre un déploiement de Lync Server dans une topologie Active Directory à domaine unique.

**Topologie à domaine unique**

![Topologie à domaine unique](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologie à domaine unique")

## Une seule forêt, plusieurs domaines

Une autre topologie Active Directory est prise en charge par Lync Server : une forêt unique comportant un domaine racine et un ou plusieurs domaines enfants. Dans ce type de topologie Active Directory, le domaine dans lequel vous créez des utilisateurs peut être différent de celui dans lequel vous déployez Lync Server. Cependant, si vous déployez un pool frontal, vous devez déployer tous les serveurs frontaux dans le pool au sein d’un seul domaine. La prise en charge par Lync Server des groupes d’administrateurs universels Windows permet l’administration interdomaine.

L’illustration suivante montre un déploiement dans une seule forêt avec plusieurs domaines. Dans cette illustration, une icône d’utilisateur indique le domaine dans lequel le compte d’utilisateur est hébergé et la flèche pointe vers le domaine où se trouve le pool Lync Server. Les comptes d’utilisateur sont les suivants :

  - Comptes d’utilisateur dans le même domaine que le pool Lync Server

  - Comptes d’utilisateur dans un domaine différent de celui du pool Lync Server

  - Comptes d’utilisateurs dans un domaine enfant du domaine avec le pool Lync Server

**Forêt unique avec plusieurs domaines**

![Forêt unique avec plusieurs domaines](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Forêt unique avec plusieurs domaines")

## Une seule forêt, plusieurs arbres

Une topologie de forêt à plusieurs arbres comporte au moins deux domaines qui définissent des arborescences indépendantes et des espaces de noms Active Directory distincts.

L’illustration suivante montre une forêt unique avec plusieurs arbres. Dans cette illustration, une icône d’utilisateur indique le domaine dans lequel le compte d’utilisateur est hébergé, une ligne pleine pointe vers un pool Lync Server qui se trouve dans le même domaine ou dans un domaine différent et une ligne en pointillé pointe vers le pool Lync Server qui se trouve dans une autre arborescence. Les comptes d’utilisateur sont les suivants :

  - Comptes d’utilisateur dans le même domaine que le pool Lync Server

  - Comptes d’utilisateur dans un domaine différent (mais dans le même arbre) du pool Lync Server

  - Comptes d’utilisateur dans une autre arborescence que celle du pool Lync Server

**Forêt unique avec plusieurs arbres**

![Forêt unique avec plusieurs arbres](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Forêt unique avec plusieurs arbres")

## Plusieurs forêts, forêt centrale

Lync Server prend en charge plusieurs forêts configurées dans une topologie de forêt centrale. Les topologies de forêt centrale utilisent des objets contact dans la forêt centrale pour représenter des utilisateurs dans les autres forêts. La forêt centrale héberge également des comptes d’utilisateur pour tout utilisateur de cette forêt. Une application de synchronisation d’annuaires, tel que Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur dans l’organisation : lorsqu’un nouveau compte d’utilisateur est créé dans l’une des forêts ou lorsqu’un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise le contact correspondant dans la forêt centrale.

Une forêt centrale présente les avantages suivants :

  - Les serveurs exécutant Lync Server sont centralisés dans une forêt unique.

  - Les utilisateurs peuvent rechercher et communiquer avec d’autres utilisateurs dans n’importe quelle forêt.

  - Les utilisateurs peuvent voir la présence d’autres utilisateurs dans n’importe quelle forêt.

  - L’application de synchronisation d’annuaires automatise l’ajout et la suppression d’objets contact dans la forêt centrale à mesure que des comptes d’utilisateur sont créés ou supprimés.

L’illustration suivante illustre une topologie de forêt centrale. Dans cette illustration, il existe des relations de confiance bidirectionnelles entre le domaine qui héberge Lync Server, qui se trouve dans la forêt centrale, et chaque domaine d’utilisateur uniquement, qui se trouve dans une forêt distincte. Le schéma dans les différentes forêts d’utilisateurs ne doit pas être étendu.

**Topologie de forêt centrale**

![Topologie de forêt centrale](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologie de forêt centrale")

## Plusieurs forêts, forêt de ressources

Dans une topologie de forêt de ressources, une forêt est dédiée à l’exécution d’applications serveur, telles que Microsoft Exchange Server et Lync Server. La forêt de ressources héberge les applications serveur et une représentation synchronisée de l’objet utilisateur actif, mais elle ne contient aucun compte d’utilisateur pour lequel l’ouverture de session est activée. La forêt de ressources joue le rôle d’un environnement de services partagés pour les autres forêts dans lesquelles se trouvent les objets utilisateur. Les forêts d’utilisateurs ont une relation de confiance au niveau de la forêt avec la forêt de ressources. Lorsque vous déployez Lync Server dans ce type de topologie, vous créez un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs. Si Microsoft Exchange est déjà déployé dans la forêt de ressources, il se peut que les comptes d’utilisateurs désactivés existent déjà. Une application de synchronisation d’annuaires, tel que MIIS, Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur. Lorsqu’un nouveau compte d’utilisateurs est créé dans l’une des forêts d’utilisateurs ou lorsqu’un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise la représentation d’utilisateur correspondante dans la forêt de ressources.

Cette topologie peut être utilisée pour fournir une infrastructure partagée pour les services dans les organisations qui gèrent plusieurs forêts ou pour administrer séparément les objets Active Directory. Les entreprises qui doivent isoler l’administration Active Directory pour des raisons de sécurité choisissent souvent cette topologie.

Cette topologie évite de devoir étendre le schéma Active Directory à une forêt unique (c’est-à-dire la forêt de ressources).

Le diagramme suivant illustre une topologie de forêt de ressources.

**Topologie de forêt de ressources**

![Topologie de forêt de ressources Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologie de forêt de ressources Active Directory")

## Plusieurs forêts d’une topologie de forêts de ressources Lync avec Exchange Online

Dans cette topologie, une ou plusieurs forêts sont locales et dédiées à l’hébergement des comptes d’utilisateur Active Directory. La forêt de ressources est hors site et tenue à jour par un fournisseur d’hébergement tiers. Elle contient uniquement le déploiement de Lync Server et une réplication synchronisée des comptes d’utilisateur provenant de la ou des forêts de comptes d’utilisateur locales. Elle ne contient pas de comptes d’utilisateur pour lesquels l’ouverture de session est activée. Exchange est déployé dans la ou les forêts de comptes d’utilisateur locales, intégrées à Exchange Online (déploiement hybride), ou bien les services de messagerie électronique pour les comptes d’utilisateur locaux sont fournis exclusivement par Exchange Online.

La forêt de ressources joue le rôle d’environnement de services partagés pour la ou les forêts Active Directory locales dans lesquelles résident les objets utilisateur. La ou les forêts de comptes d’utilisateur ont une relation d’approbation unidirectionnelle avec la forêt de ressources. Quand vous déployez Lync Server dans ce type de topologie, vous créez un seul objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur inclus dans les forêts d’utilisateurs. Une application de synchronisation d’annuaires, comme MIIS, Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur. Quand un nouveau compte d’utilisateur est créé dans l’une des forêts d’utilisateurs ou quand un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise la représentation de l’utilisateur correspondant dans la forêt de ressources. Pour plus d’informations sur la configuration d’un déploiement multiforêts, reportez-vous à la section [Déploiement de Lync dans une architecture multiforêts (Lync hébergé par un partenaire avec un déploiement Exchange hybride)](http://go.microsoft.com/fwlink/p/?linkid=513216).

