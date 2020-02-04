---
title: Décisions de planification initiale pour Lync Server 2013
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
ms.openlocfilehash: 9c15cfad5da4bab441a56d6f13a79121b6e8d87b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Décisions de planification initiale pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

La première partie du processus de planification consiste à choisir les charges de travail Lync Server et principales fonctionnalités que vous voulez pour votre organisation.

1.  **Avez-vous besoin d’un déploiement local ou en ligne ?**    Lync Server prend en charge les deux scénarios de déploiement. Pour plus d’informations sur la prise de décision, voir [décider du déploiement de Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md), plus haut dans cette section.

2.  **Souhaitez-vous utiliser une topologie physique ou virtualisée ?**    Lync Server prend en charge toutes les charges de travail et rôles de serveur dans les topologies physiques et virtuelles. La capacité de l’utilisateur et l’évolutivité peuvent différer entre les topologies physiques et virtuelles. Pour plus d’informations, voir [exécution de Lync Server 2013 sur des serveurs virtuels](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  **La messagerie ** instantanée et la *présence* sont toujours activées.**    Dans n’importe quel déploiement Lync Server, la messagerie instantanée et la charge de travail de présence sont installés et activés par défaut. Le message instantané permet à vos utilisateurs de communiquer avec des messages texte en temps réel, et leur présence leur permet d’afficher l’état d’autres utilisateurs sur le réseau. Le statut de présence d’un utilisateur fournit des informations pour aider les autres à déterminer s’ils doivent essayer de contacter l’utilisateur, et par conséquent. Pour plus d’informations, reportez-vous à la section [planification des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) dans la documentation de planification.

4.  **Souhaitez-vous déployer n’importe quel mode de conférence ?**    Conferencing est une autre fonctionnalité de base de Lync Server. Plusieurs modes de conférence sont pris en charge. Vous avez le choix entre le déploiement de tous les types de conférences pris en charge ou seulement certains d’entre eux. Les *conférences Web* permettent aux utilisateurs d’afficher un fichier, par exemple, un ensemble de diapositives créé à l’aide d’un programme de présentation graphique Microsoft PowerPoint, présenté. Le *partage d’application* permet aux utilisateurs de partager tout ou partie de leur bureau, en temps réel. Les *conférences A/V*permettent aux utilisateurs d’ajouter de l’audio (et peut-être de la vidéo) à leurs conférences et aux communications d’égal à égal. Les conférences rendez *-* vous permettent aux utilisateurs d’utiliser des téléphones RTC standard pour participer à la partie audio des conférences hébergées au sein de votre organisation. Pour plus d’informations, reportez-vous à la rubrique [planification de conférences dans Lync Server 2013](lync-server-2013-planning-for-conferencing.md) dans la documentation de planification.
    
    Dans Lync Server 2013, si vous déployez des conférences Web, vous devez également prévoir une intégration avec Office Web Apps Server pour activer le partage et l’affichage dans les réunions dans PowerPoint. Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Si vous déployez une conférence A/V, vous devez également surveiller la qualité audio de ces conférences.**    De nombreux facteurs affectent la qualité audio et vidéo des conférences A/V de Lync Server. Grâce à la surveillance, vous pouvez surveiller la qualité de vos appels et conférences. Vous pouvez détecter des problèmes affectant la qualité multimédia et garantir aux utilisateurs la meilleure utilisation de média possible. Pour plus d’informations, reportez-vous à [planification de l’analyse dans Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **Avez-vous besoin d’une haute disponibilité pour vos serveurs de messagerie instantanée, de présence et de conférence ?**    Si vous disposez d’un seul serveur sur un site disposant de fonctionnalités de messagerie instantanée, de présence et de conférence, les conséquences de la productivité de vos utilisateurs seront considérablement affectées en cas de panne. En déployant un *pool* Enterprise Edition d’au moins trois serveurs pour ces fonctions, vous pouvez faire en sorte que Lync Server continue de fonctionner avec toutes ces fonctionnalités intactes, même si un serveur n’est pas disponible.
    
    Une autre option pour les organisations qui utilisent 5000 ou moins de personnes qui veulent disposer d’une forte disponibilité est le déploiement de deux serveurs exécutant Lync Server Standard Edition et associent ces serveurs. Pour plus d’informations, reportez-vous à [planification d’une haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **Souhaitez-vous utiliser les options de récupération d’urgence ?**    Si vous avez deux centres de centres et que vous souhaitez utiliser des options de récupération d’urgence pour permettre aux utilisateurs de continuer à travailler si tous les serveurs d’un centre de tâches sont déplacés vers le bas, vous pouvez déployer vos serveurs en gardant à l’esprit le rétablissement d’urgence. Pour ce déploiement, vous jumelez un pool de serveurs sur un centre de développement et un pool correspondant dans un autre centre de ressources. Si un centre de ressources est en panne, l’autre pool de la paire peut traiter les utilisateurs dans les deux pools avec un minimum d’interruption de service. Pour plus d’informations, reportez-vous à [planification d’une haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **Souhaitez-vous permettre aux utilisateurs de communiquer et de collaborer avec des utilisateurs externes ?**    L’activation de la communication et de la collaboration avec des utilisateurs externes peut augmenter votre retour sur investissement dans Lync Server. Cela permet aux utilisateurs de votre organisation de profiter des fonctionnalités du serveur Lync, même si celles-ci travaillent à l’extérieur de votre organisation. Vous pouvez également fédérer avec votre partenaire ou les organisations de clients qui exécutent Lync Server. En procédant ainsi, vos utilisateurs et partenaires fédérés peuvent facilement envoyer et recevoir des messages INSTANTANÉs, vous inviter les uns aux autres à l’aide des réunions et voir leur présence. De plus, vos utilisateurs peuvent utiliser un message électronique pour inviter des utilisateurs externes spécifiques à des conférences qu’ils organisent. Pour plus d’informations, reportez-vous à [planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **Souhaitez-vous déployer Enterprise Voice ?**     *Enterprise Voice* est la solution VoIP (Voice over IP) fournie par Lync Server. Il offre une alternative attrayante à la téléphonie classique basée sur le PBX. Voix entreprise permet aux utilisateurs de passer des appels depuis leur ordinateur ou leur téléphone VoIP en cliquant sur un contact dans Outlook ou Lync Server. Ils peuvent passer des appels sur le réseau IP entre un ordinateur, un ordinateur ou un téléphone, ou un téléphone à un ordinateur. Les utilisateurs peuvent bénéficier de toutes leurs options de communication (voix, messagerie, messagerie instantanée et conférences) qui sont disponibles et intégrées sur leur ordinateur. Pour plus d’informations, reportez-vous à la rubrique [planification d’entreprise voix dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) dans la documentation de planification.

10. **Si vous déployez Enterprise Voice, vous devez également surveiller la qualité audio de ces appels.**    Nous vous recommandons d’utiliser la surveillance pour garantir la qualité audio de vos appels vocaux d’entreprise, si vous déployez votre voix entreprise. Pour plus d’informations, reportez-vous à [planification de l’analyse dans Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **Avez-vous besoin d’archiver le contenu du message instantané ou le contenu de la réunion à des fins de conformité ?**    Si votre organisation doit archiver le contenu des messages instantanés ou le contenu de la réunion à des fins de conformité, vous pouvez déployer l’archivage. Pour plus d’informations, voir [planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **Voulez-vous déployer une conversation permanente ?**    Pour permettre à vos utilisateurs d’avoir des conversations en temps réel qui peuvent être rendues persistantes dans le temps, vous pouvez déployer la conversation persistante. Pour plus d’informations, reportez-vous à [planification du serveur Chat permanent dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **Avez-vous déployé Microsoft Exchange ?**    Si votre organisation utilise Microsoft Exchange Server pour ses services de messagerie, vous pouvez activer plusieurs fonctionnalités qui améliorent l’utilité de Lync Server et Microsoft Exchange Server. Certaines de ces fonctionnalités, appelées messagerie unifiée Exchange, permettent aux utilisateurs de recevoir des notifications de messagerie vocale et d’écouter la messagerie vocale à partir d’Outlook ou d’Outlook Web Access, d’accéder à leurs boîtes aux lettres Microsoft Exchange via un téléphone et de recevoir des télécopies dans leurs boîtes aux lettres Microsoft Exchange. Par ailleurs, si vous avez déployé Exchange 2013, vous pouvez intégrer les magasins de contacts pour les utilisateurs entre les deux systèmes, utiliser Exchange pour stocker des photos de contact de meilleure résolution et intégrer l’archivage des messages instantanés et des messages instantanés. Pour plus d’informations, reportez-vous à [planification de l’intégration d’Exchange Server avec Lync server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **Avez-vous des succursales au sein de votre organisation ?**    Si votre organisation a des succursales, Lync Server prend en charge différentes manières de les prendre en charge et de garantir leur résilience pour les fonctionnalités vocales et autres. Par exemple, dans une succursale qui ne possède pas de lien WAN fiable vers un centre de données, vous pouvez installer une application de succursales ou un serveur de succursales survivant pour maintenir la prise en charge du réseau étendu. Pour plus d’informations, reportez-vous à la rubrique [planification de la résilience vocale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

