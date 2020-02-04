---
title: 'Lync Server 2013 : Configuration des serveurs proxy inverses'
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
ms.openlocfilehash: fbc6e0aee918d08f47c6df88f91493cd62ae6a3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Configuration des serveurs proxy inverses pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-08_

Pour les déploiements de serveur Edge Microsoft Lync Server 2013, un proxy HTTPs inverse dans le réseau de périmètre est requis pour que les clients externes accèdent aux services Web de Lync Server 2013 (appelés *composants Web* dans Office Communications Server) sur le directeur et sur le pool d’hébergement de l’utilisateur. Certaines des fonctionnalités qui nécessitent un accès externe via un proxy inverse sont les suivantes :

  - Permettre aux utilisateurs externes de télécharger le contenu de la réunion pour vos réunions.

  - Permettre aux utilisateurs externes d’étendre les groupes de distribution.

  - Permettre aux utilisateurs distants de télécharger des fichiers à partir du service de carnet d’adresses.

  - Accès au client Lync Web App.

  - Accès à la page Web des paramètres de conférence rendez-vous.

  - Permettre aux périphériques externes de se connecter au service Web de mise à jour de l’appareil et d’obtenir les mises à jour.

  - Activation des applications mobiles pour détecter et utiliser automatiquement les URL de mobilité (MCX) sur Internet.

  - Activation du client Lync 2013, de l’application Lync du Windows Store et du client mobile Lync 2013 pour trouver les URL de découverte et d’utilisation de l’API Web de communications unifiées (UCWA).

Nous vous recommandons de configurer votre proxy HTTP inverse pour publier tous les services Web dans tous les groupes. Publication de https://ExternalFQDN\* /publie tous les répertoires virtuels IIS d’un pool. Vous avez besoin d’une seule règle de publication pour chaque serveur Standard Edition, pool frontal ou pool ou pool de réalisateur au sein de votre organisation.

Par ailleurs, vous devez publier les URL simples. Si votre organisation dispose d’un directeur ou d’un pool de directeurs, le proxy HTTP inverse écoute les requêtes HTTP/HTTPs aux URL simples et aux proxys vers le répertoire virtuel des services Web externes du réalisateur ou du pool de réalisateurs. Si vous n’avez pas déployé de réalisateur, vous devez désigner un pool pour gérer les requêtes aux URL simples. (S’il ne s’agit pas de la liste de ressources partagées de l’utilisateur, celui-ci est redirigé vers les services Web sur le pool de ressources de l’utilisateur). Les URL simples peuvent être gérées par une règle de publication Web dédiée ou ajoutées au nom public de la règle de publication Web pour le directeur. Vous devez également publier l’URL du service de découverte automatique externe.

Vous pouvez utiliser Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1 ou Internet Information Server 7,0, 7,5 ou 8,0 avec le routage de requête d’application (IIS ARR) en tant que proxy inverse. Les étapes décrites dans cette section décrivent la configuration de la passerelle de gestion des menaces de gestion de la 2010 et les étapes de configuration d’ISA Server 2006 sont presque identiques. Des instructions sont également fournies pour IIS ARR. Si vous utilisez un proxy inverse différent, consultez la documentation de ce produit et mappez les exigences définies ici aux fonctionnalités associées dans d’autres proxys inverse.

<div>


> [!IMPORTANT]  
> Le routage de requête d’application Internet Information Server (IIS ARR) est une option entièrement testée et prise en charge permettant d’implémenter un proxy inverse pour Lync Server 2010 et Lync Server 2013. En novembre, 2012, Microsoft a cessé de gérer les licences de ForeFront Threat Management Gateway 2010 ou TMG. TMG est toujours un produit entièrement pris en charge et est toujours disponible à la vente sur des appareils vendus par des tiers. De plus, de nombreux équilibreurs de charge matérielle tiers et de pare-feu fournissent la prise en charge du proxy inverse. Pour les dispositifs d’équilibrage de charge matérielle et de pare-feu qui fournissent des fonctionnalités de proxy inverse, contactez votre fabricant pour obtenir des instructions spécifiques sur la configuration de ses produits pour la prise en charge du proxy inverse de Lync Server. Vous pouvez également afficher des parties tierces ayant soumis une documentation pour leur produit à Microsoft. La prise en charge est assurée par le tiers pour sa solution. Pour voir d’autres parties actives dans la fourniture de solutions, voir <A href="http://go.microsoft.com/fwlink/?linkid=268730">infrastructure Qualified pour Microsoft Lync</A>.



</div>

Les rubriques et procédures suivantes utilisent Forefront Threat Management Gateway 2010 et IIS ARR comme base pour les procédures de déploiement et de configuration.

  - [Configuration des noms de domaine complets d’une batterie de serveurs web pour Lync Server 2013](lync-server-2013-configure-web-farm-fqdns.md)

  - [Configuration des cartes réseau dans Lync Server 2013](lync-server-2013-configure-network-adapters.md)

  - [Demande et configuration d’un certificat pour votre proxy HTTP inverse dans Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Configuration des règles de publication web pour un pool interne unique dans Lync Server 2013](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Connexion d’un Survivable Branch Appliance à un pool de serveurs frontaux](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Création des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Vérification de l’accès avec le proxy inverse dans Lync Server 2013](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>Avant de commencer

Pour réussir le déploiement de Forefront Threat Management Gateway 2010 en tant que proxy inverse, vous devez configurer et configurer un serveur en utilisant la configuration requise et la configuration matérielle requise définie dans la documentation de la 2010 passerelle de gestion des menaces de Forefront. Pour plus d’informations, reportez-vous à la rubrique suivante configurée pour configurer correctement le matériel et installer la passerelle 2010 de Forefront Threat Management sur le serveur.

  - <span></span>  
    [Passerelle de gestion des menaces de Forefront (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Recommandations en matière de matériel de Forefront TMG 2010](http://go.microsoft.com/fwlink/?linkid=291293)

Pour déployer correctement IIS ARR en tant que proxy inverse, consultez les rubriques suivantes pour configurer le matériel et les logiciels requis.

  - <span></span>  
    Pour installer IIS sur Windows Server 2008 ou Windows Server 2008 R2, voir [installer IIS 7 sur Windows server 2008 ou Windows server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296) .

  - <span></span>  
    Pour installer IIS sur Windows Server 2012, voir [installer IIS 8 sur Windows server 2012](http://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    Pour installer IIS sur Windows Server 2012 R2, voir [installer iis 8,5 sur Windows server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687) .

  - <span></span>  
    Pour télécharger l’extension de routage de requête d’application pour les services Internet (IIS), suivez les instructions de téléchargement de l’application requête de routage [v 2,5](http://go.microsoft.com/fwlink/?linkid=291298) .

  - <span></span>  
    Pour installer l’application ARR, pour les instructions de la procédure d’installation de l' [application demande de routage version 2](http://go.microsoft.com/fwlink/?linkid=291299)
    
    <div>
    

    > [!NOTE]  
    > Les instructions actuellement publiées sont pour ARR 2,0. Pour l’installation de l’extension, il n’y a pas de différence entre les deux versions.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

