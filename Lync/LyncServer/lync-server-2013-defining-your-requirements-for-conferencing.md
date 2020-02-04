---
title: 'Lync Server 2013 : Définition de la configuration requise pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Définition de la configuration requise pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Lorsque vous déterminez les fonctions de conférence à déployer, vous devez tenir compte des fonctionnalités que vous souhaitez mettre à disposition de vos utilisateurs et des capacités de votre bande passante réseau. La liste des questions suivante vous guide tout au long du processus de planification des conférences pour déterminer les fonctionnalités de la Conférence que vous devez déployer en fonction de la configuration requise pour votre organisation.

  - **Souhaitez-vous activer la conférence web, qui inclut la collaboration sur des documents et le partage d’application ?**
    
    Si tel est le cas, vous devez activer la Conférence pour votre liste frontale dans Microsoft Lync Server 2013, l’outil de planification ou le générateur de topologie. Lorsque vous activez la fonctionnalité de conférence, vous activez les conférences Web et la Conférence rendez-vous.
    
    Le partage d’application nécessite et utilise plus de bande passante réseau que la collaboration sur des documents. Lync Server 2013 fournit un mécanisme de limitation pour contrôler chaque session de partage d’application. Par défaut, il est défini à 1,5 Ko/seconde pour chaque session.
    
    Si vous ne souhaitez pas activer le partage d’application, mais que vous voulez collaborer sur des documents, vous pouvez activer les conférences et utiliser les stratégies de réunion pour désactiver le partage d’application. Pour plus d’informations sur la configuration des stratégies de réunion, voir [stratégies de conférence dans Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Pour autoriser les utilisateurs à partager des présentations PowerPoint, vous devez configurer Office Web Apps Server. Pour plus d’informations sur la configuration d’Office Web Apps Server, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Souhaitez-vous activer les conférences A/V ?**
    
    Si tel est le cas, vous devez activer les conférences pour votre liste frontale dans l’outil de planification de Lync Server 2013, ou dans le générateur de topologie. Lorsque vous activez la fonctionnalité de conférence, vous activez les conférences Web et la Conférence rendez-vous.
    
    La fonction de conférence A/V nécessite et utilise davantage de bande passante réseau que les conférences Web (notamment la collaboration sur les documents et le partage d’applications). Si vous ne souhaitez pas activer la fonction de conférence A/V mais que vous voulez activer les conférences Web, vous pouvez activer les conférences et utiliser les stratégies de réunion pour désactiver les conférences A/V.
    
    Si vous voulez activer les conférences audio sans visioconférence, vous pouvez activer les conférences A/V et utiliser des stratégies de réunion pour empêcher les visioconférences. De même, vous pouvez activer la conférence A/V et ne permettre qu’à certains utilisateurs de commencer une conférence A/V ou d’y participer.
    
    <div>
    

    > [!NOTE]  
    > Vous n’êtes pas obligé d’utiliser Voix Entreprise pour utiliser la conférence A/V. Si vous activez la conférence A/V, vos utilisateurs peuvent ajouter de l’audio à leurs conférences sous réserve qu’ils disposent de périphériques audio, et ce, même si vous utilisez un autocommutateur privé (PBX) pour votre solution téléphonique.

    
    </div>

  - **Souhaitez-vous permettre aux utilisateurs d’accéder à la partie audio des conférences lors de l’utilisation d’un téléphone RTC ?**
    
    Si c’est le cas, déployez et activez la conférence rendez-vous. Les utilisateurs invités, à l’intérieur et à l’extérieur de votre organisation, peuvent alors participer à la partie audio des conférences par l’intermédiaire d’un téléphone RTC.

  - **Souhaitez-vous autoriser les utilisateurs externes disposant de clients Lync Server 2013 à rejoindre les types de conférences que vous avez activées ?**
    
    Si tel est le cas, vous devez déployer des serveurs Edge. En autorisant la participation externe aux réunions, vous Maximisez votre investissement dans Lync Server 2013. Par exemple, les utilisateurs d’ordinateurs portables dotés de Lync Server 2013 peuvent participer à des conférences où qu’elles se trouvent : chez vous, dans l’aéroport ou sur les sites du client.
    
    De plus, avec les serveurs de périphérie déployés, vous pouvez créer des relations fédérées avec d’autres organisations, telles que vos clients ou fournisseurs, et les utilisateurs de ces organisations pourront plus facilement collaborer avec vos utilisateurs.
    
    Pour plus d’informations sur le déploiement de serveurs Edge, voir [planification d’un accès utilisateur externe dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) et [déploiement d’un accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Pour plus d’informations sur l’activation de l’accès externe pour Office Web Apps Server, voir [publication d’Office Web Apps Server dans Lync server 2013 à l’aide d’un serveur proxy inverse](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Souhaitez-vous contrôler les clients qui peuvent rejoindre des réunions Lync Server 2013 ?**
    
    Si c’est le cas, vous devez configurer la page de participation aux réunions de sorte que seules les options du client à prendre en charge soient disponibles. Chaque fois qu’un utilisateur clique sur un lien pour rejoindre une réunion planifiée, Lync Server 2013 détecte si un client est déjà installé sur l’ordinateur. Il lance alors le client par défaut et ouvre la page de participation à la réunion qui contient des liens vers d’autres clients. La page de participation à une réunion contient toujours l’option d’utilisation de Microsoft Lync Web App. Outre cette option, vous pouvez décider d’inclure ou non des liens vers Participant et les versions précédentes de Communicator. Pour plus d’informations, reportez-vous à [la rubrique Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration requise pour les conférences Web dans Lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [Exigences de conférence A/V dans Lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Configuration requise pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification des conférences dans Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Liste de vérification du déploiement pour les conférences dans Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

