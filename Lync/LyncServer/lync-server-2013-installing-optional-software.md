---
title: 'Lync Server 2013: installation de logiciels facultatifs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6723d005a41b52025c7e3e475bc3b3a108f2c3d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Installer un logiciel facultatif dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

L’outil de planification Microsoft Lync Server 2013 est conçu pour être exporté vers Microsoft Excel et Microsoft Visio. Même si ces applications ne sont pas nécessaires pour l’utilisation de l’outil de planification, elles ajoutent une valeur importante au déploiement et à la documentation de votre conception.

<div>

## <a name="optional-software"></a>Logiciels facultatifs

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

L’exportation de votre conception vers Microsoft Excel permet de créer un rapport sous forme de feuille de calcul à quatre onglets :

  - Synthèse : affiche des informations sur la configuration du site, notamment le nombre d’utilisateurs, les paramètres de capacité et les informations de profil du serveur.

  - Profil matériel : affiche un rapport détaillant les configurations matérielles recommandées pour les serveurs spécifiés dans la topologie, y compris le processeur, la mémoire, le disque et l’interface réseau. La quantité et les caractéristiques conseillées pour les composants serveur y figurent également. Par ailleurs, chaque serveur est défini par site afin de fournir une représentation complète de la configuration serveur requise pour chaque site.

  - Configuration requise pour les ports : affiche un rapport de tous les ports activés et l’association entre l’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle. Vous devez utiliser ce rapport pour planifier votre pare-feu et les configurations de l’équilibrage de la charge DNS et des programmes d’équilibrage de la charge matérielle.

  - Rapport de synthèse: affiche la synthèse générale des paramètres nécessaires à la configuration de votre réseau Edge Server.

  - Rapport sur les certificats: affiche le nom du sujet et les noms de domaine alternatifs requis pour les certificats nécessaires à l’exécution des serveurs Edge.

  - Rapport de pare-feu : affiche les adresses IP et ports sources et de destination des interfaces internes et externes.

  - Rapport DNS : affiche le nom de domaine complet et les adresses IP/VIP requises pour chaque entrée DNS que vous créez.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :

<div>


> [!NOTE]  
> Si votre conception est suffisamment grande pour nécessiter plus de trois serveurs frontaux, une page supplémentaire est créée pour le pool frontal, les serveurs frontaux, l’ordinateur exécutant SQL Server, les adresses IP et les noms de domaine complets.



</div>

  - Topologie globale: diagramme des sites Lync Server 2013 configurés.

  - Onglet nom du site: affiche la topologie de configuration de site avec serveur de périmètre, pare-feu, réseau téléphonique public commuté (RTC) avec passerelles et le déploiement de serveur interne. Le déploiement interne se compose de serveurs et de pools configurés, y compris les pools front end, serveurs SQL Server, services de domaine Active Directory, directeurs, serveurs de messagerie unifiée Exchange, serveurs de boîte aux lettres Exchange, serveurs Office Web Apps. Serveurs de médiation et serveurs de chat permanents.

  - Cartographie de réseaux de réseaux latéraux: diagramme détaillant la configuration du serveur Edge avec les adresses IP et noms de domaine complets associés. L’équilibrage de la charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus. De plus, les directeurs et le serveur frontal ou le pool frontal sont affichés, avec DNS ou HLB associé et l’adresse IP attribuée (l’outil de planification prend en charge à la fois les adresses IPv4 et IPv6) et le FQDN.

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Installation de l’outil de planification dans Lync Server 2013](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

