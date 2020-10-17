---
title: 'Lync Server 2013 : configuration de la Fédération pour un fournisseur de services d’audioconférence'
description: 'Lync Server 2013 : configuration de la Fédération pour un fournisseur de services d’audioconférence.'
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
ms.openlocfilehash: c74654224c42618768d881a95031d58be4d55df5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553320"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="94ded-103">Configurer la Fédération pour un fournisseur de services d’audioconférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94ded-103">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94ded-104">_**Dernière modification de la rubrique :** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="94ded-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="94ded-105">Si vous souhaitez utiliser un fournisseur de services d’audioconférence (ACP) dans votre déploiement hybride (Lync Server local avec Lync Online), vous devez configurer la Fédération entre votre déploiement Lync local et le partenaire ACP en tant que serveur partenaire autorisé.</span><span class="sxs-lookup"><span data-stu-id="94ded-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="94ded-106">Vous pouvez configurer la Fédération en ajoutant le domaine du partenaire ACP et le serveur Edge (il peut également s’agir du proxy d’accès) à la liste des domaines fédérés pour votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="94ded-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="94ded-107">Votre partenaire ACP doit ensuite ajouter le nom de domaine complet de votre pool de serveurs Edge sur site à la liste des domaines fédérés autorisés.</span><span class="sxs-lookup"><span data-stu-id="94ded-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="94ded-108">Contactez votre fournisseur ACP pour obtenir des partenaires ACP detailsYour supplémentaires, puis ajoutez le nom de domaine complet de votre pool de serveurs Edge sur site à la liste des domaines fédérés autorisés.</span><span class="sxs-lookup"><span data-stu-id="94ded-108">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="94ded-109">**Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**</span><span class="sxs-lookup"><span data-stu-id="94ded-109">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="94ded-110">Pour ajouter le domaine ACP en tant que serveur partenaire autorisé (domaine fédéré autorisé), suivez les étapes décrites dans [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="94ded-110">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="94ded-111">Pour le serveur Edge, ajoutez le nom de domaine complet (FQDN) du serveur Edge du partenaire ACP.</span><span class="sxs-lookup"><span data-stu-id="94ded-111">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="94ded-112">Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, qui peut également être désigné par votre partenaire ACP en tant que proxy d’accès.</span><span class="sxs-lookup"><span data-stu-id="94ded-112">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="94ded-113">**Fournir le nom de domaine complet (FQDN) de votre pool de serveurs Edge au partenaire ACP**</span><span class="sxs-lookup"><span data-stu-id="94ded-113">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="94ded-114">Le partenaire ACP doit configurer la Fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.</span><span class="sxs-lookup"><span data-stu-id="94ded-114">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

