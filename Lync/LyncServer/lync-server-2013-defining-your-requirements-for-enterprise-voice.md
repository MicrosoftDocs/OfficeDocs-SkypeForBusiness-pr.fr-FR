---
title: 'Lync Server 2013 : Définition de la configuration requise pour Voix Entreprise'
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
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Définition de la configuration requise pour Voix Entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-07_

Cette rubrique fournit une vue d’ensemble des éléments à prendre en compte sur les régions, les sites et les liens entre les sites dans votre topologie et sur la manière dont celles-ci sont importantes lors du déploiement d’Enterprise Voice. Pour plus d’informations sur la prise en compte de ces décisions, voir [paramètres réseau pour les fonctionnalités avancées de voix entreprise de Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) dans la documentation de planification.

<div>

## <a name="sites-and-regions"></a>Sites et régions

Tout d’abord, identifiez les sites de votre topologie dans lesquels vous déploierez Enterprise Voice et les régions réseau auxquelles ces sites appartiennent. En particulier, pensez à la façon dont vous allez assurer la connectivité PSTN (réseau téléphonique commuté) vers chaque site. Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant. Déterminez l’emplacement de déploiement local des passerelles (SBAs) pour le déploiement des passerelles () et l’endroit où vous pouvez configurer les Trunks SIP (localement ou sur le site central) vers un fournisseur de services de téléphonie Internet (ITSP).

</div>

<div>

## <a name="network-links-between-sites"></a>Liaisons réseau entre sites

Vous devez également tenir compte de l’utilisation de la bande passante que vous attendez sur les liens réseau entre votre site central et ses sites de succursale. Si vous avez, ou envisagez de déployer, des liens WAN résilients entre les sites, nous vous conseillons de déployer une passerelle sur chaque site de succursale afin de fournir une résiliation directe à l’intérieur de ces sites. Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci. Si vous n’avez pas de liens WAN résilients, l’hébergement est inférieur à 1000 utilisateurs sur votre site de succursale et ne disposent pas des administrateurs Lync Server qualifiés en local, nous vous recommandons de déployer une application de succursale Survivable sur le site de la succursale. Si vous hébergez vos utilisateurs 1000 et 5000 sur votre site de succursale, si vous n’avez pas de connexion WAN fiable et si les administrateurs Lync Server sont disponibles, nous vous conseillons de déployer un serveur de succursales survivant auprès d’une petite passerelle sur le site de la succursale. Envisagez aussi d’activer la déviation du trafic multimédia sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

