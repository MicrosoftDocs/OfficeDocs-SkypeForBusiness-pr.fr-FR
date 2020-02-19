---
title: Prise en charge de l’infrastructure de certificat Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56582d57400bb59e55978caf67a6b957fc91f47d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="892bb-102">Prise en charge de l’infrastructure de certificat dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="892bb-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="892bb-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="892bb-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="892bb-104">Lync Server 2013 nécessite une infrastructure à clé publique (PKI) pour prendre en charge les connexions TLS (Transport Layer Security) et MTLS (Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="892bb-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="892bb-105">Par défaut, Lync Server 2013 est configuré pour utiliser le protocole TLS pour les connexions client à serveur.</span><span class="sxs-lookup"><span data-stu-id="892bb-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="892bb-106">MTLS est utilisé pour les connexions entre serveurs.</span><span class="sxs-lookup"><span data-stu-id="892bb-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="892bb-107">Les certificats MTLS doivent être émis par des autorités de certification approuvées pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="892bb-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="892bb-108">Lync Server prend en charge les certificats qui sont émis à partir des autorités de certification suivantes :</span><span class="sxs-lookup"><span data-stu-id="892bb-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="892bb-109">Certificats émis par une autorité de certification interne :</span><span class="sxs-lookup"><span data-stu-id="892bb-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="892bb-110">Autorité de certification de système d’exploitation Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="892bb-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="892bb-111">Autorité de certification de système d’exploitation Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="892bb-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="892bb-112">Autorité de certification du système d’exploitation Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="892bb-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="892bb-113">Autorité de certification de système d’exploitation Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="892bb-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="892bb-114">Autorité de certification du système d’exploitation Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="892bb-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="892bb-115">Certificats émis par une autorité de certification publique</span><span class="sxs-lookup"><span data-stu-id="892bb-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="892bb-116">La communication avec d’autres applications et serveurs, comme Exchange 2013, nécessite un certificat pris en charge par les autres applications et produits.</span><span class="sxs-lookup"><span data-stu-id="892bb-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="892bb-117">Pour la version 2013, Lync Server 2013 et d’autres produits serveur Microsoft, y compris Exchange 2013 et SharePoint Server, prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="892bb-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="892bb-118">Pour plus d’informations, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="892bb-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="892bb-119">Pour les connexions à partir de clients exécutant le système d’exploitation Windows 7, le système d’exploitation Windows Server 2008 R2 et Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 inclut une prise en charge pour (mais pas pour autant que nécessaire) des certificats signés à l’aide de l’algorithme SHA-256 fonction de hachage de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="892bb-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="892bb-120">Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.</span><span class="sxs-lookup"><span data-stu-id="892bb-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="892bb-121">Pour plus d’informations sur les certificats requis, voir [Certificate infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="892bb-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="892bb-122">Pour plus d’informations sur l’utilisation des caractères génériques avec des certificats, voir [générique Certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="892bb-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

