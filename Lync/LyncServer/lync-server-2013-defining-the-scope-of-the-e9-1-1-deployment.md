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
ms.openlocfilehash: c84c6519ab561fef034fbe0990854087f22b2e41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Avant de configurer Microsoft Lync Server 2013 pour E9-1-1, vous devez planifier votre déploiement E9-1-1. Voici certaines des questions que vous pouvez vous poser :

  - **Quelles sont la stratégie et les obligations légales de votre organisation concernant E9-1-1 ?**  
    Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre. Vous devez consulter votre équipe juridique pour comprendre les obligations qui peuvent s’appliquer à votre déploiement de Lync Server dans vos régions géographiques pertinentes.

<!-- end list -->

  - **Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**  
    Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.

<!-- end list -->

  - **Comment allez-vous déployer E9-1-1 sur des sites de succursales ?**  
    La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale. Si vous avez centralisé des jonctions SIP E-9-1-1 et qu’une panne de réseau étendu se produit, les clients qui se connectent risquent de ne pas pouvoir obtenir un emplacement depuis le service d’informations d’emplacement ou de se connecter au fournisseur de services d’urgence. Lync Server offre plusieurs stratégies de gestion de la résistance des communications vocales dans les succursales, notamment : les réseaux de données résistants, le déploiement d’une jonction SIP à chaque succursale ou l’envoi d’appels d’urgence à la passerelle locale pendant les pannes. Pour plus d’informations, reportez-vous à la rubrique [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**  
    L’acquisition d’emplacement automatique n’est disponible que pour les clients se trouvant sur le réseau de l’organisation, votre société doit donc décider si elle prendra en charge les appels E9-1-1 effectués à partir de clients Lync en dehors du site. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Toutefois, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).
    
    <div>
    

    > [!NOTE]  
    > Les clients Lync des utilisateurs qui se connectent au réseau de votre organisation à l’aide du VPN peuvent récupérer les informations d’adresse IP interne, mais ces adresses ne peuvent pas être utilisées pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux VPN soient exclus du Service d’informations d’emplacement.

    
    </div>

<!-- end list -->

  - **Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**  
    Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau PSTN pour acheminer l’appel via une passerelle PSTN locale.

</div>

<span> </span>

</div>

</div>

</div>

