---
title: 'Lync Server 2013 : hybride et fractionné-domaine-découverte automatique'
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
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Domaines hybrides et fractionnés-découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

Un espace d’adressage SIP partagé, également connu sous le nom de déploiement *Split-Domain* ou d’un déploiement *hybride* , est une configuration dans laquelle les utilisateurs sont déployés dans un déploiement local et un environnement en ligne. Le résultat escompté est d’avoir un utilisateur, où qu’il se trouve (en local ou en ligne), de se connecter au déploiement et d’être redirigé vers son emplacement du serveur d’origine. Pour ce faire, la fonctionnalité de découverte automatique de Lync Server 2013 est utilisée pour rediriger l’utilisateur en ligne vers la topologie en ligne. Pour ce faire, vous pouvez configurer le localisateur de ressources uniformes de découverte automatique (URL) à l’aide de Lync Server Management Shell, de l’applet **de action Get-CsHostingProvider** et de l’applet **de passe Set-CsHostingProvider** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilité pour le déploiement de domaines fractionnés

Vous devrez collecter et enregistrer les attributs déployés suivants :

  - À partir de Lync Server Management Shell, tapez
    
        Get-CsHostingProvider

  - Dans les résultats, recherchez le fournisseur en ligne doté de l’attribut **ProxyFQDN**. Par exemple, sipfed.online.lync.com.

  - Enregistrez la valeur de ProxyFQDN.

  - Activez la Fédération sur le panneau de configuration de Lync Server sur site, en autorisant la Fédération avec le fournisseur en ligne.

  - Activez la Fédération pour le fournisseur en ligne. Par défaut, tous les utilisateurs en ligne sont activés pour la Fédération de domaine et peuvent communiquer avec tous les domaines.

  - Si vous définissez des domaines bloqués et autorisés, déterminez les domaines à autoriser ou bloquer explicitement.

  - Pour la Fédération en ligne, vous devez prévoir des exceptions de pare-feu, des certificats et l’hôte DNS (A ou AAAA, si vous utilisez des enregistrements IPv6). Par ailleurs, vous devez configurer des stratégies de Fédération. Pour plus d’informations, reportez-vous [à planification de Lync server 2013 et la Fédération Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

