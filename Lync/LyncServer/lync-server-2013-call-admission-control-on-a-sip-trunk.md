---
title: 'Lync Server 2013 : contrôle d’admission des appels sur une jonction SIP'
description: 'Lync Server 2013 : contrôle d’admission des appels sur une jonction SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3667ef4608b221a1607b6bbe0d89d390cb1dd402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563156"
---
# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="fb5cc-103">Contrôle d’admission des appels sur une jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb5cc-103">Call admission control on a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb5cc-104">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="fb5cc-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="fb5cc-p101">Pour déployer le contrôle d’admission des appels sur une jonction SIP, vous créez un site réseau pour représenter le fournisseur de services de téléphonie Internet (ITSP). Pour appliquer la stratégie de bande passante sur la jonction SIP, vous créez une stratégie intersite entre le site réseau dans votre entreprise et le site réseau créé pour représenter le fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="fb5cc-107">La figure suivante montre un exemple de déploiement du contrôle d’admission des appels sur une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-107">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="fb5cc-108">**Configuration du contrôle d’admission des appels sur une jonction SIP**</span><span class="sxs-lookup"><span data-stu-id="fb5cc-108">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="fb5cc-109">![Diagramme de jonction SIP de contrôle d’admission des appels](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagramme de jonction SIP de contrôle d’admission des appels")</span><span class="sxs-lookup"><span data-stu-id="fb5cc-109">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="fb5cc-110">Pour configurer le contrôle d’admission des appels sur une jonction SIP, vous devrez exécuter les tâches suivantes pendant le déploiement du contrôle d’admission des appels :</span><span class="sxs-lookup"><span data-stu-id="fb5cc-110">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="fb5cc-111">Créez un site réseau pour représenter le fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-111">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="fb5cc-112">Associez le site réseau à une région réseau appropriée, et allouez une bande passante nulle pour l’audio et la vidéo pour ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-112">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="fb5cc-113">Pour plus d’informations, reportez-vous à la rubrique [configure Network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-113">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fb5cc-114">Pour le fournisseur de services de téléphonie Internet, cette configuration de site réseau n’est pas fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-114">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="fb5cc-115">Les valeurs de stratégie de bande passante sont en fait appliquées à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-115">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="fb5cc-116">Créez un lien intersite pour la jonction SIP à l’aide des valeurs de paramètre pertinentes pour le site créé à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-116">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="fb5cc-117">Par exemple, utilisez le nom du site réseau dans votre entreprise comme valeur du paramètre NetworkSiteID1 et le site réseau du fournisseur de services de téléphonie Internet comme valeur du paramètre NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-117">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="fb5cc-118">Pour plus d’informations, consultez la rubrique [Create Network intersite Policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-118">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="fb5cc-119">Consultez également la documentation Lync Server Management Shell pour la cmdlet New-CsNetworkInterSitePolicy.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-119">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="fb5cc-120">Récupérez l’adresse IP du point de terminaison multimédia du contrôleur SBC auprès de votre fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-120">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="fb5cc-121">Ajoutez cette adresse IP avec un masque de sous-réseau de 32 au site réseau qui représente le fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="fb5cc-121">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="fb5cc-122">Pour plus d’informations, consultez [la rubrique associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="fb5cc-122">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

