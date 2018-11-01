---
title: "Topo. réf. Lync Server 2013 util. ds grandes org. ac diff. centres de données"
TOCTitle: Topologie de référence utilisée dans les grandes organisations comportant plusieurs centres de données
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398797(v=OCS.15)
ms:contentKeyID: 49298285
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologie de référence de Lync Server 2013 utilisée dans les grandes organisations comportant plusieurs centres de données

 

_**Dernière rubrique modifiée :** 2012-10-22_

La prise en charge de la topologie de référence pour une grande organisation disposant de multiples centres de données est conçue pour toute taille d’entreprise dotée de plusieurs sites centraux. La topologie exacte du diagramme suivant est prévue pour une organisation comportant 50 000 utilisateurs, dont 20 000 sur le site central A, 20 000 sur le site central B et un total de 10 000 sur le site central C et les sites de succursale. Le type de topologie illustré dans ce diagramme peut convenir à toutes les organisations, quel que soit le nombre d’utilisateurs.

Outre la haute disponibilité offerte par les pools de serveurs frontaux, cette topologie ajoute la prise en charge de la récupération d’urgence. Les pools de serveurs frontaux dans les sites centraux A et B sont associés. Si l’un de ces pools ne fonctionne pas, l’administrateur peut déplacer les services pour les utilisateurs affectés vers le pool associé dans le site non affecté.

Cette topologie est présentée dans de nombreux diagrammes, avec tout d’abord une vue d’ensemble, suivie de vues détaillées des sites centraux.

**Vue d’ensemble de la topologie de référence pour les grandes organisations disposant de plusieurs centres de données**

![Topologie de référence pour des centres de données multiples](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topologie de référence pour des centres de données multiples")

**Topologie de référence pour les grandes organisations : vue détaillée du site central A**

![Planification des topologies de référence A](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "Planification des topologies de référence A")

**Topologie de référence pour les grandes organisations : vue détaillée du site central B**

![Planification des topologies de référence B](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "Planification des topologies de référence B")

**Topologie de référence pour les grandes organisations : vue détaillée du site central C**

![Planification des topologies de référence C](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "Planification des topologies de référence C")

  - **Les pools de serveurs frontaux sont associés afin d’activer la récupération d’urgence.**   Les pools de serveurs frontaux des sites A et B sont associés pour prendre en charge la récupération d’urgence. Si le pool d’un site échoue, l’administrateur peut basculer les utilisateurs de ce site vers le pool de serveurs frontaux associé de l’autre site, avec une interruption minimale de service pour les utilisateurs. Chacun de ces deux pools frontaux possède six serveurs, ce qui suffit pour les 40 000 utilisateurs des deux pools en cas de basculement. Pour plus d’informations, reportez-vous à [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Les serveurs principaux sont mis en miroir**   L’organisation a déployé une paire de serveurs principaux mis en miroir pour chaque pool de serveurs frontaux afin de garantir une meilleure disponibilité pour les fonctionnalités utilisateur de base. Cette topologie est facultative ; vous pouvez plutôt choisir de déployer un serveur principal unique.

  - **Utilisation d’un serveur Standard Edition au niveau d’un site de succursale.**   Cette organisation considère le site C comme un site de succursale car il ne dispose que de 600 employés. Cependant, les utilisateurs y organisent beaucoup de conférences A/V entre eux. S’il était déployé dans Lync Server comme site de succursale, le support de ces conférences s’exécuterait sur le réseau étendu en direction et en provenance d’un site central disposant d’un serveur frontal. Pour éviter cette charge de bande passante potentielle, ils ont installé sur ce site une paire de serveurs Standard Edition qui hébergeront ces conférences. Et dans la mesure où des serveurs Standard Edition sont installés sur ce site, par définition, Lync Server le considère comme un site central et le traite comme tel dans le Générateur de topologie et l’outil de planification.
    
    Un seul serveur Standard Edition serait suffisant ici du point de vue des performances, mais l’organisation en a déployé deux et les a associés afin de fournir une haute disponibilité en cas de panne de l’un d’entre eux.
    
    Même si le site C est considéré comme un site central, vous n’avez pas besoin d’y déployer des serveurs Edge. Dans cet exemple, le site C utilisera les serveurs Edge déployés sur le site A.

  - **Surveillance et archivage**   Cette organisation a déployé la surveillance et l’archivage. Lorsque vous déployez ces deux fonctionnalités, elles s’exécutent sur chaque serveur frontal. Les bases de données pour ces fonctionnalités peuvent être colocalisées avec la base de données principale ou se trouver sur un serveur distinct. Cette organisation a disposé ces bases de données sur un serveur distinct des serveurs principaux, dans le site central B. Ces bases de données reçoivent les données de surveillance et d’archivage en provenance des serveurs frontaux dans tous les sites.

  - **Options de déploiement de site de succursale.**   Cette organisation dispose en réalité de plus de 50 sites de succursale, dont trois seulement sont indiqués dans les schémas détaillés. Les sites de succursale 1 et 3 ne disposant pas d’une liaison de réseau étendu robuste avec le site central, des serveurs Survivable Branch Appliance ont été déployés pour fournir un service téléphonique en cas de panne de la liaison du réseau étendu avec le site central. Le site de succursale 2 comporte néanmoins une liaison de réseau étendu robuste ; seule une passerelle RTC est donc requise. La passerelle RTC déployée ici prend en charge la déviation du trafic multimédia. Aucun serveur de médiation n’est donc requis sur le site de succursale B. Pour plus d’informations sur le choix des éléments à installer sur un site de succursale, reportez-vous à [Planification de la résistance Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) dans la documentation de planification.

  - **Jonction SIP et serveur de médiation.**   Notez que sur le site central B, le serveur de médiation n’est pas colocalisé avec les serveurs frontaux. En effet, un serveur de médiation autonome est préférable sur les sites qui utilisent une jonction SIP. Dans la plupart des autres cas, nous recommandons de colocaliser le serveur de médiation avec le serveur frontal. Pour plus d’informations sur les topologies de serveur de médiation, reportez-vous à [Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

  - **La conversation permanente est déployée.**   Cette organisation a déployé les serveurs nécessaires pour activer la conversation permanente. Elle a déployé plusieurs serveurs frontaux de conversation permanente afin de gérer la charge pour le nombre d’utilisateurs dans le pool et afin de procurer une haute disponibilité. Elle a également déployé la conformité pour la conversation permanente et colocalisé le magasin de conversation permanente et le magasin de conformité de conversation permanente sur des serveurs distincts. Ces magasins pourraient être colocalisés (et peuvent même être colocalisés avec le serveur principal), mais cette organisation a choisi de les séparer pour des raisons de performances.

  - **Équilibrage de la charge DNS.**   Le pool frontal, le pool de serveur Edge et le pool directeur ont un équilibrage de la charge DNS pour le trafic SIP déployé. Cela vous évite de devoir recourir à des programmes d’équilibrage de la charge matérielle pour l’interface interne des serveurs Edge et cela réduit significativement le temps consacré à leur configuration et maintenance pour les autres pools, étant donné que ces programmes sont requis uniquement pour le trafic HTTP. Pour plus d’informations sur l’équilibrage de charge DNS, reportez-vous à [Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.

  - **Déploiement de la messagerie unifiée Exchange.**   Lync Server fonctionne avec des déploiements *locaux* de la messagerie unifiée Exchange et avec la messagerie unifiée Exchange *hébergée* . Le site central A inclut un serveur de messagerie unifiée Exchange, qui exécute Microsoft Exchange Server, et non Lync Server. La fonctionnalité de messagerie unifiée Exchange pour Lync Server s’exécute sur le pool frontal.
    
    Le site central B utilise la version Exchange hébergée, de sorte que la fonctionnalité du serveur de messagerie unifiée Exchange l’est également.
    
    Pour plus d’informations sur la messagerie unifiée Exchange, reportez-vous à [Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [Intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.

  - **Office Web Apps Server.**   Nous vous recommandons de déployer un serveur Office Web Apps Server ou une batterie Office Web Apps Server dans chaque organisation qui utilise la conférence web. Vous pourriez déployer une batterie Office Web Apps Server unique dans un site qui gère le trafic en provenance de tous les sites ou la déployer dans chaque site. Office Web Apps Server rend possible la présentation de diapositives Powerpoint durant les conférences web. Pour plus d’informations, reportez-vous à [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Des directeurs pourraient être ajoutés.**   Si cette organisation souhaitait augmenter la sécurité contre les attaques par déni de service, elle pourrait également déployer un pool directeur. Un directeur est un rôle serveur distinct et facultatif dans Lync Server qui n’héberge pas de comptes d’utilisateurs et ne fournit aucun service de présence ou de conférence. Il sert de serveur de tronçon suivant interne vers lequel un serveur serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes. Le directeur pré-authentifie les requêtes entrantes et les redirige vers le pool ou le serveur central de l’utilisateur. La pré-authentification au niveau du directeur permet d’ignorer les demandes en provenance de comptes d’utilisateurs inconnus du déploiement. Un directeur aide à isoler les serveurs frontaux du trafic malveillant, tel que les attaques par déni de service. Si le réseau est inondé avec du trafic externe non valide lors d’une attaque de ce genre, le trafic se termine au niveau du directeur.

  - **System Center Operations Manager est déployé.**   Nous vous recommandons de surveiller l’intégrité de votre déploiement Lync Server afin de garantir la disponibilité des services pour les utilisateurs finaux. Vous pouvez surveiller Lync avec le pack d’administration System Center Operations Manager pour Lync, téléchargeable gratuitement depuis le site web de Microsoft. Avec le pack d’administration Lync, vous pouvez obtenir de manière proactive des alertes en temps réel lorsque des problèmes surviennent, exécuter des transactions synthétiques pour tester la fonctionnalité Lync de bout en bout, obtenir des rapports sur la disponibilité des services, et ainsi de suite. Cela vous aide à répondre de manière proactive aux problèmes dans votre déploiement avant que les utilisateurs finaux en aient conscience.
    
    Cette organisation a déployé un serveur System Center Operations Manager sur chaque site central.

