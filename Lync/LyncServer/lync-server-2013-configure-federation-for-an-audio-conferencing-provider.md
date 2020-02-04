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
ms.openlocfilehash: c5c1ca77b2f68a2285fb15d65c19631323a03bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a><span data-ttu-id="08bf2-102">Configurer la Fédération pour un fournisseur de services d’audioconférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08bf2-102">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08bf2-103">_**Dernière modification de la rubrique :** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="08bf2-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="08bf2-104">Si vous souhaitez utiliser un fournisseur de services d’audioconférence (ACP) dans votre déploiement hybride (Lync Server local avec Lync Online), vous devez configurer la Fédération entre votre déploiement Lync local et le partenaire ACP en tant que serveur partenaire autorisé.</span><span class="sxs-lookup"><span data-stu-id="08bf2-104">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (Lync Server on-premises with Lync Online), you need to configure federation between your on-premises Lync deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="08bf2-105">Vous pouvez configurer la Fédération en ajoutant le domaine du partenaire ACP et le serveur de périphérie (cela peut également être appelé proxy d’accès) à la liste des domaines fédérés pour votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="08bf2-105">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="08bf2-106">Votre partenaire ACP doit ensuite ajouter le nom de domaine complet (FQDN) du pool de serveurs Edge local à sa liste des domaines fédérés autorisés.</span><span class="sxs-lookup"><span data-stu-id="08bf2-106">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="08bf2-107">Contactez votre fournisseur de services d’audioconférence pour plus de detailsYour partenaire ACP, puis ajoutez le nom de domaine complet (FQDN) de votre pool de serveurs Edge local à sa liste des domaines fédérés autorisés.</span><span class="sxs-lookup"><span data-stu-id="08bf2-107">Contact your ACP provider for additional detailsYour ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

  - <span data-ttu-id="08bf2-108">**Ajout du domaine ACP et du serveur Edge en tant que domaine fédéré autorisé**</span><span class="sxs-lookup"><span data-stu-id="08bf2-108">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="08bf2-109">Pour ajouter le domaine ACP comme serveur partenaire autorisé (domaine fédéré autorisé), suivez les étapes décrites dans [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="08bf2-109">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span> <span data-ttu-id="08bf2-110">Pour le serveur Edge, ajoutez le nom de domaine complet (FQDN) du serveur Edge du partenaire ACP.</span><span class="sxs-lookup"><span data-stu-id="08bf2-110">For the Edge Server, add the FQDN of the ACP partner’s Edge Server.</span></span> <span data-ttu-id="08bf2-111">Vous devrez peut-être contacter votre partenaire ACP pour obtenir le nom de domaine complet (FQDN) de son serveur Edge, que votre ACP peut également appelé « serveur proxy d’accès ».</span><span class="sxs-lookup"><span data-stu-id="08bf2-111">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

  - <span data-ttu-id="08bf2-112">**Transmission du nom de domaine complet (FQDN) de votre pool de serveurs Edge au partenaire ACP**</span><span class="sxs-lookup"><span data-stu-id="08bf2-112">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="08bf2-113">Le partenaire ACP doit configurer la fédération pour ajouter votre domaine local en tant que serveur partenaire autorisé en ajoutant le nom de domaine complet (FQDN) de votre pool de serveurs Edge en tant que domaine fédéré autorisé.</span><span class="sxs-lookup"><span data-stu-id="08bf2-113">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

