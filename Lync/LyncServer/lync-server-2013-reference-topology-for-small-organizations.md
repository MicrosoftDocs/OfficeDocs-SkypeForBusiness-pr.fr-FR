---
title: Topologie de référence de Lync Server 2013 pour les petites entreprises
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Topologie de référence pour Lync Server 2013 dans les petites organisations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La topologie de référence pour les petites organisations montre comment vous pouvez déployer une solution robuste et facilement disponible en déployant uniquement trois serveurs exécutant Lync Server.

**Topologie de référence pour les petites organisations**

![Diagramme de topologie de référence déployant trois serveurs](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagramme de topologie de référence déployant trois serveurs")

  - **Paire de serveurs Standard Edition déployés**     cette organisation a des utilisateurs 4 000 sur leur site central. L’organisation a déployé deux serveurs Standard Edition et les a couplés pour permettre une haute disponibilité et une reprise après sinistre. Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Pour plus d’informations sur les fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013, voir [planification d’une haute disponibilité et reprise après sinistre dans Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Le déploiement de Edge Server est recommandé.**    Même si le déploiement d’un serveur de périphérie n’est pas requis pour la messagerie instantanée interne, la présence et les conférences, nous le recommandons même pour les petits déploiements. Vous pouvez optimiser votre investissement sur votre serveur Lync en déployant un serveur Edge pour fournir des services aux utilisateurs qui se trouvent en dehors des pare-feu de votre organisation. Les avantages sont les suivants :
    
      - Les utilisateurs de votre organisation peuvent utiliser la fonctionnalité de serveur Lync, s’ils travaillent à la maison ou sont en déplacement.
    
      - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.
    
      - Si un partenaire, un fournisseur ou une organisation cliente utilise également Lync Server, vous pouvez créer une *relation fédérée* avec cette organisation. Le déploiement de votre serveur Lync reconnaît alors les utilisateurs de cette organisation fédérée pour une meilleure collaboration.
    
      - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publique, y compris tout ou partie des éléments suivants :\!Windows Live, AOL, Yahoo et Google Talk. Une licence distincte peut être nécessaire pour la connectivité de messagerie instantanée publique avec ces services.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo ! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
        > <LI>
        > <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, le contrat sous-jacent pour lequel le son est arrêté.</P>
        > <LI>
        > <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>

        
        </div>

  - **Survie du site de succursale.**    Cette organisation exécute un programme pilote de la fonctionnalité voix entreprise de Lync Server. Certains utilisateurs utilisent Lync Server comme solution vocale unique. Certains de ces utilisateurs de pilotes vocaux sont disponibles sur le site de la succursale. Le site de succursale ne possède pas de lien réseau étendu (WAN) fiable vers le site central ; de sorte qu’une unité de branchement survivant y est déployée. Ainsi, si la liaison de réseau étendu ne fonctionne pas, les utilisateurs sur le site de la succursale peuvent continuer à passer et à recevoir des appels (au sein de l’organisation et des appels RTC), à utiliser leur messagerie vocale et à communiquer par le biais de la messagerie instantanée à deux personnes. Les utilisateurs peuvent également être authentifiés lorsque la liaison de réseau étendu n’est plus disponible.

  - **Déploiement de la messagerie unifiée Exchange.** Cette topologie de référence inclut un serveur Exchange Unified Messaging (UM) qui exécute Microsoft Exchange Server et non Lync Server.
    
    Pour plus d’informations sur la messagerie unifiée Exchange, voir [planification d’une intégration de messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Office Web Apps Server.** Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Office Web Apps Server vous permet de présenter des diapositives PowerPoint lors de conférences Web. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

