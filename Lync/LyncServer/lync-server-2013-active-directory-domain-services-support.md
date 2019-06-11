---
title: 'Lync Server 2013 : Prise en charge des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b264abefb1234892df355fee123dd6ce68b4dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Prise en charge des services de domaine Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

Lync Server 2013 utilise le magasin central de gestion pour stocker les données de configuration pour les serveurs et les services, au lieu de s’appuyer sur les services de domaine Active Directory (AD FS) pour ces informations, comme précédemment. Lync Server 2013 enregistre toujours les éléments suivants dans AD DS:

  - **Extensions de schéma**
    
      - Extensions de l’objet utilisateur
    
      - Extensions pour les classes Lync Server 2010 et Office Communications Server 2007 R2 pour garantir la compatibilité descendante avec les versions prises en charge précédentes

  - **Data (données** ) (stocké dans le schéma étendu de Lync Server 2013 et dans les classes existantes)
    
      - URI SIP de l’utilisateur et autres paramètres utilisateur
    
      - Objets de contact pour applications (par exemple, l’application Response Group et l’application attendant);
    
      - Données publiées pour la compatibilité descendante
    
      - Un point de contrôle de service (SCP) pour le magasin de gestion central
    
      - Compte d’authentification Kerberos (objet facultatif de l’ordinateur)

Cette section décrit la configuration requise pour la prise en charge des services d’annuaire Active Directory pour Lync Server 2013. Pour plus d’informations sur la prise en charge de la topologie, voir [topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation relative à la prise en charge.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Systèmes d’exploitation de contrôleur de domaine pris en charge

Lync Server 2013 prend en charge les contrôleurs de domaine exécutant les systèmes d’exploitation suivants:

  - Système d’exploitation Windows Server 2012 R2

  - Système d’exploitation Windows Server 2012

  - Système d’exploitation Windows Server 2008 R2

  - Système d’exploitation Windows Server 2008

  - Windows Server 2008 entreprise 32 bits

  - Versions 32 ou 64 bits du système d’exploitation Windows Server 2003 R2

  - Versions 32 ou 64 bits du système d’exploitation Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Niveau fonctionnel de la forêt et du domaine

Vous devez déclencher tous les domaines dans lesquels vous déployez Lync Server 2013 vers un niveau de fonctionnement du domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou Windows Server 2003.

Toutes les forêts dans lesquelles vous déployez Lync Server 2013 doivent être déclenchées à un niveau de fonctionnalité de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Prise en charge des contrôleurs de domaine en lecture seule

Lync Server 2013 prend en charge les déploiements des services de domaine Active Directory (AD FS) qui incluent des contrôleurs de domaine en lecture seule ou des serveurs de catalogue global en lecture seule, tant qu’il existe des contrôleurs de domaine accessibles en écriture.

</div>

<div>

## <a name="domain-names"></a>Noms de domaine

Le serveur Lync ne prend pas en charge les domaines à étiquette unique. Par exemple, une forêt avec un domaine racine appelé **contoso. local** est prise en charge, mais un domaine racine nommé **local** n’est pas pris en charge. Pour plus d’informations, reportez-vous à l’article 300684 de la base de connaissances Microsoft, intitulé «informations sur la configuration [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)de Windows pour les domaines avec des noms DNS en une seule étiquette».

<div>


> [!NOTE]  
> Le serveur Lync ne prend pas en charge le changement de nom de domaines. Si vous avez besoin de renommer un domaine sur lequel Lync Server est déployé, vous devez commencer par désinstaller Lync Server, puis renommer le domaine, puis réinstaller Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Environnements AD DS verrouillés

Dans un environnement AD DS verrouillé, les utilisateurs et les objets ordinateur sont souvent placés dans des unités d’organisation (UO) spécifiques avec l’héritage des autorisations désactivé pour sécuriser la délégation d’administration et permettre l’utilisation des objets de stratégie de groupe pour l’application. stratégies de sécurité. Lync Server 2013 peut être déployé dans un environnement Active Directory verrouillé. Pour plus d’informations sur les éléments requis pour déployer Lync Server dans un environnement verrouillé, voir [préparer un service de domaine Active Directory (AD FS) verrouillé dans Lync server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

