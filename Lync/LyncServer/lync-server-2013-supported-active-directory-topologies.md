---
title: 'Lync Server 2013 : topologies Active Directory prises en charge'
description: 'Lync Server 2013 : topologies Active Directory prises en charge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ce820a36cb033933b423e01deb5a3049ed3ea2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575310"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Topologies Active Directory prises en charge dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-10-02_

Lync Server 2013 prend en charge les mêmes topologies de services de domaine Active Directory que Microsoft Lync Server 2010 et Microsoft Office Communications Server 2007 R2. Les topologies suivantes sont prises en charge :

  - Forêt unique avec domaine unique

  - Forêt unique avec un arbre unique et plusieurs domaines

  - Forêt unique avec plusieurs arbres et des espaces de noms disjoints

  - Plusieurs forêts dans une topologie de forêt centrale

  - Plusieurs forêts dans une topologie de forêt de ressources

  - Plusieurs forêts dans une topologie de forêt de ressources Lync avec Exchange Online

L’illustration suivante identifie les icônes utilisées dans les illustrations de cette section.

**Éléments des illustrations de topologie**

![Éléments des illustrations de topologie](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Éléments des illustrations de topologie")

<div>

## <a name="single-forest-single-domain"></a>Forêt unique, domaine unique

La topologie Active Directory la plus simple prise en charge par Lync Server, une forêt de domaine unique, est une topologie commune.

La figure suivante illustre un déploiement de Lync Server dans une topologie Active Directory à domaine unique.

**Topologie à domaine unique**

![Topologie à domaine unique](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologie à domaine unique")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>Une seule forêt, plusieurs domaines

Une autre topologie Active Directory prise en charge par Lync Server est une forêt unique qui se compose d’un domaine racine et d’un ou plusieurs domaines enfants. Dans ce type de topologie Active Directory, le domaine dans lequel vous créez les utilisateurs peut être différent du domaine dans lequel vous déployez Lync Server. Toutefois, si vous déployez un pool frontal, vous devez déployer tous les serveurs frontaux dans le pool au sein d’un seul domaine. La prise en charge de Lync Server pour les groupes d’administrateurs universels Windows permet l’administration entre domaines.

L’illustration suivante montre un déploiement dans une seule forêt avec plusieurs domaines. Dans cette illustration, une icône utilisateur indique le domaine dans lequel le compte d’utilisateur est hébergé et la flèche pointe vers le domaine où se trouve le pool Lync Server. Les comptes d’utilisateur sont les suivants :

  - Comptes d’utilisateur dans le même domaine que le pool Lync Server

  - Comptes d’utilisateur dans un domaine différent du pool Lync Server

  - Comptes d’utilisateur dans un domaine enfant du domaine avec le pool Lync Server

**Forêt unique avec plusieurs domaines**

![Forêt unique avec plusieurs domaines](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Forêt unique avec plusieurs domaines")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>Une seule forêt, plusieurs arbres

Une topologie de forêt à plusieurs arbres comporte au moins deux domaines qui définissent des arborescences indépendantes et des espaces de noms Active Directory distincts.

L’illustration suivante montre une forêt unique avec plusieurs arbres. Dans cette illustration, une icône utilisateur indique le domaine dans lequel le compte d’utilisateur est hébergé, une ligne pleine pointe vers un pool Lync Server qui se trouve dans le même domaine ou un domaine différent, et une ligne en pointillés pointe vers le pool Lync Server qui réside dans une autre arborescence. Les comptes d’utilisateur sont les suivants :

  - Comptes d’utilisateur dans le même domaine que le pool Lync Server

  - Les comptes d’utilisateur dans un domaine différent, à partir de la même arborescence que le pool Lync Server.

  - Comptes d’utilisateur dans une arborescence différente du pool Lync Server

**Forêt unique avec plusieurs arbres**

![Forêt unique avec plusieurs arbres](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Forêt unique avec plusieurs arbres")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>Plusieurs forêts, forêt centrale

Lync Server prend en charge plusieurs forêts configurées dans une topologie de forêt centrale. Les topologies de forêt centrale utilisent des objets contact dans la forêt centrale pour représenter des utilisateurs dans les autres forêts. La forêt centrale héberge également des comptes d’utilisateur pour tout utilisateur de cette forêt. Une application de synchronisation d’annuaires, tel que Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur dans l’organisation : lorsqu’un nouveau compte d’utilisateur est créé dans l’une des forêts ou lorsqu’un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise le contact correspondant dans la forêt centrale.

Une forêt centrale présente les avantages suivants :

  - Les serveurs exécutant Lync Server sont centralisés au sein d’une forêt unique.

  - Les utilisateurs peuvent rechercher et communiquer avec d’autres utilisateurs dans n’importe quelle forêt.

  - Les utilisateurs peuvent voir la présence d’autres utilisateurs dans n’importe quelle forêt.

  - L’application de synchronisation d’annuaires automatise l’ajout et la suppression d’objets contact dans la forêt centrale à mesure que des comptes d’utilisateur sont créés ou supprimés.

L’illustration suivante illustre une topologie de forêt centrale. Dans cette figure, il existe des relations d’approbation bidirectionnelles entre le domaine qui héberge Lync Server, qui se trouve dans la forêt centrale et chaque domaine User-only, qui se trouve dans une forêt distincte. Le schéma dans les différentes forêts d’utilisateurs ne doit pas être étendu.

**Topologie de forêt centrale**

![Topologie de forêt centrale](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologie de forêt centrale")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>Plusieurs forêts, forêt de ressources

Dans une topologie de forêt de ressources, une forêt est dédiée à l’exécution d’applications serveur, telles que Microsoft Exchange Server et Lync Server. La forêt de ressources héberge les applications serveur et une représentation synchronisée de l’objet utilisateur actif, mais elle ne contient aucun compte d’utilisateur pour lequel l’ouverture de session est activée. La forêt de ressources joue le rôle d’un environnement de services partagés pour les autres forêts dans lesquelles résident les objets utilisateur. Les forêts d’utilisateurs ont une relation de confiance au niveau de la forêt avec la forêt de ressources. Lorsque vous déployez Lync Server dans ce type de topologie, vous créez un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs. Si Microsoft Exchange est déjà déployé dans la forêt de ressources, il se peut que les comptes d’utilisateurs désactivés existent déjà. Une application de synchronisation d’annuaires, tel que MIIS, Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur. Lorsqu’un nouveau compte d’utilisateurs est créé dans l’une des forêts d’utilisateurs ou lorsqu’un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise la représentation d’utilisateur correspondante dans la forêt de ressources.

Cette topologie peut être utilisée pour fournir une infrastructure partagée pour les services dans les organisations qui gèrent plusieurs forêts ou pour administrer séparément les objets Active Directory. Les entreprises qui doivent isoler l’administration Active Directory pour des raisons de sécurité choisissent souvent cette topologie.

Cette topologie évite de devoir étendre le schéma Active Directory à une forêt unique (c’est-à-dire la forêt de ressources).

Le diagramme suivant illustre une topologie de forêt de ressources.

**Topologie de forêt de ressources**

![Topologie de forêt de ressources Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologie de forêt de ressources Active Directory")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts dans une topologie de forêt de ressources Lync avec Exchange Online

Dans cette topologie, une ou plusieurs forêts sont situées sur site et sont dédiées à l’hébergement des comptes d’utilisateur Active Directory. La forêt de ressources se trouve hors site et est gérée par un fournisseur d’hébergement tiers. La forêt de ressources contient uniquement le déploiement Lync Server et une réplication synchronisée des comptes d’utilisateur à partir des forêts de comptes d’utilisateurs locaux. Il ne contient pas de comptes d’utilisateur à extension connexion. Exchange est déployé dans les forêts de compte d’utilisateur locales intégrées avec Exchange Online (hybride), ou les services de messagerie pour les comptes d’utilisateur locaux sont fournis exclusivement par Exchange Online.

La forêt de ressources agit comme un environnement de services partagés pour les forêts Active Directory locales où les objets utilisateur résident. Les forêts de compte d’utilisateur ont une relation d’approbation de niveau forêt unidirectionnelle avec la forêt de ressources. Lorsque vous déployez Lync Server dans ce type de topologie, vous créez un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs. Une application de synchronisation d’annuaires, tel que MIIS, Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur. Lorsqu’un nouveau compte d’utilisateurs est créé dans l’une des forêts d’utilisateurs ou lorsqu’un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise la représentation d’utilisateur correspondante dans la forêt de ressources. Pour plus d’informations sur la configuration d’un déploiement à forêts multiples, reportez-vous à la rubrique [Deploying Lync in a multi-Forest architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).

</div>

</div>

<span> </span>

</div>

</div>

</div>

