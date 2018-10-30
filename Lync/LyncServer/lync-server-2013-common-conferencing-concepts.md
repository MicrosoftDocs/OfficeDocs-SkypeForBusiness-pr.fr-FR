---
title: Concepts communs relatifs aux conférences dans Lync Server 2013
TOCTitle: Concepts communs relatifs aux conférences dans Lync Server 2013
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49891476
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Concepts communs relatifs aux conférences dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-19_

Plusieurs concepts sont communs à tous les types de conférences. Ces concepts sont décrits dans les sections suivantes.

## Gestion des stratégies et de la bande passante

Lync Server 2013 permet aux administrateurs de définir des stratégies pour les types de réunions que les utilisateurs peuvent organiser. Ceci vous aide à appliquer les stratégies de votre organisation et à contrôler l’utilisation de la bande passante. Vous pouvez définir un grand nombre de stratégies de réunion et les assigner à des utilisateurs et groupes d’utilisateurs spécifiques. Vous pouvez également définir des stratégies régissant les conversations d’égal à égal. Pour plus d’informations sur la définition de stratégies de conférence, voir [Stratégies de conférence dans Lync Server 2013](lync-server-2013-conferencing-policies.md) dans la documentation des opérations. Pour plus d’informations sur la gestion de la bande passante, voir [Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) et [Configuration de la bande passante vidéo dans Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

## Fonctionnalités d’archivage et de conformité

Lync Server 2013 offre des fonctionnalités dont vous pouvez tirer parti si votre organisation doit respecter des réglementations en matière de conformité. Vous pouvez utiliser les fonctionnalités d’archivage pour archiver le contenu présenté lors des réunions, mais aussi le contenu des conversations de messagerie instantanée et des conférences de messagerie instantanée. Pour plus d’informations, voir [Planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification. Vous pouvez utiliser les fonctionnalités de conformité de serveur de conversations permanentes pour archiver des conversations à plusieurs, basées sur des sujets et conservées avec le temps. Pour plus d’informations, voir [Planification du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

## Fonctionnalité de surveillance

La fonctionnalité de serveur de surveillance peut capturer des enregistrements de détails des appels, que vous pouvez utiliser pour savoir quels utilisateurs appellent quels autres utilisateurs à l’aide de Lync Server 2013. Pour plus d’informations sur le déploiement et la configuration de la surveillance, voir [Déploiement du serveur de surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md).

## Activation de la participation externe aux conférences

Vous pouvez fortement accroître les bénéfices de votre investissement dans un système de conférence Lync Server 2013 en permettant aux utilisateurs externes de participer également aux conférences lorsqu’ils y sont invités. Les utilisateurs externes peuvent inclure les catégories suivantes :

  - **Utilisateurs distants**   Utilisateurs appartenant à votre organisation, lorsqu’ils se trouvent en dehors de vos pare-feu et qu’ils utilisent leur ordinateur portable ou d’autres périphériques Lync Server 2013.

  - **Utilisateurs fédérés**   Utilisateurs appartenant aux entreprises avec lesquelles vous travaillez et qui exécutent aussi Lync Server 2013. Pour autoriser vos utilisateurs à contacter facilement ces utilisateurs, créez des relations fédérées avec ces entreprises.

  - **Utilisateurs anonymes**   Tous les autres utilisateurs externes qui sont invités par vos utilisateurs à participer à des conférences spécifiques. Un organisateur de réunion qui appartient à votre entreprise peut envoyer à un utilisateur externe, par courrier électronique, une invitation à participer à une conférence. Le courrier électronique inclut un lien sur lequel l’utilisateur externe peut cliquer pour prendre part à la conférence.

Pour activer un ou plusieurs de ces scénarios, vous devez déployer un serveur Edge pour aider à sécuriser les communications entre votre déploiement de Lync Server 2013 et les utilisateurs externes. La solution Lync Server 2013 faisant appel à des serveurs Edge fournit un trafic multimédia de meilleure qualité que les autres solutions telles que les réseaux privés virtuels (VPN). Pour plus d’informations, voir [Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

En outre, que vous choisissiez de déployer ou non des serveurs Edge, vous pouvez autoriser les utilisateurs (dans ou en dehors de votre organisation) à composer un numéro à partir de téléphones PSTN standard, afin de prendre part aux audioconférences sur site. Cette opération s’effectue en déployant la fonctionnalité de conférence rendez-vous de Lync Server 2013.

## Compatibilité entre les types de réunions et les versions des clients

S’il est prévu que Lync Server 2013 interopère avec des versions précédentes d’Office Communications Server et ses clients, vous devez prendre connaissance des points suivants :

  - Les utilisateurs de Lync Server 2013 ne peuvent pas planifier de conférences Live Meeting, ni modifier de réunions migrées de ce type.

  - Les utilisateurs de Lync Server 2013 qui doivent participer à des conférences Live Meeting hébergées sur des serveurs exécutant Office Communications Server 2007 R2 doivent installer le client Live Meeting sur leur ordinateur (en plus de Lync Server 2013) pour pouvoir participer à ces réunions.

  - Lorsque des conférences Live Meeting sont migrées vers Lync Server 2013, le contenu des réunions n’est pas migré. Si ce contenu est requis, il doit de nouveau être téléchargé.

