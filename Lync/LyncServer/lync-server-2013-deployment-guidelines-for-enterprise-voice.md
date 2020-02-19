---
title: 'Lync Server 2013 : instructions de déploiement pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc2aee745a362e58003c62f483dda6c63ab244f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Instructions de déploiement de voix entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Cette rubrique décrit les conditions préalables et les autres instructions à prendre en compte lorsque vous envisagez de déployer Lync Server 2013 et la charge de travail voix entreprise.

<div>

## <a name="deployment-prerequisites"></a>Conditions préalables du déploiement

Pour une expérience optimale lors du déploiement de voix entreprise, assurez-vous que votre infrastructure, votre réseau et vos systèmes informatiques remplissent les conditions préalables suivantes :

  - Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.

  - Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, y compris les serveurs Edge avec le service Edge d’accès, le service Edge A/V, le service Edge de conférence Web et un proxy inverse.

  - Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou le Service Pack le plus récent, ou Microsoft Exchange Server 2010 est installé. L’une d’entre elles est requise pour l’intégration de la messagerie unifiée Exchange avec Lync Server et pour fournir des notifications enrichies et des informations de journal des appels aux points de terminaison du client.

  - Un numéro de téléphone principal unique a été désigné, normalisé et copié dans l’attribut **msRTCSIP-Line** pour chaque utilisateur à activer pour voix entreprise.
    
    <div>
    

    > [!NOTE]  
    > Lync Server prend en charge les numéros E. 164 et les numéros DID (non directs). Les nombres non did peuvent être représentés au format <STRONG> &lt;E. 164&gt;; ext =&lt;extension&gt; </STRONG> ou en tant que chaîne de chiffres, avec la nécessité que l’extension privée soit unique dans l’entreprise. Par exemple, le numéro privé 1 001 peut être représenté comme suit : <STRONG>+1425550100;ext=1001</STRONG> ou <STRONG>1001</STRONG>. S’il est représenté comme <STRONG>1001</STRONG>, ce numéro privé doit être unique dans l’entreprise.

    
    </div>

  - Les administrateurs qui déploient voix entreprise doivent être membres du groupe RTCUniversalServerAdmins.

  - Au minimum, Office Communicator 2007 est déployé avec succès. Pour utiliser les nouvelles fonctionnalités de cette version, Lync 2013 est déployé.

  - L’infrastructure MKI (Managed key infrastructure) est déployée et configurée, à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.

  - Chaque ordinateur sur lequel vous installez un serveur de médiation doit :
    
      - Un serveur membre d’un domaine et préparé pour les services de domaine Active Directory. Pour connaître les procédures de préparation des services de domaine Active Directory, voir [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.
    
      - Exécuter l’un des systèmes d’exploitation suivants :
        
          - <span></span>  
            Édition 64 bits du système d’exploitation Windows Server 2008 Standard
        
          - <span></span>  
            Édition 64 bits du système d’exploitation Windows Server 2008 Enterprise

  - Si la connexion au réseau téléphonique commuté (PSTN) ou à l’autocommutateur privé (PBX) s’effectue au moyen d’une connexion TDM (multiplexage temporel), une ou plusieurs passerelles PSTN sont disponibles pour le déploiement. (Si la connexion s’effectue via une jonction SIP, une passerelle PSTN n’est pas nécessaire.)

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Coupure de courant, interruption du réseau ou du service téléphonique

En cas de panne, de perturbation ou d’autres dégradations des services d’alimentation, de réseau ou de téléphonie sur votre site, la voix, la messagerie instantanée, la présence et d’autres fonctionnalités de Lync Server et tout périphérique connecté à Lync Server peuvent ne pas fonctionner correctement.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Voix Entreprise dépend de la disponibilité du serveur et de l’opérabilité du client et du matériel vocal

Les communications vocales avec Lync Server dépendent de la disponibilité du logiciel serveur et du bon fonctionnement des clients vocaux ou des périphériques de téléphonie matériel se connectant au logiciel serveur.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Méthode alternative d’accès aux services d’urgence

Pour les emplacements où vous installez un client vocal (par exemple, un PC exécutant un client Lync ou un appareil Lync Phone Edition), nous vous recommandons de conserver une option de sauvegarde pour les utilisateurs qui appellent des services d’urgence (par exemple, 911 ou 999) en cas de panne de courant. , une dégradation de la connectivité réseau, une interruption du service téléphonique ou tout autre problème susceptible d’empêcher le fonctionnement des appareils Lync Server, Lync ou Lync Phone Edition. Une telle alternative peut consister en un téléphone connecté à une ligne de réseau téléphonique commuté (RTC) standard ou un téléphone mobile.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Appels d’urgence et systèmes téléphoniques multilignes

L’utilisation d’un système téléphonique multiligne (MLTS) peut être sujette à une réglementation d’état et/ou fédérale des États-Unis et à une réglementation étrangère relative aux systèmes téléphoniques multilignes exigeant du système qu’il fournisse le numéro de téléphone ou de poste et/ou l’emplacement physique de l’appelant aux services d’urgence appropriés lorsqu’un appel est effectué (par exemple, lorsque le numéro d’un service d’urgence, tel que le 18 ou le 112, est composé). Dans cette version, Lync Server peut être configuré pour fournir l’emplacement physique d’un appelant à un fournisseur de services d’urgence, comme décrit dans la rubrique [planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). La conformité avec les lois MLTS est la seule responsabilité de l’acheteur de Lync Server, du client Lync et des appareils Lync Phone Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

