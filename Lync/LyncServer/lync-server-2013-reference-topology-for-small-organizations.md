---
title: Topologie de référence Lync Server 2013 pour les petites organisations
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
ms.openlocfilehash: 0b9947fe1657551b901b6b68cc3efbbf811b261b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a>Topologie de référence pour Lync Server 2013 dans les petites organisations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La topologie de référence pour les petites organisations vous montre comment déployer une solution robuste hautement disponible en déployant uniquement trois serveurs exécutant Lync Server.

**Topologie de référence pour les petites organisations**

![Diagramme de la topologie de référence de déploiement de trois serveurs](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagramme de la topologie de référence de déploiement de trois serveurs")

  - **Paire de serveurs Standard Edition déployée**     cette organisation a 4 000 utilisateurs sur leur site central. L’organisation a déployé deux serveurs Standard Edition et les a associés pour permettre la haute disponibilité et la récupération d’urgence. Chaque serveur héberge 2 000 utilisateurs, mais les informations sur tous les utilisateurs sont synchronisées entre les deux serveurs. En cas de panne, un administrateur peut faire basculer ces utilisateurs pour qu’ils soient pris en charge par l’autre serveur, avec un minimum de perturbation pour les utilisateurs. Pour plus d’informations sur les fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013, consultez la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Le déploiement de serveur Edge est recommandé.**    Bien que le déploiement d’un serveur Edge ne soit pas requis pour la messagerie instantanée interne, la présence et la Conférence, nous vous recommandons de le faire même pour les déploiements de petite taille. Vous pouvez optimiser votre investissement Lync Server en déployant un serveur Edge pour fournir des services aux utilisateurs qui se trouvent actuellement en dehors des pare-feu de votre organisation. Les avantages sont les suivants :
    
      - Les utilisateurs de votre organisation peuvent utiliser les fonctionnalités de Lync Server, s’ils travaillent de chez eux ou s’ils sont en déplacement.
    
      - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.
    
      - Si vous avez un partenaire, un fournisseur ou une organisation cliente qui utilise également Lync Server, vous pouvez former une *relation fédérée* avec cette organisation. Votre déploiement Lync Server reconnaîtrait alors les utilisateurs de cette organisation fédérée, ce qui permettra une meilleure collaboration.
    
      - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publics, y compris tout ou partie des éléments suivants :\!Windows Live, AOL, Yahoo et Google Talk. Une licence distincte peut être requise pour la connectivité PIC avec ces services.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
        > <LI>
        > <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
        > <LI>
        > <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>

        
        </div>

  - **Survivabilité du site de succursale.**    Cette organisation exécute un programme pilote de la fonctionnalité voix entreprise de Lync Server. Certains utilisateurs utilisent Lync Server comme solution vocale unique. Certains de ces utilisateurs de la version pilote vocale se trouvent sur le site de succursale. Le site de succursale ne dispose pas d’un lien de réseau étendu (WAN) fiable vers le site central, c’est pourquoi un Survivable Branch Appliance est déployé à cet emplacement. Une fois cette fonctionnalité déployée, si la liaison de réseau étendu (WAN) tombe en panne, les utilisateurs du site de succursale peuvent continuer à passer et recevoir des appels (les deux appels au sein de l’organisation et les appels RTC), bénéficier des fonctionnalités de messagerie vocale et communiquer avec la messagerie instantanée (IM) à deux personnes. Les utilisateurs peuvent également être authentifiés lorsque la liaison WAN n’est plus disponible.

  - **Déploiement de la messagerie unifiée Exchange** Cette topologie de référence inclut un serveur de messagerie unifiée Exchange, qui exécute Microsoft Exchange Server, et non Lync Server.
    
    Pour plus d’informations sur la messagerie unifiée Exchange, consultez la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et l' [intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Office Web Apps Server.** Nous vous recommandons de déployer une batterie de serveurs Office Web Apps Server ou Office Web Apps Server dans toutes les organisations qui utilisent la conférence Web. Office Web Apps Server permet de présenter des diapositives PowerPoint dans des conférences Web. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

</div>

<span> </span>

</div>

</div>

</div>

