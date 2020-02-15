---
title: 'Lync Server 2013 : concepts communs aux conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 546e350dc78883ac56623a23f9153d5bdfd4a1d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Concepts communs de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-19_

Plusieurs concepts sont communs à tous les types de conférences. Ces concepts sont décrits dans les sections suivantes.

<div>

## <a name="policies-and-bandwidth-management"></a>Gestion des stratégies et de la bande passante

Lync Server 2013 permet aux administrateurs de définir des stratégies pour les types de réunions que les utilisateurs peuvent organiser. Ceci vous aide à appliquer les stratégies de votre organisation et à contrôler l’utilisation de la bande passante. Vous pouvez définir un grand nombre de stratégies de réunion et les assigner à des utilisateurs et groupes d’utilisateurs spécifiques. Vous pouvez également définir des stratégies régissant les conversations d’égal à égal. Pour plus d’informations sur la définition des stratégies de conférence, voir [stratégies de conférence dans Lync Server 2013](lync-server-2013-conferencing-policies.md) dans la documentation des opérations. Pour plus d’informations sur la gestion de la bande passante, voir [vue d’ensemble du contrôle d’admission des appels dans Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) et [configuration de la bande passante vidéo dans Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Fonctionnalités d’archivage et de conformité

Lync Server 2013 fournit des fonctionnalités que vous pouvez utiliser si votre organisation doit respecter les réglementations en matière de conformité. Vous pouvez utiliser les fonctionnalités d’archivage pour archiver le contenu présenté lors des réunions, mais aussi le contenu des conversations de messagerie instantanée et des conférences de messagerie instantanée. Pour plus d’informations, reportez-vous à la rubrique [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification. Vous pouvez utiliser les fonctionnalités de conformité de serveur de conversations permanentes pour archiver des conversations à plusieurs, basées sur des sujets et conservées avec le temps. Pour plus d’informations, reportez-vous à la rubrique [Planning for persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

</div>

<div>

## <a name="monitoring-feature"></a>Fonctionnalité de surveillance

La fonctionnalité de serveur de surveillance peut capturer des enregistrements des détails des appels (CdR), que vous pouvez utiliser pour identifier les utilisateurs qui discutent avec les autres utilisateurs de Lync Server 2013. Pour plus d’informations sur le déploiement et la configuration de la surveillance, voir [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Activation de la participation externe aux conférences

Vous pouvez grandement augmenter les avantages de votre investissement dans la Conférence Lync Server 2013 en permettant aux utilisateurs externes de participer également à des conférences lorsqu’ils sont invités. Les utilisateurs externes peuvent inclure les catégories suivantes :

  - **Utilisateurs distants**   les utilisateurs de votre organisation, lorsqu’ils travaillent à l’extérieur de vos pare-feu et qu’ils utilisent leur ordinateur portable ou d’autres appareils Lync Server 2013.

  - **Utilisateurs fédérés**   les utilisateurs de sociétés avec qui exécutent également Lync Server 2013. Pour autoriser vos utilisateurs à contacter facilement ces utilisateurs, créez des relations fédérées avec ces entreprises.

  - **Utilisateurs anonymes**   tous les autres utilisateurs externes qui sont invités spécifiquement par vos utilisateurs à participer à des conférences spécifiques. Un organisateur de réunion qui appartient à votre entreprise peut envoyer à un utilisateur externe, par courrier électronique, une invitation à participer à une conférence. Le courrier électronique inclut un lien sur lequel l’utilisateur externe peut cliquer pour prendre part à la conférence.

Pour activer un ou l’ensemble de ces scénarios, vous devez déployer un serveur Edge pour permettre la sécurisation des communications entre votre déploiement Lync Server 2013 et les utilisateurs externes. La solution Lync Server 2013 utilisant des serveurs Edge offre un média de meilleure qualité que d’autres solutions, telles qu’un réseau privé virtuel (VPN). Pour plus d’informations, consultez la rubrique [planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

En outre, que vous choisissiez de déployer ou non des serveurs Edge, vous pouvez autoriser les utilisateurs (dans ou en dehors de votre organisation) à composer un numéro à partir de téléphones PSTN standard, afin de prendre part aux audioconférences sur site. Pour ce faire, vous déployez la Conférence rendez-vous Lync Server 2013.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Compatibilité entre les types de réunions et les versions des clients

Si vous envisagez d’interagir avec Lync Server 2013 avec des versions antérieures d’Office Communications Server et de ses clients, vous devez avoir conscience des problèmes suivants :

  - Les utilisateurs de Lync Server 2013 ne peuvent pas planifier de conférences Live Meeting ni modifier les réunions migrées de ce type.

  - Les utilisateurs de Lync Server 2013 qui doivent participer à des conférences Live Meeting hébergées sur des serveurs exécutant Office Communications Server 2007 R2 doivent disposer du client Live Meeting installé sur leur ordinateur (en plus de Lync Server 2013) pour participer à ces réunions.

  - Lorsque les conférences Live Meeting sont migrées vers Lync Server 2013, le contenu de réunion n’est pas migré. Si ce contenu est requis, il doit de nouveau être téléchargé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

