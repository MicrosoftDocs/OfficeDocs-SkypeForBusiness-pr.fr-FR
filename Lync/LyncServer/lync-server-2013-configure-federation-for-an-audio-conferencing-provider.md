---
title: 'Lync Server 2013 : configuration de la Fédération pour un fournisseur de services d’audioconférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a85a8ef64d43561a68dca7c850f79cc6a1632fc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Configurer la Fédération pour un fournisseur de services d’audioconférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-07-24_

Si vous souhaitez utiliser un fournisseur de services d’audioconférence (ACP) dans votre déploiement hybride (Lync Server local avec Lync Online), vous devez configurer la Fédération entre votre déploiement Lync local et le partenaire ACP en tant que serveur partenaire autorisé. Vous pouvez configurer la Fédération en ajoutant le domaine du partenaire ACP et le serveur Edge (il peut également s’agir du proxy d’accès) à la liste des domaines fédérés pour votre déploiement local. Votre partenaire ACP doit ensuite ajouter le nom de domaine complet de votre pool de serveurs Edge sur site à la liste des domaines fédérés autorisés. Contactez votre fournisseur ACP pour obtenir des partenaires ACP detailsYour supplémentaires, puis ajoutez le nom de domaine complet de votre pool de serveurs Edge sur site à la liste des domaines fédérés autorisés.

  - **Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**
    
    Pour ajouter le domaine ACP en tant que serveur partenaire autorisé (domaine fédéré autorisé), suivez les étapes décrites dans [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md). Pour le serveur Edge, ajoutez le nom de domaine complet (FQDN) du serveur Edge du partenaire ACP. Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, qui peut également être désigné par votre partenaire ACP en tant que proxy d’accès.

  - **Fournir le nom de domaine complet (FQDN) de votre pool de serveurs Edge au partenaire ACP**
    
    Le partenaire ACP doit configurer la Fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.

</div>

<span> </span>

</div>

</div>

</div>

