---
title: 'Lync Server 2013 : configuration des serveurs proxy inverses'
description: 'Lync Server 2013 : configuration des serveurs proxy inverses.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8cd5842e4d735637406f6d0fa4f467f1cb8ed03
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549220"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Configuration des serveurs proxy inverses pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-08_

Pour les déploiements de serveur Edge Microsoft Lync Server 2013, un proxy inverse HTTPs dans le réseau de périmètre est nécessaire pour que les clients externes accèdent aux services Web Lync Server 2013 (appelés *composants Web* dans Office Communications Server) sur le directeur et le pool d’accueil de l’utilisateur. Les fonctionnalités qui nécessitent un accès externe via un proxy inverse sont les suivantes :

  - Permettre aux utilisateurs externes de télécharger le contenu de vos réunions

  - Permettre aux utilisateurs externes de développer des groupes de distribution

  - Permettre aux utilisateurs distants de télécharger des fichiers du Service de carnet d’adresses

  - Accès au client Lync Web App.

  - Accès à la page web des paramètres de conférence rendez-vous

  - Permettre aux périphériques externes de se connecter au service web de mise à jour des périphériques et d’obtenir des mises à jour

  - Permettre aux applications mobiles de découvrir et d’utiliser automatiquement les URL de mobilité (MCX) à partir d’Internet.

  - Activation du client Lync 2013, de l’application Lync Windows Store et de Lync 2013 mobile client pour localiser les URL de découverte Lync (découverte automatique) et utiliser UCWA (Unified Communications Web API).

Nous vous recommandons de configurer le proxy inverse HTTP de sorte qu’il publie tous les services web dans tous les pools. Publishing https://ExternalFQDN/ \* publie tous les répertoires virtuels IIS pour un pool. Une règle de publication est nécessaire pour chaque serveur Standard Edition, pool frontal, directeur ou pool directeur dans votre organisation.

En outre, vous devez publier les URL simples. Si l’organisation dispose d’un directeur ou d’un pool directeur, le proxy inverse HTTP écoute les requêtes HTTP/HTTPS vers les URL simples et les redirige via proxy vers le répertoire virtuel externe des services web sur le directeur ou le pool directeur. Si vous n’avez pas déployé de directeur, vous devez désigner un pool pour traiter les requêtes transmises aux URL simples. (S’il ne s’agit pas du pool d’accueil de l’utilisateur, le proxy redirigera ces requêtes vers les services web sur le pool d’accueil de l’utilisateur). Les URL simples peuvent être traitées par une règle de publication web dédiée ou vous pouvez les ajouter aux noms publics de la règle de publication web pour le directeur. Vous devez également publier l’URL du service de découverte automatique externe.

Vous pouvez utiliser Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 ou Internet Information Server 7,0, 7,5 ou 8,0 avec application Routing Routing (IIS ARR) en tant que proxy inverse. Les étapes détaillées de cette section décrivent comment configurer Forefront Threat Management Gateway 2010 et les étapes de configuration d’ISA Server 2006 sont presque identiques. Des conseils sont également fournis pour IIS ARR. Si vous utilisez un proxy inverse différent, consultez la documentation de ce produit et mappez les conditions requises définies ici aux fonctionnalités associées dans d’autres proxys inverses.

<div>


> [!IMPORTANT]  
> Internet Information Server application Request Routing (IIS ARR) est une option entièrement testée et prise en charge pour l’implémentation d’un proxy inverse pour Lync Server 2010 et Lync Server 2013. En novembre 2012, Microsoft a cessé les ventes de licences de ForeFront Threat Management Gateway 2010 ou TMG. TMG reste un produit entièrement pris en charge et est toujours disponible sur les appliances vendues par des tiers. De plus, de nombreux programmes d’équilibrage de la charge matérielle et pare-feu tiers fournissent la prise en charge du proxy inverse. Pour les programmes d’équilibrage de la charge matérielle et les pare-feu qui fournissent des fonctionnalités de proxy inverse, consultez votre fournisseur pour obtenir des instructions spécifiques sur la configuration de son produit afin de fournir une prise en charge de proxy inverse pour Lync Server. Vous pouvez également afficher les tiers qui ont envoyé une documentation pour leur produit à Microsoft. La prise en charge est fournie par le tiers pour leur solution. Pour voir les tiers qui sont actifs dans la fourniture de solutions, voir <A href="https://go.microsoft.com/fwlink/?linkid=268730">infrastructure Qualified for Microsoft Lync</A>.



</div>

Les rubriques et procédures suivantes utilisent Forefront Threat Management Gateway 2010 et IIS ARR comme base pour les procédures de déploiement et de configuration.

  - [Configurer les noms de domaine complets des batteries de serveurs Web pour Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configurer les cartes réseau dans Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Demander et configurer un certificat pour votre proxy HTTP inverse dans Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configurer des règles de publication Web pour un pool interne unique dans Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Vérifier ou configurer l’authentification et la certification sur les répertoires virtuels IIS dans Lync Server 2013](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Créer des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Vérifier l’accès par le biais de votre proxy inverse dans Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Avant de commencer

Pour déployer Forefront Threat Management Gateway 2010 en tant que proxy inverse, vous devez installer et configurer un serveur en vous conformant aux conditions préalables et à la configuration matérielle requise définies dans la documentation de Forefront Threat Management Gateway 2010. Consultez la rubrique suivante pour configurer correctement le matériel et installer Forefront Threat Management Gateway 2010 sur le serveur avant de poursuivre.

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Recommandations matérielles sur Forefront TMG 2010](https://go.microsoft.com/fwlink/?linkid=291293)

Pour déployer IIS ARR comme serveur proxy inverse, consultez les rubriques suivantes pour configurer le matériel et les logiciels prérequis.

  - <span></span>  
    Pour installer les services Internet (IIS) sur Windows Server 2008 ou Windows Server 2008 R2, consultez la rubrique [installation des services Internet (IIS) 7 sur Windows server 2008 ou Windows server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296) .

  - <span></span>  
    Pour installer les services Internet (IIS) sur Windows Server 2012, consultez la rubrique [installation des services Internet (IIS) 8 sur Windows server 2012](https://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Pour installer les services Internet (IIS) sur Windows Server 2012 R2, consultez la rubrique [installation des services Internet (IIS) 8,5 sur Windows server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687) .

  - <span></span>  
    Pour télécharger l’extension de routage des demandes d’applications pour les services Internet (IIS), suivez les instructions de la rubrique [application Request Routing v 2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)

  - <span></span>  
    Pour installer ARR, pour les instructions de la rubrique [install application Request Routing version 2](https://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > Les instructions actuellement validées sont pour ARR 2,0. Pour l’installation de l’extension, il n’existe aucune différence entre les deux versions.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

