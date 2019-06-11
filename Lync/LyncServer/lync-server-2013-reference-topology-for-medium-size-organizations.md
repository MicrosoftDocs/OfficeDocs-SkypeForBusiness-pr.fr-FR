---
title: Topologie de référence de Lync Server 2013 pour les organisations de taille moyenne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41a003bd87e4dc8b85e78946a5ce870f3f6dd045
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Topologie de référence de Lync Server 2013 pour les organisations de taille moyenne

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-10-07_

La topologie de référence avec haute disponibilité et centre de données unique est conçue pour une entreprise de taille petite ou moyenne dotée d’un site central. La topologie exacte présentée dans le diagramme suivant est destinée à une organisation de 20 000 utilisateurs.

**Topologie de référence pour des organisations de taille moyenne**

![Topologie de référence pour un diagramme du centre de données] (images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Topologie de référence pour un diagramme du centre de données")

  - **Pour permettre à d’autres utilisateurs d’ajouter d’autres serveurs frontaux.**    La topologie exacte de ce diagramme est composée de trois serveurs frontaux pour fournir une prise en charge des utilisateurs de 20 000. Si vous avez un seul site central et des utilisateurs supplémentaires, vous pouvez simplement ajouter davantage de serveurs frontaux dans le pool. Le nombre maximal d’utilisateurs par pool est 80 000, avec douze serveurs frontaux.
    
    Néanmoins, la topologie sur site unique peut prendre en charge davantage d’utilisateurs en ajoutant un autre pool frontal au site.

  - **Une reprise après sinistre a pu être ajoutée.**    Pour cette organisation, il est nécessaire de disposer d’une haute disponibilité pour les services Lync Server, mais pas de la reprise après sinistre. La réserve de serveurs frontaux déployés offre une disponibilité élevée.
    
    Pour disposer d’une fonctionnalité de récupération d’urgence, cette organisation peut établir un autre centre de données et ajouter un autre pool frontal, en le couplant au pool frontal du centre de données actuel. Si une catastrophe devait affecter le pool principal, les administrateurs pourraient effectuer un basculement des utilisateurs vers le pool de sauvegarde.

  - **Les serveurs dorsaux sont mis en miroir**   pour offrir une plus grande disponibilité aux fonctionnalités utilisateur de base, l’organisation a déployé une paire de serveurs dorsaux en miroir pour chaque pool frontal. Il s’agit d’une nouvelle option de topologie pour Lync Server 2013, qui est facultative. Vous pouvez choisir de déployer un serveur principal unique à la place.

  - **Options de base de données du serveur surveillées.**    Cette organisation a déployé une analyse pour garantir la qualité des appels vocaux d’entreprise et des conférences A/V. La surveillance est déployée sur chaque serveur frontal et la base de données de surveillance est colocalisée avec les serveurs principaux. Nous prenons également en charge les topologies dans lesquelles la base de données de surveillance est située sur un serveur distinct.

  - **Haute disponibilité du serveur Edge**    Dans cet exemple d’organisation avec des utilisateurs de 20 000, un seul serveur Edge serait suffisant pour les performances. Néanmoins, il existe un pool de deux serveurs Edge déployés pour offrir une disponibilité élevée.

  - **Options de déploiement d’un site de succursale.**    L’organisation de cette topologie dispose d’Enterprise Voice déployé comme solution vocale. Le site de succursale 1 ne possède pas de lien réseau étendu (WAN) sur le site central, de sorte qu’il dispose d’une unité de branchement Survivable déployée pour gérer de nombreuses fonctionnalités de Lync Server en cas de panne du lien WAN vers le site central. Le site de succursale 2 possède toutefois une liaison WAN résiliente, de sorte qu’il n’est pas nécessaire de disposer d’une passerelle RTC (réseau téléphonique commuté). La passerelle RTC déployée prend en charge la fonctionnalité de contournement du contenu multimédia; donc aucun serveur d’intermédiation n’est requis au niveau du site de succursale 2. Pour plus d’informations sur la décision de déploiement sur un site de succursale, voir [planification de la résilience vocale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) dans la documentation de planification.

  - **Équilibrage de charge DNS.**    Le pool frontal andEdge serveur, l’équilibrage de charge DNS du trafic SIP déployé. Cela vous évite de devoir recourir à un appareil d’équilibrage de charge pour les serveurs Edge et cela réduit significativement la configuration et la maintenance des appareils d’équilibrage de charge pour les autres pools, car les appareils d’équilibrage de charge sont uniquement nécessaires pour le trafic HTTP. Pour plus d’informations sur l’équilibrage de charge DNS, voir [équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

  - **Déploiement de la messagerie unifiée Exchange.** Cette topologie de référence inclut un serveur Exchange Unified Messaging (UM) qui exécute Microsoft Exchange Server et non Lync Server.
    
    Pour plus d’informations sur la messagerie unifiée Exchange, voir [planification d’une intégration de messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Office Web Apps Server.** Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web. Office Web Apps Server permet de présenter des diapositives PowerPoint au cours de conférences Web. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Il est recommandé d’avoir un serveur Edge.**    Le déploiement d’un serveur de périphérie n’est pas obligatoire, mais nous vous recommandons de le faire pour toute taille de déploiement. Vous pouvez optimiser votre investissement sur votre serveur Lync en déployant un serveur Edge pour fournir des services aux utilisateurs qui se trouvent en dehors des pare-feu de votre organisation. Les avantages sont les suivants :
    
      - Les utilisateurs de votre organisation peuvent utiliser la fonctionnalité de serveur Lync, s’ils travaillent à la maison ou sont en déplacement.
    
      - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.
    
      - Si un partenaire, un fournisseur ou une organisation cliente utilise également Lync Server, vous pouvez créer une *relation fédérée* avec cette organisation. Le déploiement de votre serveur Lync reconnaît alors les utilisateurs de cette organisation fédérée pour une meilleure collaboration.
    
      - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publique, y compris tout ou partie des éléments suivants:\!Windows Live, AOL, Yahoo et Google Talk. Une licence distincte peut être nécessaire pour la connectivité de messagerie instantanée publique avec ces services.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity («PIC USL») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
        > <LI>
        > <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, le contrat sous-jacent pour lequel le son est arrêté.</P>
        > <LI>
        > <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>

        
        </div>

  - **Les directeurs peuvent être ajoutés.**    Si cette organisation souhaitait améliorer la sécurité contre les attaques par déni de service, elle peut également déployer un pool de directeurs. Un directeur est un rôle de serveur distinct facultatif dans Lync Server qui n’utilise pas de compte d’utilisateur familial ou fournit des services de présence et de conférence. Il sert de serveur interne de tronçons de tronçon sur lequel un serveur de périphérie route le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie les demandes entrantes et les redirige vers le serveur ou le groupe de destination de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur permet d’isoler les serveurs frontaux du trafic malveillant, tels que les attaques par déni de service (DoS). Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, le trafic se termine au directeur.

  - **System Center Operations Manager est recommandé.**   Nous vous recommandons de surveiller l’état de votre déploiement de Lync Server afin de garantir la disponibilité du service pour les utilisateurs finaux. Vous pouvez surveiller Lync avec le pack d’administration System Center Operations Manager pour Lync disponible en téléchargement gratuit depuis Microsoft. Le pack d’administration de Lync vous permet d’obtenir des alertes en temps réel en temps réel en cas de problème, d’exécuter des transactions synthétiques pour tester la fonctionnalité Lync de bout en bout, d’obtenir des rapports sur la disponibilité du service, etc. This helps you to proactively respond to issues with your deployment before end-users experience them.

</div>

<span> </span>

</div>

</div>

</div>

