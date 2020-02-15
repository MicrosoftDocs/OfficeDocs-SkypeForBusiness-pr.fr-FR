---
title: Conditions préalables et autorisations pour la configuration de la Conférence rendez-vous
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33ac1b54f03463972c49b2e4584f1b9f72d16c03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Conditions préalables et autorisations pour la configuration de la Conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-20_

La Conférence rendez-vous est un composant facultatif de la charge de travail de conférence Lync Server 2013. Les composants que vous devez installer avant de pouvoir configurer la Conférence rendez-vous sont déployés lorsque vous utilisez le générateur de topologies pour concevoir votre topologie, puis configurer votre pool frontal ou votre serveur Standard Edition. Cette rubrique décrit les étapes à accomplir avant de pouvoir configurer la conférence rendez-vous.

Elle suppose que vous avez pris connaissance des sections de planification liées à la charge de travail Conférence et en particulier à la conférence rendez-vous.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Conditions préalables à la configuration de la conférence rendez-vous

La Conférence rendez-vous nécessite les composants Lync Server 2013 suivants :

  - service d’application de communications unifiées (UCAS), désigné par *Service d’application*

  - application Intendant Conférence

  - application d’annonce de conférence

  - page web Paramètres de conférence rendez-vous

  - Au moins un serveur de médiation Lync Server 2013 et au moins une passerelle RTC

Vous déployez ces composants lorsque vous utilisez le générateur de topologie pour définir et publier votre topologie, puis déployer un pool frontal ou un serveur Standard Edition. Si vous déployez voix entreprise, vous devez la déployer avant de configurer la Conférence rendez-vous. Si vous ne déployez pas voix entreprise, vous pouvez déployer un serveur de médiation et une passerelle PSTN (réseau téléphonique commuté) lorsque vous déployez votre pool frontal ou votre serveur Standard Edition.

<div>


> [!NOTE]
> Si vous effectuez une mise à niveau d’Office Communications Server 2007 R2 vers Lync Server 2013, déployez la Conférence rendez-vous dans chaque pool que vous envisagez d’utiliser pour héberger les conférences Lync Server 2013. Pour plus d’informations sur la migration des conférences rendez-vous, consultez la rubrique <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.



</div>

Cette section suppose que vous avez :

  - Application des dernières mises à jour à votre environnement Office Communications Server 2007 R2, si vous effectuez une migration vers Lync Server 2013.

  - Utilisation du générateur de topologies pour concevoir et configurer votre topologie. lors de la spécification de votre charge de travail Conférence, vous avez sélectionné l’option de conférence rendez-vous. Pour plus d’informations sur la définition de votre topologie, reportez-vous à la rubrique [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) dans la documentation de déploiement.

  - publié votre topologie et configuré le pool frontal ou le serveur Standard Edition Server. Pour plus d’informations sur la publication de la topologie et l’installation de Lync Server 2013, voir [Deploying Lync server 2013](lync-server-2013-deploying-lync-server.md) dans la documentation de déploiement.
    
    <div>
    

    > [!NOTE]
    > Lorsque vous installez votre topologie publiée, la page web Paramètres de conférence rendez-vous est installée sur le serveur frontal ou le serveur Standard Edition Server dans le cadre des services web.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Si vous modifiez le chemin d’accès du magasin de fichiers dans le générateur de topologie après avoir déployé Lync Server 2013, vous devez redémarrer les applications de surveillance de conférence et d’annonce de conférence pour utiliser le nouveau chemin d’accès.

    
    </div>

  - Voix entreprise déployée. Si vous ne déployez pas voix entreprise, vous avez colocalisé un serveur de médiation sur le serveur frontal Enterprise Edition ou le serveur Standard Edition, ou vous avez déployé un serveur de médiation autonome et vous avez déployé une passerelle PSTN. Pour plus d’informations sur le déploiement de voix entreprise, reportez-vous à la rubrique [déploiement de voix entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement. Pour plus d’informations sur l’installation d’un serveur de médiation autonome et d’une passerelle PSTN, voir [Deploying Mediation Servers and Defining Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) dans la documentation de déploiement.

Le graphique suivant présente les étapes à effectuer avant de pouvoir configurer la conférence rendez-vous, ainsi que celles permettant de configurer la conférence rendez-vous.

**Déploiement de la conférence rendez-vous**

![Organigramme de déploiement de conférence rendez-vous](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Organigramme de déploiement de conférence rendez-vous")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Autorisations de la conférence rendez-vous

Pour configurer la conférence rendez-vous, vous devez utiliser les outils d’administration suivants :

  - Panneau de configuration Lync Server 2013

  - Lync Server Management Shell

Ces outils permettent de configurer les paramètres de conférence rendez-vous ainsi que les plans de numérotation, les stratégies et les autres paramètres nécessaires à la conférence rendez-vous.

La configuration de la conférence rendez-vous nécessite l’un des rôles administratifs suivants, selon la tâche :

  - **CsVoiceAdministrator**   ce rôle d’administrateur peut créer, configurer et gérer les stratégies et les paramètres liés à la voix.

  - **CsUserAdministrator**   ce rôle d’administrateur permet d’activer et de désactiver des utilisateurs pour Lync Server et d’affecter des stratégies existantes, telles que des stratégies de conférence et des stratégies de code confidentiel, aux utilisateurs.

  - **CsAdministrator**   ce rôle d’administrateur peut effectuer toutes les tâches de CsVoiceAdministrator et de CsUserAdministrator.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de voix entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

