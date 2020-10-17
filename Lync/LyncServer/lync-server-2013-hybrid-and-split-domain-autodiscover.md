---
title: 'Lync Server 2013 : hybride et Split-Domain-autodiscover'
description: 'Lync Server 2013 : hybride et Split-Domain-autodiscover.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972233fd10d2b68a002d2d3a203f61bb0bd29574
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554880"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Découverte automatique de domaine hybride et fractionné dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

Un espace d’adressage SIP partagé, également appelé déploiement de *domaine scindé* , ou déploiement *hybride* , est une configuration où les utilisateurs sont déployés dans un déploiement local et un environnement en ligne. Le résultat souhaité est qu’un utilisateur, quel que soit l’emplacement de son serveur d’accueil (local ou en ligne), se connecte au déploiement et soit redirigé vers son serveur d’origine. Pour ce faire, la fonctionnalité de découverte automatique de Lync Server 2013 est utilisée pour rediriger l’utilisateur en ligne vers la topologie en ligne. Pour ce faire, vous pouvez configurer l’URL (Uniform Resource Locator) de découverte automatique à l’aide de Lync Server Management Shell, de la cmdlet **Get-CsHostingProvider** et de la cmdlet **Set-CsHostingProvider** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilité pour le déploiement dans un domaine séparé

Vous devrez recueillir et enregistrer les attributs déployés suivants :

  - À partir de Lync Server Management Shell, tapez
    
        Get-CsHostingProvider

  - Dans les résultats, recherchez le fournisseur en ligne avec l’attribut **ProxyFQDN**. Par exemple, sipfed.online.lync.com.

  - Enregistrez la valeur de ProxyFQDN.

  - Activez la Fédération dans le panneau de configuration Lync Server sur site, en autorisant la Fédération avec le fournisseur en ligne.

  - Activez la fédération pour le fournisseur en ligne. Par défaut, tous les utilisateurs en ligne sont activés pour la Fédération de domaine et peuvent communiquer avec tous les domaines.

  - Si vous définissez des domaines bloqués et autorisés, déterminez les domaines que vous autorisez explicitement ou bloquez explicitement.

  - Pour la Fédération en ligne, vous devez planifier les exceptions de pare-feu, les certificats et l’hôte DNS (A ou AAAA, si vous utilisez le protocole IPv6). En outre, vous devez configurer les stratégies de fédération. Pour plus d’informations, reportez-vous à la rubrique [Planning for Lync Server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

