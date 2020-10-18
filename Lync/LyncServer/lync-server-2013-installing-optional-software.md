---
title: 'Lync Server 2013 : installation de logiciels facultatifs'
description: 'Lync Server 2013 : installation de logiciels facultatifs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7423c0d54b762fb4af7cedc8d7ba8745fd94bdf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573910"
---
# <a name="installing-optional-software-in-lync-server-2013"></a>Installation de logiciels facultatifs dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

L’outil de planification Microsoft Lync Server 2013 est conçu pour l’exportation vers Microsoft Excel et Microsoft Visio. Bien que ces applications ne soient pas requises pour le fonctionnement de l’outil de planification, elles ajoutent une valeur significative au déploiement et à la documentation de votre conception.

<div>

## <a name="optional-software"></a>Logiciels facultatifs

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

L’exportation de votre conception vers Microsoft Excel crée un rapport qui affiche sept onglets dans la feuille de calcul :

  - Résumé : affiche des informations sur la configuration du site, notamment le nombre d’utilisateurs, les paramètres de capacité et les informations de profil de serveur.

  - Profil matériel : affiche un rapport détaillant les configurations matérielles recommandées pour les serveurs spécifiés dans la topologie, y compris le processeur, la mémoire, le disque et l’interface réseau. La quantité et les spécifications recommandées pour les composants serveur sont également incluses. Par ailleurs, chaque serveur est défini par site pour fournir une représentation complète des exigences en matière de serveur par site.

  - Ports Requirements : affiche un rapport de tous les ports activés, ainsi que l’association avec l’équilibrage de charge DNS (Domain Name System) et les programmes d’équilibrage de la charge matérielle (charge matérielle). Vous devez utiliser ce rapport pour planifier vos configurations de pare-feu et de DNS et charge matérielle.

  - Rapport de synthèse : affiche le résumé général des paramètres requis pour configurer votre réseau de serveur Edge.

  - Certificate Report : affiche le nom de l’objet et les autres noms du sujet requis pour les certificats nécessaires pour obtenir les serveurs Edge en cours d’exécution.

  - Rapport de pare-feu : affiche les adresses IP et les ports source et de destination pour les interfaces internes et externes.

  - Rapport DNS : affiche le nom de domaine complet (FQDN) et les adresses IP/VIP requises pour chaque entrée DNS que vous créez.

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

L’exportation de votre conception vers Microsoft Visio crée un diagramme à utiliser dans la documentation de votre topologie et infrastructure configurée. Le diagramme importé peut être modifié et réorganisé pour répondre aux besoins de votre documentation. Un diagramme Visio classique inclut les éléments suivants :

<div>


> [!NOTE]  
> Si votre conception est suffisamment importante pour nécessiter plus de trois serveurs frontaux, une page supplémentaire est créée pour le pool frontal, les serveurs frontaux, l’ordinateur exécutant SQL Server, les adresses IP et les noms de domaine complets.



</div>

  - Topologie globale : diagramme des sites Lync Server 2013 configurés.

  - Onglet nom du site – affiche la topologie de configuration de site avec le serveur Edge, le pare-feu, le réseau téléphonique commuté (RTC) avec passerelles et le déploiement du serveur interne. Le déploiement interne se compose de serveurs et de pools configurés, y compris les pools frontaux, les serveurs SQL Server, les services de domaine Active Directory, les directeurs, les serveurs de messagerie unifiée Exchange, les serveurs de boîtes aux lettres Exchange, les serveurs Office Web Apps, les serveurs de médiation et les serveurs de conversation permanente.

  - Diagramme de réseau Edge : diagramme détaillant la configuration du serveur Edge avec des adresses IP et des noms de domaine complets associés. L’équilibrage de charge DNS et les programmes d’équilibrage de la charge matérielle sont également inclus. De plus, les directeurs et le serveur frontal ou le pool frontal sont affichés, avec le DNS charge matérielle associé et l’adresse IP affectée (l’outil de planification prend en charge les adresses IPv4 et IPv6) et le nom de domaine complet (FQDN).

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

