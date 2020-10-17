---
title: Décisions de planification initiale de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fdc9b9e2494078a8db4b524e9ffb6b2794c545d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512571"
---
# <a name="initial-planning-decisions-for-lync-server-2013"></a>Décisions de planification initiale pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

La première partie du processus de planification consiste à choisir les charges de travail Lync Server et les principales fonctionnalités que vous souhaitez pour votre organisation.

1.  **Voulez-vous un déploiement local ou en ligne ?**     Lync Server prend en charge les deux scénarios de déploiement. Pour plus d’informations sur la façon de prendre cette décision, voir la rubrique relative [à la procédure de déploiement de Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md)plus haut dans cette section.

2.  **Voulez-vous une topologie physique ou virtualisée ?**     Lync Server prend en charge toutes les charges de travail et tous les rôles serveur dans les topologies physiques et virtuelles. La capacité utilisateur et l’évolutivité peuvent différer entre les topologies physiques et virtualisées. Pour plus d’informations, reportez-vous à l' [exécution de Lync Server 2013 sur des serveurs virtuels](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  La **messagerie *(IM)* instantanée et la *présence* sont toujours activées.**     Dans tout déploiement Lync Server, la charge de travail de messagerie instantanée et de présence est installée et activée par défaut. La messagerie instantanée permet aux utilisateurs de communiquer par messages texte en temps réel, et la présence de voir le statut des autres utilisateurs sur le réseau. Le statut de présence d’un utilisateur fournit des informations permettant aux autres utilisateurs de décider s’ils doivent essayer de contacter l’utilisateur et par quel moyen. Pour plus d’informations, reportez-vous à la rubrique [planification des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) dans la documentation de planification.

4.  **Voulez-vous déployer les modes de conférence ?**     La Conférence est une autre fonctionnalité essentielle de Lync Server. Plusieurs modes de conférence sont pris en charge. Vous pouvez choisir de déployer tous les types de conférence pris en charge ou seulement certains d’entre eux. La *conférence Web* permet aux utilisateurs de visualiser un fichier, tel qu’un diaporama créé avec le programme de création de graphiques de présentation Microsoft PowerPoint, qui est présenté. Le *partage d’application* permet aux utilisateurs de partager tout ou partie de leur bureau les uns avec les autres en temps réel. Grâce à la *conférence A/V*, les utilisateurs peuvent ajouter de l’audio (et éventuellement de la vidéo) à leurs conférences et communications d’égal à égal. La Conférence rendez *-* vous permet aux utilisateurs d’utiliser des téléphones RTC standard pour rejoindre la partie audio des conférences hébergées dans votre organisation. Pour plus d’informations, reportez-vous à la rubrique [Planning for Conferencing in Lync Server 2013](lync-server-2013-planning-for-conferencing.md) dans la documentation de planification.
    
    Dans Lync Server 2013, si vous déployez la conférence Web, vous devez également planifier l’intégration à Office Web Apps Server pour activer le partage et l’affichage PowerPoint dans les réunions. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Si vous déployez une conférence A/V, vous devez également surveiller la qualité audio de ces conférences.**     De nombreux facteurs influent sur la qualité audio et vidéo des conférences A/V de Lync Server. La surveillance vous permet de contrôler la qualité audio et vidéo de vos appels et conférences. Vous pouvez détecter les problèmes affectant la qualité des médias et garantir la meilleure expérience multimédia possible aux utilisateurs. Pour plus d’informations, reportez-vous à la rubrique [Planning for Monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **Souhaitez-vous disposer d’une haute disponibilité pour vos serveurs de messagerie instantanée, de présence et de conférence ?**     Si vous n’avez qu’un seul serveur au niveau d’un site offrant des fonctionnalités de messagerie instantanée, de présence et de conférence, la productivité de vos utilisateurs sera grandement compromise en cas de panne du serveur. En déployant un *pool* Enterprise Edition d’au moins trois serveurs pour ces fonctions, vous permettez à Lync Server de continuer à fonctionner avec toutes ces fonctionnalités intactes même si un serveur n’est pas disponible.
    
    Une autre option pour les organisations avec 5000 ou moins d’utilisateurs qui souhaitent une haute disponibilité consiste à déployer deux serveurs exécutant Lync Server Standard Edition et à associer ces serveurs ensemble. Pour plus d’informations, reportez-vous à la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **Souhaitez-vous utiliser les options de récupération d’urgence ?**     Si vous disposez de deux centres de centre et que vous souhaitez utiliser les options de récupération d’urgence pour permettre à vos utilisateurs de continuer à travailler si l’ensemble ou un grand nombre de serveurs d’un centre de mise à niveau vers le bas, vous pouvez déployer vos serveurs en tenant compte de la récupération d’urgence. Pour ce déploiement, vous couplez un pool de serveurs d’un centre de données à un pool correspondant dans un autre centre de données. Si un centre de données tombe en panne, le pool de l’autre centre peut desservir les utilisateurs dans les deux pools avec une interruption minimale des services. Pour plus d’informations, reportez-vous à la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **Souhaitez-vous autoriser vos utilisateurs à communiquer et à collaborer avec des utilisateurs externes ?**     L’activation de la communication et de la collaboration avec des utilisateurs externes peut augmenter votre retour sur investissement dans Lync Server. Cela permet aux utilisateurs de votre organisation de tirer parti des fonctionnalités de Lync Server même lorsqu’ils travaillent à l’extérieur des pare-feu de votre organisation. Vous pouvez également fédérer avec vos partenaires ou organisations clientes qui exécutent Lync Server. Ainsi, vos utilisateurs et ceux des partenaires fédérés peuvent facilement échanger des messages instantanés, s’inviter mutuellement à des réunions et voir leur statut de présence. Par ailleurs, vos utilisateurs peuvent envoyer un message électronique pour inviter certains utilisateurs externes aux conférences qu’ils organisent. Pour plus d’informations, reportez-vous à la rubrique [planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **Voulez-vous déployer voix entreprise ?**     *Voix entreprise* est la solution voix sur IP (VoIP) fournie par Lync Server. Elle fournit une alternative intéressante à la téléphonie traditionnelle basée sur le système PBX. Voix entreprise permet aux utilisateurs de passer des appels à partir de leurs ordinateurs ou téléphones VoIP en cliquant sur un contact dans Outlook ou Lync Server. Ils peuvent passer des appels sur le réseau IP d’ordinateur à ordinateur, d’ordinateur à téléphone ou de téléphone à ordinateur. Ils bénéficient de toutes les options de communication disponibles et intégrées sur leurs ordinateurs : par voix, messagerie instantanée et conférence. Pour plus d’informations, reportez-vous à la rubrique [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) dans la documentation de planification.

10. **Si vous déployez voix entreprise, vous devez également surveiller la qualité audio de ces appels.**     Nous vous recommandons d’utiliser la surveillance pour garantir la qualité audio de vos appels vocaux d’entreprise, si vous déployez voix entreprise. Pour plus d’informations, reportez-vous à la rubrique [Planning for Monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. Avez **-vous besoin d’archiver le contenu de messagerie instantanée ou le contenu de réunion à des fins de conformité ?**     Si votre organisation doit archiver le contenu de messagerie instantanée ou le contenu de réunion à des fins de conformité, vous pouvez déployer l’archivage. Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **Voulez-vous déployer la conversation permanente ?**     Si vous souhaitez permettre à vos utilisateurs d’avoir des conversations en temps réel qui peuvent être conservées au fil du temps, vous pouvez déployer une conversation permanente. Pour plus d’informations, reportez-vous à la rubrique [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **Microsoft Exchange est-il déployé ?**     Si votre organisation utilise Microsoft Exchange Server pour ses services de messagerie, vous pouvez activer plusieurs fonctionnalités qui améliorent l’utilité de Lync Server et de Microsoft Exchange Server. Certaines de ces fonctionnalités, appelées messagerie unifiée Exchange, permettent aux utilisateurs de recevoir des messages vocaux et d’écouter des messages vocaux à partir d’Outlook ou d’Outlook Web Access, d’accéder à leurs boîtes aux lettres Microsoft Exchange via un téléphone et de recevoir des télécopies dans leurs boîtes aux lettres Microsoft Exchange. En outre, si Exchange 2013 est déployé, vous pouvez intégrer les magasins de contacts pour les utilisateurs entre les deux systèmes, utiliser Exchange pour stocker des photos de contact de plus haute résolution et intégrer l’archivage des courriers électroniques et des messages instantanés. Pour plus d’informations, reportez-vous à la rubrique [Planning for Exchange Server Integration with Lync Server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **Disposez-vous de succursales dans votre organisation ?**     Si votre organisation possède des succursales, Lync Server prend en charge plusieurs façons de les prendre en charge et de s’assurer de leur résilience pour les fonctionnalités vocales et autres. En particulier, dans une succursale qui n’a pas de liaison de réseau étendu résiliente à un centre de données, vous pouvez installer un Survivable Branch Appliance ou un serveur Survivable Branch Server pour maintenir la prise en charge de voix entreprise si la liaison de réseau étendu (WAN) est interrompue. Pour plus d’informations, reportez-vous à la rubrique [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

