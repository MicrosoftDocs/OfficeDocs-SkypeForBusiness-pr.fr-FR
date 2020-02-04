---
title: 'Lync Server 2013 : Demande des certificats pour les composants Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="7dc62-102">Demande des certificats pour les composants Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7dc62-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7dc62-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="7dc62-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7dc62-104">Les certificats nécessaires à la prise en charge de l’accès des utilisateurs externes incluent des certificats émis par une autorité de certification publique et des certificats émis par une autorité de certification d’entreprise interne :</span><span class="sxs-lookup"><span data-stu-id="7dc62-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="7dc62-105">Les certificats requis pour l’interface externe du serveur Edge et le proxy inverse doivent être émis par une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="7dc62-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="7dc62-106">Les certificats requis pour l’interface interne peuvent être émis par une autorité de certification publique ou une autorité de certification d’entreprise interne.</span><span class="sxs-lookup"><span data-stu-id="7dc62-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="7dc62-107">Nous recommandons l’utilisation d’une autorité de certification Windows Server 2008, de Windows Server 2008 R2, d’une autorité de certification Windows Server 2012 ou d’une autorité de certification Windows Server 2012 R2 pour la création de ces certificats pour faire des économies sur les coûts d’utilisation des certificats publics.</span><span class="sxs-lookup"><span data-stu-id="7dc62-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7dc62-108">Il est temps de traiter les demandes de certificat, en particulier celles des autorités de certification publiques, afin de vous assurer qu’elles soient disponibles lorsque vous commencez le déploiement de vos composants serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="7dc62-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="7dc62-109">Pour obtenir une synthèse des exigences de certificats pour les serveurs Edge, voir exigences relatives aux <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">certificats pour l’accès des utilisateurs externes dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7dc62-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7dc62-110">Même si vous pouvez opter pour l’utilisation d’une autorité de certification publique pour le certificat Edge interne, nous vous conseillons d’utiliser une autorité de certification d’entreprise interne pour ces certificats au lieu de réduire le coût des certificats.</span><span class="sxs-lookup"><span data-stu-id="7dc62-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="7dc62-111">Pour obtenir une synthèse des exigences de certificats pour les serveurs Edge, voir exigences relatives aux [certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7dc62-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7dc62-112">Lors de l’installation d’un serveur Edge, le programme d’installation inclut un assistant de certification qui simplifie les tâches de demande, d’attribution et d’installation des certificats, comme décrit dans la section <A href="lync-server-2013-set-up-edge-certificates.md">configurer les certificats d’activation pour Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="7dc62-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="7dc62-113">Si vous souhaitez demander des certificats avant d’installer un serveur Edge (par exemple, pour gagner du temps au cours du déploiement réel des composants du serveur Edge), vous pouvez le faire à l’aide de serveurs internes tant que vous vous assurez que les certificats sont exportés et contiennent tous les autres noms d’objet obligatoires.</span><span class="sxs-lookup"><span data-stu-id="7dc62-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="7dc62-114">Cette documentation ne fournit pas de procédures permettant d’utiliser les serveurs internes pour demander des certificats.</span><span class="sxs-lookup"><span data-stu-id="7dc62-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="7dc62-115">Demander des certificats auprès d’une autorité de certification publique</span><span class="sxs-lookup"><span data-stu-id="7dc62-115">Request certificates from a public CA</span></span>

<span data-ttu-id="7dc62-116">Le déploiement de votre serveur Edge nécessite un certificat public unique pour les interfaces externes des serveurs Edge, qui est utilisé pour le service Edge d’accès, le service Edge de conférence Web et pour le service d’authentification A/V.</span><span class="sxs-lookup"><span data-stu-id="7dc62-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="7dc62-117">Ce certificat doit avoir une clé privée exportable pour s’assurer que le service d’authentification A/V utilise les mêmes clés sur tous les serveurs Edge d’un pool.</span><span class="sxs-lookup"><span data-stu-id="7dc62-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="7dc62-118">Le proxy inverse, qui est utilisé avec Microsoft Internet Security and Acceleration (ISA) Server 2006 ou Microsoft Forefront Threat Management Gateway 2010, nécessite également un certificat public.</span><span class="sxs-lookup"><span data-stu-id="7dc62-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="7dc62-119">Demander des certificats auprès d’une autorité de certification d’entreprise interne</span><span class="sxs-lookup"><span data-stu-id="7dc62-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="7dc62-120">Les certificats requis pour l’interface de bord interne peuvent être émis par une autorité de certification (CA) publique ou une autorité de certification interne.</span><span class="sxs-lookup"><span data-stu-id="7dc62-120">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA.</span></span> <span data-ttu-id="7dc62-121">Vous pouvez utiliser une autorité de certification d’entreprise interne pour réduire le coût des certificats.</span><span class="sxs-lookup"><span data-stu-id="7dc62-121">You can use an internal enterprise CA to help minimize the cost of certificates.</span></span> <span data-ttu-id="7dc62-122">Si votre organisation a déployé une autorité de certification interne, les certificats pour le bord interne doivent être émis par l’autorité de certification interne.</span><span class="sxs-lookup"><span data-stu-id="7dc62-122">If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA.</span></span> <span data-ttu-id="7dc62-123">L’utilisation d’une autorité de certification d’entreprise interne pour les certificats internes peut réduire le coût des certificats.</span><span class="sxs-lookup"><span data-stu-id="7dc62-123">Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="7dc62-124">Pour obtenir une synthèse des exigences en matière de certificats pour les composants Edge, voir exigences relatives aux [certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7dc62-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="7dc62-125">Pour plus d’informations sur l’utilisation d’une autorité de certification publique pour obtenir des certificats, voir [demander des certificats pour les composants Edge dans Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="7dc62-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="7dc62-126">Pour plus d’informations sur la demande, l’installation et l’attribution de certificats, voir [configurer des certificats Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="7dc62-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

