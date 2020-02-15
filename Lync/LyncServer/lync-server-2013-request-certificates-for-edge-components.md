---
title: 'Lync Server 2013 : demande de certificats pour les composants Edge'
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
ms.openlocfilehash: 10e7a724edd6e68602e4655a783f953ad1e2bc2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="bb23f-102">Demander des certificats pour les composants Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb23f-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb23f-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="bb23f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="bb23f-104">Les certificats nécessaires à la prise en charge de l’accès des utilisateurs externes incluent les certificats émis par une autorité de certification publique et les certificats émis par une autorité de certification d’entreprise interne :</span><span class="sxs-lookup"><span data-stu-id="bb23f-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="bb23f-105">Les certificats requis pour l’interface externe du serveur Edge et le proxy inverse doivent être émis par une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="bb23f-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="bb23f-106">Les certificats requis pour l’interface interne peuvent être émis par une autorité de certification publique ou une autorité de certification d’entreprise interne.</span><span class="sxs-lookup"><span data-stu-id="bb23f-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="bb23f-107">Nous vous recommandons d’utiliser une autorité de certification Windows Server 2008 interne, Windows Server 2008 R2 CA, Windows Server 2012 CA ou Windows Server 2012 R2 pour créer ces certificats afin d’économiser sur les frais d’utilisation des certificats publics.</span><span class="sxs-lookup"><span data-stu-id="bb23f-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb23f-108">Le traitement des demandes de certificat, en particulier les demandes adressées aux autorités de certification publiques, peut prendre du temps, donc vous devez demander des certificats pour vos serveurs Edge suffisamment tôt pour vous assurer qu’ils sont disponibles lorsque vous démarrez le déploiement de vos composants de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="bb23f-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="bb23f-109">Pour obtenir un résumé des exigences en matière de certificats pour les serveurs Edge, reportez-vous à <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate Requirements for External User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bb23f-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="bb23f-110">Même si vous pouvez choisir d’utiliser une autorité de certification publique pour le certificat Edge interne, nous vous conseillons plutôt d’utiliser une autorité de certification d’entreprise interne pour les autres certificats pour en réduire le coût.</span><span class="sxs-lookup"><span data-stu-id="bb23f-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="bb23f-111">Pour obtenir un résumé des exigences en matière de certificats pour les serveurs Edge, reportez-vous à [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="bb23f-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb23f-112">Lorsque vous installez un serveur Edge, le programme d’installation inclut un Assistant certificat qui facilite les tâches de demande, d’affectation et d’installation des certificats, comme décrit dans la section <A href="lync-server-2013-set-up-edge-certificates.md">set up Edge Certificates for Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="bb23f-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="bb23f-113">Si vous souhaitez demander des certificats avant d’installer un serveur Edge (par exemple, pour gagner du temps pendant le déploiement réel des composants de serveur Edge), vous pouvez le faire à l’aide de serveurs internes tant que vous vous assurez que les certificats sont exportables et qu’ils contiennent tous les autres noms de sujet requis.</span><span class="sxs-lookup"><span data-stu-id="bb23f-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="bb23f-114">Cette documentation ne fournit pas de procédures relatives à l’utilisation de serveurs internes pour la demande de certificats.</span><span class="sxs-lookup"><span data-stu-id="bb23f-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="bb23f-115">Demander des certificats à une autorité de certification publique</span><span class="sxs-lookup"><span data-stu-id="bb23f-115">Request certificates from a public CA</span></span>

<span data-ttu-id="bb23f-116">Le déploiement de votre serveur Edge nécessite un certificat public unique pour les interfaces externes des serveurs Edge, utilisé pour le service Edge d’accès, le service Edge de conférence Web et le service d’authentification A/V.</span><span class="sxs-lookup"><span data-stu-id="bb23f-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="bb23f-117">Ce certificat doit disposer d’une clé privée exportable pour s’assurer que le service d’authentification A/V utilise les mêmes clés sur tous les serveurs Edge d’un pool.</span><span class="sxs-lookup"><span data-stu-id="bb23f-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="bb23f-118">Le proxy inverse, qui est utilisé avec Microsoft Internet Security and Acceleration (ISA) Server 2006 ou Microsoft Forefront Threat Management Gateway 2010, nécessite également un certificat public.</span><span class="sxs-lookup"><span data-stu-id="bb23f-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="bb23f-119">Demander des certificats à partir d’une autorité de certification d’entreprise interne</span><span class="sxs-lookup"><span data-stu-id="bb23f-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="bb23f-p106">Les certificats nécessaires à l’interface interne du serveur Edge peuvent être émis par une autorité de certification publique ou interne. L’utilisation d’une autorité de certification interne à l’entreprise permet de réduire les coûts de certificat. Si votre organisation en a déployé une, les certificats des serveurs Edge internes doivent être émis par cette autorité de certification. L’utilisation d’une autorité de certification interne à l’entreprise permet de réduire les coûts de certificat.</span><span class="sxs-lookup"><span data-stu-id="bb23f-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="bb23f-124">Pour obtenir un résumé des exigences en matière de certificats pour les composants Edge, voir [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="bb23f-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="bb23f-125">Pour plus d’informations sur l’utilisation d’une autorité de certification publique pour obtenir des certificats, voir [demander des certificats pour les composants Edge dans Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span><span class="sxs-lookup"><span data-stu-id="bb23f-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="bb23f-126">Pour plus d’informations sur la demande, l’installation et l’affectation de certificats, voir [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="bb23f-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

