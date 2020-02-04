---
title: 'Lync Server 2013 : Topologies Active Directory prises en charge'
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
ms.openlocfilehash: 3e4aca368f6ea7d5b31a1cfe74273dfbd42a6594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Topologies Active Directory prises en charge dans Lync Server 2013

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

La figure suivante identifie les icônes utilisées dans les illustrations de cette section.

**Clé pour les illustrations topologiques**

![Clé pour les illustrations topologiques](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Clé pour les illustrations topologiques")

<div>

## <a name="single-forest-single-domain"></a>Forêt unique, domaine unique

La topologie Active Directory la plus simple prise en charge par Lync Server (forêt de domaine unique) est une topologie courante.

La figure suivante illustre un déploiement de serveur Lync dans une topologie Active Directory de domaine unique.

**Topologie à domaine unique**

![Topologie à domaine unique](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologie à domaine unique")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>Forêt unique, plusieurs domaines

Une autre topologie Active Directory prise en charge par Lync Server est une forêt unique composée d’un domaine racine et d’un ou plusieurs domaines enfants. Dans ce type de topologie Active Directory, le domaine dans lequel vous créez des utilisateurs peut être différent de celui dans lequel vous déployez Lync Server. Toutefois, si vous déployez un pool frontal, vous devez déployer tous les serveurs frontaux dans le pool au sein d’un domaine unique. La prise en charge de Lync Server pour les groupes d’administrateurs Windows universelle autorise une administration entre domaines.

La figure suivante illustre un déploiement au sein d’une seule forêt avec plusieurs domaines. Dans cette figure, une icône utilisateur affiche le domaine dans lequel le compte d’utilisateur est hébergé et la flèche pointe vers le domaine dans lequel réside le pool de serveurs Lync. Les comptes d’utilisateurs incluent les éléments suivants :

  - Comptes d’utilisateurs au sein du même domaine que le pool de serveurs Lync

  - Comptes d’utilisateurs d’un domaine différent du pool de serveurs Lync

  - Comptes d’utilisateurs dans un domaine enfant du domaine avec le pool de serveurs Lync

**Forêt unique avec plusieurs domaines**

![Forêt unique avec plusieurs domaines](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Forêt unique avec plusieurs domaines")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>Forêt unique, plusieurs arbres

Une topologie à plusieurs arborescences de forêts se compose de deux domaines ou plus qui définissent des structures d’arborescence indépendantes et des espaces de noms Active Directory distincts.

La figure suivante illustre une seule forêt avec plusieurs arborescences. Dans cette figure, une icône d’utilisateur affiche le domaine dans lequel le compte d’utilisateur est hébergé, une ligne pleine pointe vers un pool de serveurs Lync résidant au sein d’un même domaine ou d’un autre domaine et un trait en pointillés vers Lync Server pool se trouvant dans une autre arborescence. Les comptes d’utilisateurs incluent les éléments suivants :

  - Comptes d’utilisateurs au sein du même domaine que le pool de serveurs Lync

  - Comptes d’utilisateurs d’un domaine différent de (mais de l’arborescence)

  - Comptes utilisateur dans une autre arborescence que le pool de serveurs Lync

**Forêt unique avec plusieurs arborescences**

![Forêt unique avec plusieurs arborescences](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Forêt unique avec plusieurs arborescences")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>Forêts multiples, forêt centrale

Lync Server prend en charge plusieurs forêts configurées dans une topologie de forêt centrale. Les topologies de forêt centralisées utilisent les objets de contact dans la forêt centrale pour représenter les utilisateurs dans les autres forêts. La forêt centrale héberge également les comptes d’utilisateurs pour tous les utilisateurs de cette forêt. Un produit de synchronisation d’annuaires, tel que Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateurs dans Organisation : lorsqu’un nouveau compte d’utilisateur est créé dans l’une des forêts ou qu’un compte d’utilisateur est supprimé d’une forêt, le produit de synchronisation d’annuaires synchronise le contact correspondant dans la forêt centrale.

Une forêt centrale offre les avantages suivants :

  - Les serveurs exécutant Lync Server sont centralisés au sein d’une même forêt.

  - Les utilisateurs peuvent rechercher et communiquer avec d’autres utilisateurs dans n’importe quelle forêt.

  - Les utilisateurs peuvent afficher le statut de présence d’autres utilisateurs dans n’importe quelle forêt.

  - Le produit de synchronisation d’annuaires automatise l’ajout et la suppression d’objets de contact dans la forêt centrale lors de la création ou de la suppression de comptes d’utilisateur.

La figure suivante illustre une topologie de forêt centrale. Dans cette figure, il existe des relations d’approbation à double sens entre le domaine qui héberge Lync Server, qui se trouve dans la forêt centrale et chaque domaine utilisateur uniquement, qui se trouve dans une autre forêt. Il n’est pas nécessaire de prolonger le schéma dans les forêts utilisateurs distinctes.

**Topologie de forêt centrale**

![Topologie de forêt centrale](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologie de forêt centrale")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>Forêts multiples, forêt de ressources

Dans une topologie de forêt de ressources, une forêt est consacrée aux applications serveur en cours d’exécution, comme Microsoft Exchange Server et Lync Server. La forêt de ressources héberge les applications serveur et une représentation synchronisée de l’objet utilisateur actif, mais elle ne contient pas de comptes d’utilisateur à extension messagerie. La forêt de ressources agit en tant qu’environnement de services partagés pour les autres forêts où résident les objets utilisateurs. Les forêts utilisateur disposent d’une relation d’approbation de niveau forêt avec la forêt de ressources. Lorsque vous déployez Lync Server dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts utilisateurs. Si Microsoft Exchange est déjà déployé dans la forêt de ressources, il est possible que les comptes d’utilisateurs désactivés existent déjà. Un produit de synchronisation d’annuaires, tel que MIIS, Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateurs. Lorsqu’un nouveau compte d’utilisateur est créé dans l’une des forêts utilisateur ou qu’un compte d’utilisateur est supprimé d’une forêt, le produit de synchronisation d’annuaires synchronise la représentation utilisateur correspondante dans la forêt de ressources.

Cette topologie peut être utilisée pour fournir une infrastructure partagée pour les services dans les organisations qui gèrent plusieurs forêts ou pour dissocier l’administration des objets Active Directory d’une autre administration. Les sociétés qui ont besoin d’isoler l’administration Active Directory pour des raisons de sécurité choisissent souvent cette topologie.

Cette topologie offre l’avantage de limiter l’extension du schéma Active Directory à une seule forêt (c’est-à-dire la forêt de ressources).

Le diagramme suivant illustre une topologie de forêt de ressources.

**Topologie de forêt de ressources**

![Topologie de la forêt de ressources Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologie de la forêt de ressources Active Directory")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Plusieurs forêts dans une topologie de forêt de ressources Lync avec Exchange Online

Dans cette topologie, une ou plusieurs forêts résident en local et sont dédiées à l’hébergement des comptes d’utilisateurs Active Directory. La forêt de ressources est située en local et est gérée par un fournisseur d’hébergement tiers. La forêt de ressources contient uniquement le déploiement de Lync Server et une réplication synchronisée des comptes d’utilisateurs des forêts de comptes d’utilisateurs locales. Il ne contient pas de comptes d’utilisateur à extension messagerie. Exchange est déployé soit dans les forêts de comptes d’utilisateurs locales intégrées que dans Exchange Online, ou les services de messagerie pour les comptes d’utilisateurs locaux sont fournis uniquement par Exchange Online.

La forêt de ressources agit en tant qu’environnement de services partagés pour la ou les forêts Active Directory locales où résident les objets utilisateurs. La ou les forêts de compte d’utilisateur disposent d’une relation d’approbation de forêt à une façon unique avec la forêt de ressources. Lorsque vous déployez Lync Server dans ce type de topologie, vous devez créer un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts utilisateurs. Un produit de synchronisation d’annuaires, tel que MIIS, Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateurs. Lorsqu’un nouveau compte d’utilisateur est créé dans l’une des forêts utilisateur ou qu’un compte d’utilisateur est supprimé d’une forêt, le produit de synchronisation d’annuaires synchronise la représentation utilisateur correspondante dans la forêt de ressources. Pour plus d’informations sur la configuration d’un déploiement de forêts multiples, voir [déploiement de Lync dans une architecture à plusieurs forêts (partenaire hébergé sur Lync avec Exchange hybride)](http://go.microsoft.com/fwlink/p/?linkid=513216).

</div>

</div>

<span> </span>

</div>

</div>

</div>

