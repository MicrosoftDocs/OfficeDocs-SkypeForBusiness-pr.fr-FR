---
title: 'Lync Server 2013 : définition de la configuration requise pour les conférences'
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
ms.openlocfilehash: ee3b7631a3c05fb497ee7fcdf37b6db984361845
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Définition de la configuration requise pour les conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Lorsque vous déterminez les fonctionnalités de conférence à déployer, vous devez tenir compte des fonctionnalités que vous souhaitez mettre à disposition de vos utilisateurs et des capacités de votre bande passante réseau. La liste de questions suivante va vous guider tout au long du processus de planification du système de conférence afin que vous puissiez déterminer les fonctionnalités de conférence à déployer en fonction des besoins de votre organisation.

  - **Souhaitez-vous activer la conférence web, qui inclut la collaboration sur des documents et le partage d’application ?**
    
    Si c’est le cas, vous devez activer la Conférence pour votre pool frontal dans l’outil de planification de Microsoft Lync Server 2013, ou dans le générateur de topologie. Lorsque vous activez la conférence, vous activez à la fois la conférence web et la conférence A/V.
    
    Le partage d’application requiert et utilise plus de bande passante réseau que la collaboration sur des documents. Lync Server 2013 fournit un mécanisme de limitation pour contrôler chaque session de partage d’application. Par défaut, il est défini à 1,5 Ko/seconde pour chaque session.
    
    Si vous ne souhaitez pas activer le partage d’application, mais que vous voulez autoriser la collaboration sur des documents, vous pouvez activer la conférence et utiliser des stratégies de réunion pour désactiver le partage d’application. Pour plus d’informations sur la configuration des stratégies de réunion, voir [stratégies de conférence dans Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Pour permettre aux utilisateurs de partager des présentations PowerPoint, vous devez configurer Office Web Apps Server. Pour plus d’informations sur la configuration d’Office Web Apps Server, voir Configuration de l' [intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Souhaitez-vous activer la conférence A/V ?**
    
    Si c’est le cas, vous devez activer la Conférence pour votre pool frontal dans l’outil de planification Lync Server 2013 ou dans le générateur de topologies. Lorsque vous activez la conférence, vous activez à la fois la conférence web et la conférence A/V.
    
    La conférence A/V requiert et utilise plus de bande passante réseau que la conférence web (qui inclut la collaboration sur des documents et le partage d’applications). Si vous ne souhaitez pas activer la conférence A/V, mais que vous voulez activer la conférence web, vous pouvez activer la fonctionnalité de conférence et utiliser des stratégies de réunion pour désactiver la conférence A/V.
    
    Si vous souhaitez activer la conférence audio, mais pas la conférence vidéo, vous pouvez activer la conférence A/V et utiliser des stratégies de réunion pour interdire la conférence vidéo. De même, vous pouvez activer la conférence A/V, et autoriser uniquement certains utilisateurs à initier une conférence A/V ou à y prendre part.
    
    <div>
    

    > [!NOTE]  
    > Voix entreprise n’est pas nécessaire pour utiliser la conférence A/V. Si vous activez la conférence A/V, vos utilisateurs peuvent ajouter de l’audio à leurs conférences pourvu qu’ils disposent de périphériques audio, et ce même si vous utilisez un autocommutateur privé (PBX) pour votre solution téléphonique.

    
    </div>

  - **Souhaitez-vous autoriser les utilisateurs à participer à la partie audio des conférences lorsqu’ils utilisent un téléphone PSTN ?**
    
    Dans l’affirmative, déployez et activez la conférence rendez-vous. Les utilisateurs invités, à l’intérieur et à l’extérieur de votre organisation, peuvent alors prendre part à la partie audio des conférences par l’intermédiaire d’un téléphone PSTN.

  - **Voulez-vous autoriser les utilisateurs externes avec des clients Lync Server 2013 à rejoindre les types de conférences que vous avez activés ?**
    
    Si c’est le cas, vous devez déployer des serveurs Edge. En autorisant une participation externe aux réunions, vous optimisez votre investissement dans Lync Server 2013. Par exemple, les utilisateurs disposant d’ordinateurs portables avec Lync Server 2013 peuvent participer à des conférences où qu’ils soient, depuis leur domicile, dans l’aéroport ou sur les sites des clients.
    
    En outre, si les serveurs Edge sont déployés, vous pouvez créer des relations fédérées avec d’autres organisations, afin que les clients ou fournisseurs de ces organisations puissent plus facilement collaborer avec vos utilisateurs.
    
    Pour plus d’informations sur le déploiement des serveurs Edge, reportez-vous à la rubrique [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) et [déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Pour plus d’informations sur l’activation de l’accès externe pour Office Web Apps Server, consultez [la rubrique Publishing Office Web Apps Server in Lync Server 2013 using a reverse Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Souhaitez-vous contrôler les clients qui peuvent rejoindre des réunions Lync Server 2013 ?**
    
    Dans l’affirmative, vous devez configurer la page de participation aux réunions, afin que seules les options clientes que vous souhaitez prendre en charge soient disponibles. Chaque fois qu’un utilisateur clique sur un lien pour participer à une réunion planifiée, Lync Server 2013 détecte si un client est déjà installé sur l’ordinateur. Il démarre alors le client par défaut et ouvre la page de participation à la réunion qui contient des liens vers d’autres clients. La page de participation aux réunions contient toujours l’option d’utilisation de Microsoft Lync Web App. En plus de cette option, vous pouvez décider s’il faut inclure des liens pour les participants et les versions précédentes de Communicator. Pour plus d’informations, reportez-vous à [la rubrique Configuration de la page de participation aux réunions dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration requise pour la conférence Web dans Lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [Configuration requise pour les conférences A/V dans Lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Exigences en matière de conférence rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la Conférence dans Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Liste de vérification du déploiement pour les conférences dans Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

