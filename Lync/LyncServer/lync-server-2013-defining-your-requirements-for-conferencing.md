---
title: 'Lync Server 2013 : Définition de la configuration requise pour les conférences'
TOCTitle: Définition de la configuration requise pour les conférences
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204935(v=OCS.15)
ms:contentKeyID: 49297341
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour les conférences dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-30_

Lorsque vous déterminez les fonctionnalités de conférence à déployer, vous devez tenir compte des fonctionnalités que vous souhaitez mettre à disposition de vos utilisateurs et des capacités de votre bande passante réseau. La liste de questions suivante va vous guider tout au long du processus de planification du système de conférence afin que vous puissiez déterminer les fonctionnalités de conférence à déployer en fonction des besoins de votre organisation.

  - **Souhaitez-vous activer la conférence web, qui inclut la collaboration sur des documents et le partage d’application ?**
    
    Dans l’affirmative, vous devez activer la conférence pour votre pool de serveurs frontaux dans l’outil de planification Microsoft Lync Server 2013 ou dans le Générateur de topologie. Lorsque vous activez la conférence, vous activez à la fois la conférence web et la conférence A/V.
    
    Le partage d’application requiert et utilise plus de bande passante réseau que la collaboration sur des documents. Lync Server 2013 fournit un mécanisme de limitation qui permet de contrôler chaque session de partage d’application. Par défaut, il est défini à 1,5 Ko/seconde pour chaque session.
    
    Si vous ne souhaitez pas activer le partage d’application, mais que vous voulez autoriser la collaboration sur des documents, vous pouvez activer la conférence et utiliser des stratégies de réunion pour désactiver le partage d’application. Pour plus d’informations sur la configuration de stratégies de réunion, reportez-vous à [Stratégies de conférence dans Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Pour permettre aux utilisateurs de partager des présentations PowerPoint, vous devez configurer Office Web Apps Server. Pour plus d’informations sur la configuration de Office Web Apps Server, reportez-vous à [Configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Souhaitez-vous activer la conférence A/V ?**
    
    Dans l’affirmative, vous devez activer la conférence pour votre pool de serveurs frontaux dans l’outil de planification Lync Server 2013 ou dans le Générateur de topologie. Lorsque vous activez la conférence, vous activez à la fois la conférence web et la conférence A/V.
    
    La conférence A/V requiert et utilise plus de bande passante réseau que la conférence web (qui inclut la collaboration sur des documents et le partage d’applications). Si vous ne souhaitez pas activer la conférence A/V, mais que vous voulez activer la conférence web, vous pouvez activer la fonctionnalité de conférence et utiliser des stratégies de réunion pour désactiver la conférence A/V.
    
    Si vous souhaitez activer la conférence audio, mais pas la conférence vidéo, vous pouvez activer la conférence A/V et utiliser des stratégies de réunion pour interdire la conférence vidéo. De même, vous pouvez activer la conférence A/V, et autoriser uniquement certains utilisateurs à initier une conférence A/V ou à y prendre part.
    
    > [!NOTE]  
    > Vous n’êtes pas obligé d’utiliser Voix Entreprise pour utiliser la conférence A/V. Si vous activez la conférence A/V, vos utilisateurs peuvent ajouter de l’audio à leurs conférences pourvu qu’ils disposent de périphériques audio, et ce même si vous utilisez un autocommutateur privé (PBX) pour votre solution téléphonique.

  - **Souhaitez-vous autoriser les utilisateurs à participer à la partie audio des conférences lorsqu’ils utilisent un téléphone RTC ?**
    
    Dans l’affirmative, déployez et activez la conférence rendez-vous. Les utilisateurs invités, à l’intérieur et à l’extérieur de votre organisation, peuvent alors prendre part à la partie audio des conférences par l’intermédiaire d’un téléphone RTC.

  - **Souhaitez-vous autoriser les utilisateurs externes dotés de clients Lync Server 2013 à participer aux types de conférences que vous avez activés ?**
    
    Dans ce cas, vous devez déployer les serveurs Edge. En autorisant la participation externe aux réunions, vous optimisez votre investissement dans Lync Server 2013. Par exemple, les utilisateurs disposant d’ordinateurs portables équipés de Lync Server 2013 peuvent rejoindre une conférence, où qu’ils soient (chez eux, à l’aéroport ou chez un client).
    
    En outre, si les serveurs Edge sont déployés, vous pouvez créer des relations fédérées avec d’autres organisations afin que les clients ou fournisseurs de ces organisations puissent plus facilement collaborer avec vos utilisateurs.
    
    Pour plus d’informations sur le déploiement de serveurs Edge, reportez-vous à [Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) et [Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Pour plus d’informations sur l’activation de l’accès externe pour Office Web Apps Server, reportez-vous à [Publication d’Office Web Apps Server dans Lync Server 2013 avec un serveur proxy inverse](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Souhaitez contrôler les clients pouvant participer à des réunions Lync Server 2013 ?**
    
    Dans l’affirmative, vous devez configurer la page de participation aux réunions afin que seules les options clientes que vous souhaitez prendre en charge soient disponibles. Chaque fois qu’un utilisateur clique sur un lien pour participer à une réunion planifiée, Lync Server 2013 détecte si un client est déjà installé sur l’ordinateur. Il démarre alors le client par défaut et ouvre la page de participation à la réunion qui contient des liens vers d’autres clients. La page de participation à la réunion offre toujours la possibilité d’utiliser Microsoft Lync Web App. En plus de cette option, vous pouvez décider d’inclure ou non des liens vers Participant et les versions précédentes de Communicator. Pour plus d’informations, reportez-vous à [Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

## Dans cette section

  - [Configuration requise pour les fonctions de conférence web](lync-server-2013-web-conferencing-requirements.md)

  - [Configuration requise pour la conférence A/V](lync-server-2013-a-v-conferencing-requirements.md)

  - [Configuration requise pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

## Voir aussi

#### Autres ressources

[Planification des conférences dans Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Liste de vérification du déploiement pour les conférences dans Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

