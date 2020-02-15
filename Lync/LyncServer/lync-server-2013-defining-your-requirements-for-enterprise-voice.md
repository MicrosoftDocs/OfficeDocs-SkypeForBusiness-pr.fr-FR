---
title: 'Lync Server 2013 : définition de la configuration requise pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d88a70796282fe09941ce7632d8c13258defc515
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Définition de la configuration requise pour voix entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-07_

Cette rubrique fournit une vue d’ensemble des éléments à prendre en compte concernant les régions, les sites et les liens entre les sites de votre topologie et la façon dont ils sont importants lorsque vous déployez voix entreprise. Pour plus d’informations pour vous aider à prendre ces décisions, voir [paramètres réseau pour les fonctionnalités avancées de voix entreprise dans Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) dans la documentation de planification.

<div>

## <a name="sites-and-regions"></a>Sites et régions

Tout d’abord, identifiez les sites de votre topologie dans lesquels vous allez déployer voix entreprise et les régions réseau auxquelles ces sites appartiennent. En particulier, pensez à la façon dont vous allez assurer la connectivité PSTN (réseau téléphonique commuté) vers chaque site. Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant. Déterminez l’emplacement où les passerelles seront déployées localement, où Survivable Branch Appliances (SBA) seront déployés et où vous pouvez configurer des jonctions SIP (localement ou sur le site central) vers un fournisseur de services de téléphonie Internet (téléphonie Internet).

</div>

<div>

## <a name="network-links-between-sites"></a>Liaisons réseau entre sites

Vous devez également tenir compte de l’utilisation de la bande passante que vous attendez sur les liaisons réseau entre votre site central et ses sites de succursale. Si vous avez ou envisagez de déployer des liaisons de réseau étendu (WAN) résilientes entre les sites, nous vous recommandons de déployer une passerelle sur chaque site de succursale afin de fournir une terminaison de numérotation directe vers l’intérieur pour les utilisateurs de ces sites. Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci. Si vous n’avez pas de liaisons WAN résilientes, que vous hébergez moins de 1000 utilisateurs sur votre site de succursale et que vous ne disposez pas des administrateurs Lync Server formés en local, nous vous recommandons de déployer un Survivable Branch appliance sur le site de succursale. Si vous hébergez entre 1000 et 5000 utilisateurs sur votre site de succursale, si vous ne disposez pas d’une connexion WAN résiliente et si vous disposez d’administrateurs Lync Server formés, nous vous recommandons de déployer un serveur Survivable Branch Server avec une petite passerelle sur le site de succursale. Envisagez aussi d’activer le contournement de média sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Paramètres réseau pour les fonctionnalités avancées de voix entreprise dans Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

