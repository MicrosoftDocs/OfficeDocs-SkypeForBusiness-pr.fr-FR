---
title: 'Lync Server 2013 : définition de l’étendue du déploiement E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Avant de configurer Microsoft Lync Server 2013 pour E9-1-1, vous devez planifier votre déploiement E9-1-1. Voici certaines des questions que vous pouvez vous poser :

  - **Quelles sont la stratégie et les obligations légales de votre organisation concernant E9-1-1 ?**  
    Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre. Reportez-vous à votre équipe légale pour comprendre les obligations qui pourraient s’appliquer à votre déploiement de Lync Server dans vos zones géographiques pertinentes.

<!-- end list -->

  - **Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**  
    Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.

<!-- end list -->

  - **Comment allez-vous déployer E9-1-1 sur des sites de succursale ?**  
    La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale. Si vous avez centralisé des lignes SIP E-9-1-1 et une panne de réseau étendu (WAN), les clients qui se connectent risquent de ne pas être en mesure d’obtenir un emplacement à partir du service de coordonnées de l’emplacement ou de se connecter au fournisseur de services d’urgence. Lync Server offre plusieurs stratégies de gestion de la résilience vocale dans les succursales, notamment : disposer de réseaux de données résilients, déploiement d’une ligne SIP dans chaque succursale ou envoi d’appels d’urgence vers la passerelle locale lors des pannes. Pour plus d’informations, reportez-vous à la rubrique [planification de la résilience vocale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**  
    L’acquisition automatique de l’emplacement est disponible uniquement pour les clients situés à l’intérieur du réseau de l’organisation, afin que votre organisation puisse prendre en charge les appels E9-1-1 passés à partir des clients Lync en local. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Cependant, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).
    
    <div>
    

    > [!NOTE]  
    > Les clients Lync qui se connectent au réseau de votre organisation à l’aide d’un VPN peuvent capter les informations d’adresse IP interne, mais ces adresses ne peuvent pas être utilisées pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux VPN soient exclus du Service d’information d’emplacement.

    
    </div>

<!-- end list -->

  - **Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**  
    Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau RTC pour acheminer l’appel via une passerelle RTC locale.

</div>

<span> </span>

</div>

</div>

</div>

