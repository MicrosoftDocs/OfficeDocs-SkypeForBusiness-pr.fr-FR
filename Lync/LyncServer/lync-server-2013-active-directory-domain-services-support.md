---
title: 'Lync Server 2013 : prise en charge des services de domaine Active Directory'
description: 'Lync Server 2013 : prise en charge des services de domaine Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558680"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Prise en charge des services de domaine Active Directory dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Lync Server 2013 utilise le magasin central de gestion pour stocker les données de configuration des serveurs et des services, au lieu de s’appuyer sur les services de domaine Active Directory pour ces informations, comme dans le passé. Lync Server 2013 stocke toujours les éléments suivants dans AD DS :

  - **Extensions de schéma**
    
      - Extensions de l’objet utilisateur
    
      - Extensions pour les classes Lync Server 2010 et Office Communications Server 2007 R2 afin de maintenir la compatibilité descendante avec les versions prises en charge précédentes

  - **Données** (stockées dans le schéma étendu Lync Server 2013 et dans les classes existantes)
    
      - URI SIP de l’utilisateur et autres paramètres utilisateur
    
      - Objets contact pour les applications (par exemple, l’application Response Group et l’application de surveillance de conférence)
    
      - Données publiées pour la compatibilité descendante
    
      - Un point de contrôle de service (SCP) pour le magasin central de gestion
    
      - Compte d’authentification Kerberos (un objet ordinateur facultatif)

Cette section décrit la configuration requise pour la prise en charge des services AD DS pour Lync Server 2013. Pour plus d’informations sur la prise en charge de la topologie, voir [topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation de prise en charge.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Systèmes d’exploitation de contrôleur de domaine pris en charge

Lync Server 2013 prend en charge les contrôleurs de domaine exécutant les systèmes d’exploitation suivants :

  - Système d’exploitation Windows Server 2012 R2

  - Système d’exploitation Windows Server 2012

  - système d’exploitation Windows Server 2008 R2

  - système d’exploitation Windows Server 2008

  - Windows Server 2008 Enterprise 32 bits

  - Les versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003 R2

  - Les versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Niveau fonctionnel de la forêt et du domaine

Vous devez déclencher tous les domaines dans lesquels vous déployez Lync Server 2013 sur un niveau fonctionnel de domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.

Toutes les forêts dans lesquelles vous déployez Lync Server 2013 doivent être augmentées jusqu’à un niveau fonctionnel de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au moins Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Prise en charge des contrôleurs de domaine Read-Only

Lync Server 2013 prend en charge les déploiements des services de domaine Active Directory qui incluent des contrôleurs de domaine en lecture seule ou des serveurs de catalogue global en lecture seule, à condition qu’il y ait des contrôleurs de domaine accessibles en écriture.

</div>

<div>

## <a name="domain-names"></a>Noms de domaine

Lync Server ne prend pas en charge les domaines à étiquette unique. Par exemple, une forêt comportant le domaine racine **contoso.local** est prise en charge alors que le domaine racine **local** ne l’est pas. Pour plus d’informations, consultez l’article 300684 de la base de connaissances Microsoft, « informations sur la configuration de Windows pour les domaines avec des noms DNS en une seule partie », à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) .

<div>


> [!NOTE]  
> Lync Server ne prend pas en charge le changement de nom des domaines. Si vous devez renommer un domaine où Lync Server est déployé, vous devez d’abord désinstaller Lync Server, renommer le domaine, puis réinstaller Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Environnements AD DS verrouillés

Dans un environnement AD DS verrouillé, les utilisateurs et les objets ordinateur sont souvent placés dans des unités d’organisation (UO) spécifiques dont l’héritage des autorisations est désactivé pour aider à sécuriser la délégation d’administration et pour permettre l’utilisation des objets de stratégie de groupe (GPO) pour appliquer des stratégies de sécurité. Lync Server 2013 peut être déployé dans un environnement Active Directory verrouillé. Pour plus d’informations sur les éléments requis pour déployer Lync Server dans un environnement verrouillé, voir [Preparing a Locked Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

