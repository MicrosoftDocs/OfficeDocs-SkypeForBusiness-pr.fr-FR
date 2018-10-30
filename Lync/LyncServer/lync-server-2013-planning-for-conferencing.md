---
title: 'Lync Server 2013 : Planification des conférences'
TOCTitle: Planification des conférences
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398781(v=OCS.15)
ms:contentKeyID: 49298229
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification des conférences dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-01-29_

Lync Server 2013 offre un large éventail de fonctionnalités de conférence :

  - Conférence web, qui comprend la collaboration sur des documents, le partage d’application et le partage de bureau. Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et l’affichage des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, reportez-vous à [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Conférence audio/vidéo (A/V), qui permet aux utilisateurs de participer à des conférences audio ou vidéo en temps réel sans avoir besoin de recourir à des services externes, tels que Microsoft Live Meeting ou un pont audio tiers.

  - Conférence rendez-vous, qui permet aux utilisateurs de participer à la partie audio d’une conférence Lync Server 2013 en utilisant un téléphone du réseau téléphonique commuté (RTC) sans faire appel à un fournisseur de services d’audioconférence tiers.

  - Conférence par messagerie instantanée, au cours de laquelle au moins deux parties communiquent lors d’une session de messagerie instantanée unique. Pour plus d’informations sur la conférence par messagerie instantanée, reportez-vous à [Planification des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)

Lync Server 2013 prend en charge les conférences planifiées et les conférences improvisées.

Lorsque vous déployez le serveur frontalLync Server 2013, vous avez également la possibilité de déployer les fonctionnalités de conférence web, conférence A/V et conférence rendez-vous. Les fonctionnalités de conférence par messagerie instantanée sont systématiquement et automatiquement déployées avec les fonctionnalités de messagerie instantanée sur les serveurs frontauxLync Server 2013.

> [!NOTE]  
> Si votre déploiement comprend des réunions organisées à l’aide de clients Office Communicator 2007 R2 (y compris la console Live Meeting ou le complément de conférence pour Microsoft Office Outlook), ces réunions présenteront les limitations suivantes après une migration vers Lync Server 2013 :
> <ul>
> <li><p>Les utilisateurs de la réunion ne pourront pas utiliser les fonctionnalités de collaboration de données, y compris la collaboration de document, le partage d’application et le partage de bureau.</p></li>
> <li><p>Des problèmes de stabilité peuvent survenir car les clients Office Communicator 2007 R2 ne sont pas pris en charge avec Lync Server 2013.</p></li></ul>
> Pour éviter ces problèmes, replanifiez toute réunion organisée à l’aide de clients Office Communicator 2007 R2 avec Outlook 2010 ou Outlook 2013 à l’aide du complément de réunion en ligne pour Lync 2010 ou du complément de réunion en ligne pour Lync 2013.


Les sections suivantes décrivent les éléments nécessaires au déploiement des divers types de fonctionnalités de conférence, dont le processus de planification, les composants, la configuration matérielle et logicielle, ainsi que le processus de déploiement.

## Dans cette section

  - [Vue d’ensemble des conférences dans Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Définition de la configuration requise pour les conférences dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Composants et topologies utilisés pour les conférences dans Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Configuration technique requise pour les conférences dans Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Liste de vérification du déploiement pour les conférences dans Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Prise en charge des réunions importantes dans Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

