---
title: Configuration requise et autorisations pour la configuration de conférence rendez-vous
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a60fc58e0ec40dadff044257d43629c2f3cb01ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Configuration requise et autorisations pour la configuration de conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-20_

La fonction de conférence rendez-vous est un composant facultatif de la charge de travail des conférences Lync Server 2013. Pour pouvoir configurer une conférence rendez-vous, les composants que vous devez installer peuvent être déployés lorsque vous utilisez le générateur de topologie pour concevoir votre topologie, puis configurer votre pool frontal ou votre serveur Standard Edition. Cette rubrique décrit ce que vous devez faire pour pouvoir configurer les conférences rendez-vous.

Cette section suppose que vous avez lu en particulier les sections de planification relatives à la charge de travail des conférences et aux conférences rendez-vous.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Conditions préalables à la configuration des conférences rendez-vous

Les conférences rendez-vous nécessitent les composants Lync Server 2013 suivants:

  - Service d’application de communications unifiées (UCAS), désigné par *Service d’application*

  - Application Intendant Conférence

  - Application d’annonce de conférence

  - Page web Paramètres de conférence rendez-vous

  - Au moins un serveur de médiation Lync Server 2013 et au moins une passerelle RTC

Vous déployez ces composants lorsque vous utilisez le générateur de topologie pour définir et publier votre topologie, puis déployer un pool frontal ou un serveur Standard Edition Server. Si vous déployez Enterprise Voice, vous devez le déployer avant de configurer la Conférence rendez-vous. Si vous n’êtes pas le déploiement d’Enterprise Voice, vous pouvez déployer un serveur de médiation et une passerelle de réseau téléphonique commuté (PSTN) lors du déploiement de votre pool frontal ou du serveur Standard Edition Server.

<div>


> [!NOTE]
> Si vous effectuez une mise à niveau d’Office Communications Server 2007 R2 vers Lync Server 2013, déployez des conférences rendez-vous dans chaque liste que vous envisagez d’utiliser pour héberger des conférences Lync Server 2013. Pour plus d’informations sur la migration des conférences rendez-vous, voir <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migration d’Office Communications Server 2007 R2 vers Lync Server 2013</A>.



</div>

Cette section part du principe que vous avez réalisé les tâches suivantes:

  - Appliquez les mises à jour les plus récentes de votre environnement Office Communications Server 2007 R2, si vous effectuez une migration vers Lync Server 2013.

  - Utiliser le générateur de topologie pour concevoir et configurer votre topologie. Lorsque vous spécifiez la charge de travail de conférence, vous avez sélectionné l’option Conférence rendez-vous. Pour plus d’informations sur la définition de votre topologie, voir [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) dans la documentation de déploiement.

  - A publié votre topologie et configuré le pool frontal ou un serveur Standard Edition Server. Pour plus d’informations sur la publication de la topologie et l’installation de Lync Server 2013, voir [déploiement de Lync server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.
    
    <div>
    

    > [!NOTE]
    > Lorsque vous installez votre topologie publiée, la page Web des paramètres de conférence rendez-vous est installée sur le serveur frontal ou sur le serveur Standard Edition dans le cadre des services Web.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Si vous modifiez le chemin d’accès du magasin de fichiers dans le générateur de topologie après le déploiement de Lync Server 2013, vous devez redémarrer les applications du surveillant de conférences et de l’annonce de conférence pour utiliser le nouveau chemin.

    
    </div>

  - Voix entreprise déployée. Si vous n’effectuez pas le déploiement d’Enterprise Voice, vous colocalisez un serveur de médiation sur le serveur frontal Enterprise Edition ou le serveur Standard Edition Server, ou vous avez déployé un serveur de médiation autonome et vous avez déployé une passerelle PSTN. Pour plus d’informations sur le déploiement de voix entreprise, reportez-vous à la rubrique [déploiement d’Enterprise Voice dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement. Pour plus d’informations sur l’installation d’un serveur de médiation autonome et d’une passerelle RTC, voir [déploiement de serveurs de médiation et définition d’homologues dans Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) dans la documentation de déploiement.

Le diagramme suivant montre les étapes que vous devez effectuer avant de configurer la Conférence rendez-vous et les étapes que vous devez effectuer pour configurer la Conférence rendez-vous.

**Déploiement de conférences rendez-vous**

![Diagramme de déploiement de la Conférence] rendez-vous (images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagramme de déploiement de la Conférence") rendez-vous

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Autorisations de conférence rendez-vous

Pour configurer des conférences rendez-vous, vous devez utiliser les outils d’administration suivants:

  - Panneau de configuration de Lync Server 2013

  - Lync Server Management Shell

Les outils d’administration suivants vous permettent de configurer les paramètres de conférence rendez-vous, ainsi que les plans de numérotation, les politiques et d’autres paramètres nécessaires à la Conférence rendez-vous.

La configuration de la Conférence rendez-vous nécessite l’un des rôles d’administration suivants, en fonction de la tâche:

  - **CsVoiceAdministrator**   ce rôle d’administrateur peut créer, configurer et gérer les paramètres et les stratégies relatives à la voix.

  - **CsUserAdministrator**   ce rôle d’administrateur peut activer et désactiver des utilisateurs pour Lync Server et affecter des stratégies existantes, telles que les stratégies de conférences et les stratégies de code confidentiel, aux utilisateurs.

  - **CsAdministrator**   ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator et de CsUserAdministrator.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement d’Enterprise Voice dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

