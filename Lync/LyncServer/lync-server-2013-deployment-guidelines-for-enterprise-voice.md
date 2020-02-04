---
title: 'Lync Server 2013 : Instructions de déploiement de Voix Entreprise'
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
ms.openlocfilehash: 221c09fc5dadda267baad35f4784c22cc4f3c9c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Instructions de déploiement de Voix Entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Cette rubrique décrit les conditions préalables et d’autres recommandations à prendre en compte lors de la planification du déploiement de Lync Server 2013 et de la charge de travail voix entreprise.

<div>

## <a name="deployment-prerequisites"></a>Prérequis de déploiement

Pour une qualité optimale lors du déploiement d’Enterprise Voice, assurez-vous que votre infrastructure, réseau et systèmes informatiques répondent aux conditions préalables suivantes :

  - Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.

  - Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, notamment les serveurs Edge avec service Edge d’accès, service Edge A/V, service Edge de conférence Web et un proxy inverse.

  - Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou le dernier Service Pack ou Microsoft Exchange Server 2010 est installé. L’une de ces fonctionnalités est nécessaire pour l’intégration de la messagerie unifiée Exchange avec Lync Server et pour fournir des notifications complètes et des informations de journalisation d’appels aux points de terminaison clients.

  - Un numéro de téléphone principal unique a été désigné, normalisé et copié sur l’attribut **msRTCSIP-Line** pour chaque utilisateur qui doit être activé pour voix entreprise.
    
    <div>
    

    > [!NOTE]  
    > Lync Server prend en charge les numéros E. 164 et les numéros de numérotation à l’intérieur non directs. Les nombres non-did peuvent être représentés au format <STRONG> &lt;E. 164&gt;; ext =&lt;extension&gt; </STRONG> ou sous la forme d’une chaîne de chiffres, ce qui exige que l’extension privée soit unique dans l’entreprise. Par exemple, un nombre privé d' 1001 peut être représenté sous la forme <STRONG>+ 1425550100 ; ext = 1001</STRONG>ou As <STRONG>1001</STRONG>. S’il est représenté en tant que <STRONG>1001</STRONG>, il est possible que ce numéro privé soit unique au sein de l’entreprise.

    
    </div>

  - Les administrateurs qui déploient Enterprise Voice doivent être membres du groupe RTCUniversalServerAdmins.

  - Le déploiement d’Office Communicator 2007 est au minimum effectué. Pour utiliser les nouvelles fonctionnalités de cette version, Lync 2013 est déployé.

  - Le déploiement et la configuration de l’infrastructure à clé managée (MKI) s’effectue à l’aide d’une infrastructure de certification (CA) Microsoft ou tierce.

  - Chaque ordinateur sur lequel vous installez le serveur de médiation doit être :
    
      - Serveur membre d’un domaine et préparé pour les services de domaine Active Directory (AD FS). Pour les procédures de préparation des services de domaine Active Directory, voir [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.
    
      - Exécutant l’un des systèmes d’exploitation suivants :
        
          - <span></span>  
            Version 64 bits du système d’exploitation Windows Server 2008 standard
        
          - <span></span>  
            Version 64 bits du système d’exploitation Windows Server 2008 entreprise

  - S’il s’agit d’une connexion de réseau téléphonique commuté (PSTN) ou d’échange de succursale privée (PBX) par le biais d’une connexion de multiplexage par répartition du temps, une ou plusieurs passerelles RTC sont disponibles pour le déploiement. (S’il s’agit d’une connexion SIP par le biais d’une connexion SIP, une passerelle RTC n’est pas nécessaire.)

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Pannes d’alimentation, de réseau ou de service téléphonique

En cas de panne, de perturbation ou d’autres dégradations des services d’alimentation, de réseau ou de téléphone dans votre emplacement, la voix, la messagerie instantanée, la présence et d’autres fonctionnalités de Lync Server et de n’importe quel appareil connecté à Lync Server peut ne pas fonctionner correctement.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Voix entreprise dépend de la disponibilité du serveur et du client vocal et de l’organisation matérielle

Les communications vocales avec Lync Server dépendent de la disponibilité du logiciel serveur et du fonctionnement approprié des clients vocaux ou des appareils de téléphone matériel qui se connectent au logiciel serveur.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Autres moyens d’accès aux services d’urgence

Pour les emplacements où vous installez un client vocal (par exemple, un PC exécutant un client Lync ou un appareil Lync Phone Edition), nous vous recommandons de conserver une option de sauvegarde pour les utilisateurs pour appeler des services d’urgence (par exemple, 911 ou 999) en cas de panne de courant. , de la dégradation de la connectivité réseau, du service de téléphone ou d’autres problèmes qui risquent d’empêcher le fonctionnement des appareils Lync Server, Lync ou Lync Phone Edition. Par exemple, il peut s’agir d’un téléphone relié à une ligne réseau téléphonique commutée standard ou à un téléphone mobile.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Appels d’urgence et systèmes téléphoniques multilignes

L’utilisation d’un système téléphonique multiligne (MLTS) peut être soumise à une loi américaine ou fédérale des États-Unis ou aux lois d’autres pays/régions qui requièrent que le MLTS fournisse le numéro de téléphone, l’extension et/ou l’emplacement physique d’un appelant aux services d’urgence en vigueur lors de la mise en place d’un appelant aux services d’urgence (par exemple, 999 911 lorsque Dans cette version, Lync Server peut être configuré pour fournir l’emplacement physique d’un appelant à un fournisseur de services d’urgence, comme décrit dans la rubrique [planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). La conformité avec la législation MLTS est la seule responsabilité de l’acquéreur de périphériques Lync Server, Lync et Lync Phone Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

