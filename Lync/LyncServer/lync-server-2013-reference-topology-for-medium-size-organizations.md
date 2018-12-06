---
title: "Topo. de réf. de Lync Server 2013 pour les organisations de taille moyenne"
TOCTitle: Topologie de référence pour les organisations de taille moyenne
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425939(v=OCS.15)
ms:contentKeyID: 49297048
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologie de référence de Lync Server 2013 pour les organisations de taille moyenne

 

_**Dernière rubrique modifiée :** 2013-10-07_

La topologie de référence avec haute disponibilité et centre de données unique est conçue pour une entreprise de taille petite ou moyenne dotée d’un site central. La topologie exacte présentée dans le diagramme suivant est destinée à une organisation de 20 000 utilisateurs.

**Topologie de référence pour des organisations de taille moyenne**

![Diagramme de topologie de référence pour un seul centre de données](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Diagramme de topologie de référence pour un seul centre de données")

  - **Augmentez le nombre d’utilisateurs pris en charge en ajoutant des serveurs frontaux supplémentaires.**    La topologie exacte présentée dans ce diagramme inclut trois serveurs frontaux pour prendre en charge jusqu’à 20 000 utilisateurs. Si vous avez un seul site central et des utilisateurs supplémentaires, vous pouvez simplement ajouter davantage de serveurs frontaux dans le pool. Le nombre maximal d’utilisateurs par pool est 80 000, avec douze serveurs frontaux.
    
    Néanmoins, la topologie sur site unique peut prendre en charge davantage d’utilisateurs en ajoutant un autre pool frontal au site.

  - **La récupération d’urgence peut être ajoutée.**    Pour cette organisation, la haute disponibilité de ses services Lync Server est une fonctionnalité nécessaire, mais pas la récupération d’urgence. Le pool de serveurs frontaux qu’elle a déployé fournit une haute disponibilité.
    
    Pour disposer d’une fonctionnalité de récupération d’urgence, cette organisation peut établir un autre centre de données et ajouter un autre pool frontal, en le couplant au pool frontal du centre de données actuel. Si une catastrophe devait affecter le pool principal, les administrateurs pourraient effectuer un basculement des utilisateurs vers le pool de sauvegarde.

  - **Les serveurs principaux sont mis en miroir.**   Pour garantir une meilleure disponibilité pour les fonctionnalités utilisateur, l’organisation a déployé une paire de serveurs principaux mis en miroir pour chaque pool de serveurs frontaux. Il s’agit d’une nouvelle option de topologie pour Lync Server 2013 (facultative). Vous pouvez choisir de déployer plutôt un serveur principal unique.

  - **Options de base de données du serveur de surveillance.**    Cette organisation a déployé une fonctionnalité de surveillance pour assurer la qualité des appels Voix Entreprise et des conférences A/V. La surveillance est déployée sur chaque serveur frontal et la base de données de surveillance est colocalisée avec les serveurs principaux. Nous prenons également en charge les topologies dans lesquelles la base de données de surveillance est située sur un serveur distinct.

  - **Haute disponibilité du serveur Edge.**    Dans cet exemple d’organisation comportant 20 000 utilisateurs, un seul serveur Edge suffit pour obtenir les performances souhaitées. Cependant, un pool de deux serveurs Edge est déployé afin de fournir une haute disponibilité.

  - **Options de déploiement de site de succursale.**    L’organisation dans cette topologie a déployé Voix Entreprise en tant que solution de voix. Le site de succursale 1 ne dispose d’aucune liaison de réseau étendu (WAN) robuste vers le site central. Un Survivable Branch Appliance est donc déployé pour permettre la gestion des nombreuses fonctionnalités Lync Server en cas de défaillance de la liaison de réseau étendu vers le site central. Néanmoins, le site de succursale 2 comporte une liaison de réseau étendu robuste ; seule une passerelle RTC est donc nécessaire. La passerelle RTC déployée ici prend en charge la déviation du trafic multimédia. Aucun serveur de médiation n’est donc nécessaire sur le site de succursale 2. Pour plus d’informations sur le choix des éléments à déployer sur un site de succursale, reportez-vous à [Planification de la résistance vocale d’un site de succursale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) dans la documentation de planification.

  - **Équilibrage de charge DNS.**    Le pool frontal et le pool de serveurs Edge disposent d’un équilibrage de charge DNS pour le trafic SIP. Cela vous évite de devoir recourir à un appareil d’équilibrage de charge pour les serveurs Edge et cela réduit significativement la configuration et la maintenance des appareils d’équilibrage de charge pour les autres pools, car les appareils d’équilibrage de charge sont uniquement nécessaires pour le trafic HTTP. Pour plus d’informations sur l’équilibrage de charge DNS, reportez-vous à [Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

  - **Déploiement de la messagerie unifiée Exchange.**    Cette topologie de référence inclut un serveur de messagerie unifiée Exchange, qui exécute Microsoft Exchange Server et non Lync Server
    
    Pour plus d’informations sur la messagerie unifiée Exchange, reportez-vous à [Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [Intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Office Web Apps Server.**    Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences web. Office Web Apps Server permet de présenter des diapositives Powerpoint au cours de conférences web. Pour plus d’informations, reportez-vous à [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Les serveurs Edge sont recommandés.**    Même si le déploiement d’un serveur Edge n’est pas obligatoire, nous vous conseillons de l’effectuer pour toute taille de déploiement. Vous pouvez optimiser votre investissement dans Lync Server en déployant un serveur Edge pour fournir des services aux utilisateurs se trouvant hors des pare-feu de votre organisation. Les avantages sont les suivants :
    
      - Les utilisateurs de votre organisation peuvent utiliser les fonctionnalités de Lync Server, s’ils travaillent de chez eux ou s’ils sont en déplacement.
    
      - Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.
    
      - Si un partenaire, un fournisseur ou un client avec qui vous êtes en relation, utilise également Lync Server, vous pouvez former une *relation fédérée* avec l’organisation de cette personne. Le déploiement Lync Server reconnaîtra alors les utilisateurs de cette organisation fédérée pour une meilleure collaboration.
    
      - Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publics, notamment : Windows Live, AOL, Yahoo\! et Google Talk. Une licence distincte peut être nécessaire pour la connectivité de la messagerie instantanée publique avec ces services.
        
        > [!IMPORTANT]  
        > <ul>        
        > <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>        
        > <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>        
        > <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li>
        > </ul>


  - **Des directeurs peuvent être ajoutés.**    Si cette organisation veut accroître la sécurité face aux attaques par déni de service, elle peut également déployer un pool directeur. Un directeur est un rôle serveur distinct, facultatif, dans Lync Server, qui n’héberge pas de comptes d’utilisateur et ne fournit pas de services de présence ou de conférence. Il sert de serveur du tronçon suivant interne vers lequel un serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur pré-authentifie les requêtes entrantes et les redirige vers le pool ou le serveur central de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les requêtes des comptes d’utilisateur inconnus dans le déploiement. Un directeur aide à isoler les serveurs frontaux du trafic malveillant, par exemple, les attaques par déni de service (DoS). Si le réseau est saturé en raison d’un trafic externe non valide lié à ce type d’attaque, le trafic s’arrête au niveau du directeur.

  - **System Center Operations Manager est recommandé.**    Nous vous recommandons de surveiller l’intégrité de votre déploiement Lync Server afin de garantir la disponibilité du service pour l’utilisateur final. Vous pouvez surveiller Lync à l’aide du pack d’administration System Center Operations Manager pour Lync, qui peut être téléchargé gratuitement sur le site de Microsoft. Grâce au pack d’administration Lync, vous pouvez obtenir de manière proactive des alertes en temps réel quand des problèmes surviennent, exécuter des transactions synthétiques pour tester de bout en bout les fonctionnalités de Lync, obtenir des rapports sur la disponibilité du service, etc. Cela vous permet de répondre de manière proactive aux problèmes liés à votre déploiement avant que l’utilisateur final n’y soit confronté.

