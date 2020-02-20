---
title: 'Lync Server 2013 : déploiement de voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b56065b0e3b7e7ef25c81f20140e8869dbe5376
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Déploiement de voix entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Lync Server 2013, voix entreprise fait partie de l’infrastructure Lync Server 2013.

Le déploiement de Voix Entreprise requiert de vous les opérations suivantes :

<div id="sectionSection0" class="section">

1.  Consultez la section [planification de voix entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) de la documentation de planification.

2.  finaliser les plans pour les fonctionnalités et les composants à déployer avec cette charge de travail ;

3.  Exécutez l’outil de planification pour concevoir une topologie reflétant vos décisions de déploiement.

4.  Ouvrez la conception de la topologie dans le générateur de topologie, comme décrit dans la rubrique [Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) dans la documentation de déploiement.
    
    <div>
    

    > [!NOTE]  
    > L’installation du générateur de topologies fait partie du processus de déploiement du pool interne. Pour plus d’informations, voir <A href="lync-server-2013-install-lync-server-administrative-tools.md">install Lync Server 2013 administrative Tools</A> dans la documentation de déploiement.

    
    </div>

En outre, vous devez déjà avoir déployé Lync Server, Enterprise Edition sur des sites centraux et des sites de succursale qui correspondent à la topologie de référence que vous choisissez de déployer. Vous ne pouvez pas déployer les composants voix entreprise tant que vous n’avez pas défini, publié et installé les fichiers d’au moins un pool interne, et vous devez utiliser le générateur de topologies pour définir et publier un pool interne.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Pour afficher des topologies de référence avec des exemples de déploiement de rôles de serveur voix entreprise (et leur relation entre eux et d’autres rôles serveur Lync Server 2013), voir [Reference topologies in Lync server 2013](lync-server-2013-reference-topologies.md) dans la documentation de planification.

Pour afficher une topologie de référence illustrant et expliquant un exemple de déploiement de contrôle d’admission des appels, notamment les régions réseau, les sites réseau et les sous-réseaux, voir [example : Gathering Your Requirements for Call Admission Control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Pour déployer voix entreprise sur un site central, continuez à lire les rubriques de cette section. Pour déployer voix entreprise sur un site de succursale, passez à la rubrique <A href="lync-server-2013-deploying-branch-sites.md">Deploying Branch sites in Lync Server 2013</A> dans la documentation de déploiement.



</div>

Cette section comprend des procédures pour les déploiements dans lesquels un serveur de médiation est colocalisé sur chaque serveur frontal ou serveur Standard Edition, comme recommandé, ainsi que pour les déploiements avec un pool de serveurs de médiation autonome.

Vous pouvez ignorer le contenu suivant si vous avez utilisé le générateur de topologie pour définir et publier une topologie qui colocalise un serveur de médiation sur chaque serveur frontal ou serveur Standard Edition, car l’Assistant déploiement a déjà installé automatiquement les fichiers pour Serveur de médiation lorsque vous avez installé des fichiers pour votre pool de serveurs frontaux ou votre serveur Standard Edition :

  - [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md)

Si vous avez utilisé le générateur de topologie pour définir et publier un serveur de médiation dans un pool autonome, vous pouvez utiliser le contenu suivant :

  - Vérifiez que votre topologie répond aux conditions préalables logicielles et environnementales, comme décrit dans [Enterprise Voice Prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - <span></span>  
    [Conditions préalables pour voix entreprise pour Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Configuration des plans de numérotation dans Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Exportation et importation de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Tester le routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Déploiement de la messagerie unifiée Exchange locale pour fournir la messagerie vocale Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Fourniture de la messagerie vocale des utilisateurs de Lync Server 2013 sur la messagerie unifiée Exchange hébergée](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Configuration de l’intégration de Lync Server 2013 sur site à Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Déploiement des fonctionnalités avancées de voix entreprise dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [À propos des régions réseau, des sites et des sous-réseaux dans Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Création ou modification d’une région réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Configurer le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Configurer Enhanced 9-1-1 dans Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Configurer la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Activer les utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de sites de succursale dans Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Configuration de la Conférence rendez-vous dans Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Configuration du parcage d’appel dans Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Configuration des annonces pour les numéros non attribués dans Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Déploiement de la surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

