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
ms.openlocfilehash: 91d21526cfcd6d2c78cd67660136e8f7600d1841
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Concepts de conférence courants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-19_

Plusieurs concepts sont communs à tous les types de conférences. Celles-ci sont décrites dans les sections suivantes.

<div>

## <a name="policies-and-bandwidth-management"></a>Stratégies et gestion de la bande passante

Lync Server 2013 permet aux administrateurs de définir des stratégies pour les types de réunions que les utilisateurs peuvent organiser. Cela vous permet d’appliquer les stratégies de votre organisation et de contrôler l’utilisation de la bande passante. Vous pouvez définir une large gamme de stratégies de réunion et les attribuer à des utilisateurs et des groupes d’utilisateurs individuels. Vous pouvez également définir des stratégies régissant les conversations P2P. Pour plus d’informations sur la configuration des stratégies de conférence, voir [stratégies de conférence dans Lync Server 2013](lync-server-2013-conferencing-policies.md) dans la documentation opérations. Pour plus d’informations sur la gestion de la bande passante, voir [vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) et [configuration de la bande passante vidéo dans Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Fonctionnalités d’archivage et de conformité

Lync Server 2013 fournit des fonctionnalités que vous pouvez utiliser si votre organisation doit respecter les règles de conformité. Vous pouvez utiliser les capacités d’archivage pour archiver du contenu présenté dans les réunions, ainsi que le contenu des conversations par messagerie instantanée et des conférences de messagerie instantanée. Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification. Vous pouvez utiliser les fonctionnalités de conformité du serveur de chat permanent pour archiver des conversations basées sur des sujets qui persistent dans le temps. Pour plus d’informations, reportez-vous à [planification du serveur de conversation persistant dans Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) dans la documentation de planification.

</div>

<div>

## <a name="monitoring-feature"></a>Fonctionnalité de surveillance

La fonctionnalité analyse du serveur peut capturer les enregistrements des détails des appels (CdR), que vous pouvez utiliser pour effectuer le suivi des utilisateurs qui parlent d’autres utilisateurs à l’aide de Lync Server 2013. Pour plus d’informations sur le déploiement et la configuration de la surveillance, voir [déploiement de l’analyse dans Lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Activation de la participation externe aux conférences

Vous pouvez considérablement augmenter les avantages de votre investissement dans les conférences Lync Server 2013 en permettant aux utilisateurs externes de participer également à des conférences lors de leur invitation. Exemples d’utilisateurs externes :

  - **Utilisateurs distants**   les utilisateurs de votre organisation qui travaillent à l’extérieur de votre pare-feu et qui utilisent leur ordinateur portable ou d’autres appareils Lync Server 2013.

  - **Utilisateurs fédérés utilisateurs**   de sociétés qui travaillent également sur Lync Server 2013. Pour autoriser vos utilisateurs à communiquer facilement avec ces utilisateurs externes, créez des relations fédérées avec ces entreprises.

  - **Utilisateurs anonymes**   tout autre utilisateur externe invité spécifiquement par vos utilisateurs à rejoindre des conférences spécifiques. Un organisateur de réunion qui appartient à votre entreprise peut envoyer à un utilisateur externe, par courrier électronique, une invitation à participer à une conférence. Le courrier électronique inclut un lien sur lequel l’utilisateur externe peut cliquer pour participer à la conférence.

Pour activer tout ou partie de ces scénarios, vous devez déployer un serveur Edge pour sécuriser les communications entre votre déploiement Lync Server 2013 et les utilisateurs externes. La solution Lync Server 2013 qui utilise des serveurs Edge fournit des médias de meilleure qualité que d’autres solutions, telles qu’un réseau privé virtuel (VPN). Pour plus d’informations, reportez-vous à la [planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Par ailleurs, si vous déployez des serveurs de périphérie, vous pouvez permettre aux utilisateurs (à l’intérieur ou à l’extérieur de votre organisation) de se connecter à partir de téléphones RTC standard pour participer à des conférences audio locales. Pour ce faire, il suffit de déployer la Conférence rendez-vous Lync Server 2013.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Compatibilité entre les types de réunion et les versions de client

Si vous envisagez d’utiliser Lync Server 2013 avec des versions antérieures d’Office Communications Server et de ses clients, vous devez tenir compte des éléments suivants :

  - Les utilisateurs de Lync Server 2013 ne peuvent pas planifier de conférences en temps réel, ni modifier une réunion migrée de ce type.

  - Les utilisateurs de Lync Server 2013 qui doivent participer à des conférences Live Meeting hébergées sur des serveurs exécutant Office Communications Server 2007 R2 doivent avoir installé le client Live Meeting sur leur ordinateur (en plus de Lync Server 2013) pour participer à ces réunions.

  - Lors de la migration de conférences Live Meeting vers Lync Server 2013, le contenu de la réunion n’est pas migré. Si vous avez besoin de ce contenu, vous devez le télécharger à nouveau.

</div>

</div>

<span> </span>

</div>

</div>

</div>

