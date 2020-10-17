---
title: Topologie de référence Lync Server 2013 pour les organisations de taille moyenne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2549acbf8b5eac2ac909eb213d6d73e8233b0a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536701"
---
# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Topologie de référence pour Lync Server 2013 dans les organisations de taille moyenne

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La topologie de référence avec haute disponibilité et centre de données unique est conçue pour une entreprise de taille petite ou moyenne dotée d’un site central. La topologie exacte dans le diagramme suivant est pour une organisation de 20 000 utilisateurs.

**Topologie de référence pour les organisations de taille moyenne**

![Diagramme de topologie de référence pour un centre de données unique](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Diagramme de topologie de référence pour un centre de données unique")

  - **Prendre en charge un plus grand nombre d’utilisateurs en ajoutant des serveurs frontaux.**     La topologie exacte dans ce diagramme dispose de trois serveurs frontaux pour fournir la prise en charge des utilisateurs 20 000. Si vous disposez d’un seul site central et de plusieurs utilisateurs, vous pouvez simplement ajouter des serveurs frontaux au pool. Le nombre maximal d’utilisateurs par pool est de 80 000, avec douze serveurs frontaux.
    
    Néanmoins, la topologie sur site unique peut prendre en charge davantage d’utilisateurs en ajoutant un autre pool frontal au site.

  - La **récupération d’urgence a pu être ajoutée.**     Pour cette organisation, la haute disponibilité de leurs services Lync Server est une fonctionnalité nécessaire, mais pas la récupération d’urgence. Le pool de serveurs frontaux qu’ils ont déployé offre une haute disponibilité.
    
    S’ils souhaitaient ajouter une fonctionnalité de récupération d’urgence, ils peuvent envisager d’établir un autre centre de données et d’y ajouter un autre pool frontal et de le coupler au pool frontal dans leur centre de données actuel. En cas de sinistre affectant leur pool principal, les administrateurs pouvaient basculer les utilisateurs vers le pool de sauvegarde.

  - **Les serveurs principaux sont mis en miroir**     Afin de fournir une haute disponibilité pour les fonctionnalités utilisateur de base, l’organisation a déployé une paire de serveurs principaux en miroir pour chaque pool frontal. Il s’agit d’une nouvelle option de topologie pour Lync Server 2013 et est facultative. Vous pouvez choisir de déployer un seul serveur principal à la place.

  - **Options de base de données du serveur de surveillance.**     Cette organisation a déployé la surveillance pour garantir la qualité des appels vocaux d’entreprise et des conférences A/V. La surveillance est déployée sur chaque serveur frontal et la base de données de surveillance est colocalisée avec les serveurs principaux. Nous prenons également en charge les topologies dans lesquelles la base de données de surveillance se trouve sur un serveur distinct.

  - **Haute disponibilité**     du serveur Edge Dans cet exemple d’organisation avec 20 000 utilisateurs, un seul serveur Edge suffira pour les performances. Toutefois, il existe un pool de deux serveurs Edge déployés pour fournir une haute disponibilité.

  - **Options de déploiement de site de succursale.**     L’organisation de cette topologie a une voix entreprise déployée en tant que solution vocale. Le site de succursale 1 ne dispose pas d’un lien de réseau étendu (WAN) résilient vers le site central, de sorte qu’il dispose d’un Survivable Branch Appliance déployé pour maintenir de nombreuses fonctionnalités Lync Server en cas de panne de la liaison de réseau étendu vers le site central. Le site de succursale 2 possède toutefois une liaison de réseau étendu résilient, de sorte qu’une seule passerelle de réseau téléphonique commuté (PSTN) est nécessaire. La passerelle PSTN déployée prend en charge la déviation du trafic multimédia, de sorte qu’aucun serveur de médiation n’est nécessaire sur le site de succursale 2. Pour plus d’informations sur la décision de déploiement sur un site de succursale, voir [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) dans la documentation de planification.

  - **Équilibrage de la charge DNS.**     Le pool de serveurs andEdge de pool frontal, a un équilibrage de charge DNS pour le trafic SIP déployé. Cela vous évite de devoir recourir à des programmes d’équilibrage de la charge pour les serveurs Edge et cela réduit significativement la configuration et la maintenance des programmes d’équilibrage de la charge pour les autres pools, étant donné que les programmes d’équilibrage de la charge sont uniquement requis pour le trafic HTTP. Pour plus d’informations sur l’équilibrage de la charge DNS, voir [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

  - **Déploiement de la messagerie unifiée Exchange** Cette topologie de référence inclut un serveur de messagerie unifiée Exchange, qui exécute Microsoft Exchange Server, et non Lync Server.
    
    Pour plus d’informations sur la messagerie unifiée Exchange, consultez la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et l' [intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Office Web Apps Server.** Nous vous recommandons de déployer une batterie de serveurs Office Web Apps Server ou Office Web Apps Server dans toutes les organisations qui utilisent la conférence Web. Office Web Apps Server permet de présenter des diapositives PowerPoint dans des conférences Web. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Les serveurs Edge sont recommandés.**     Bien que le déploiement d’un serveur Edge ne soit pas obligatoire, nous vous recommandons de le déployer pour n’importe quelle taille de déploiement. Vous pouvez optimiser votre investissement Lync Server en déployant un serveur Edge pour fournir des services aux utilisateurs qui se trouvent actuellement en dehors des pare-feu de votre organisation. Les avantages sont les suivants :
    
      - Les utilisateurs de votre organisation peuvent utiliser les fonctionnalités de Lync Server, s’ils travaillent de chez eux ou s’ils sont en déplacement.
    
      - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.
    
      - Si vous avez un partenaire, un fournisseur ou une organisation cliente qui utilise également Lync Server, vous pouvez former une *relation fédérée* avec cette organisation. Votre déploiement Lync Server reconnaîtrait alors les utilisateurs de cette organisation fédérée, ce qui permettra une meilleure collaboration.
    
      - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publics, y compris tout ou partie des éléments suivants : Windows Live, AOL, Yahoo \! et Google Talk. Une licence distincte peut être requise pour la connectivité PIC avec ces services.
        
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

  - Des **directeurs peuvent être ajoutés.**     Si cette organisation voulait aider à renforcer la sécurité contre les attaques par déni de service, elle peut également déployer un pool de directeurs. Un directeur est un rôle de serveur distinct et facultatif dans Lync Server qui n’utilise pas de comptes d’utilisateurs personnels, ou fournit des services de présence ou de conférence. Il sert de serveur de tronçon suivant interne vers lequel un serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie les requêtes entrantes et les redirige vers le serveur ou le pool d’accueil de l’utilisateur. La pré-authentification au niveau du directeur permet de supprimer les demandes des comptes d’utilisateur inconnus du déploiement. Un directeur aide à isoler les serveurs frontaux du trafic malveillant, tels que les attaques par déni de service (DoS). Si le réseau est inondé avec du trafic externe non valide lors d’une attaque de ce type, le trafic se termine au niveau du directeur.

  - **System Center Operations Manager est recommandé.**    Nous vous recommandons de surveiller l’état de votre déploiement Lync Server afin de garantir la disponibilité du service pour les utilisateurs finaux. Vous pouvez surveiller Lync avec le pack d’administration System Center Operations Manager pour Lync, disponible gratuitement auprès de Microsoft. Avec le pack d’administration Lync, vous pouvez activer de manière proactive des alertes en temps réel lorsque des problèmes surviennent, exécuter des transactions synthétiques pour tester les fonctionnalités Lync de bout en bout, obtenir des rapports sur la disponibilité des services, etc. Cela vous permet de répondre de manière proactive aux problèmes de votre déploiement avant que les utilisateurs finaux ne les connaissent.

</div>

<span> </span>

</div>

</div>

</div>

