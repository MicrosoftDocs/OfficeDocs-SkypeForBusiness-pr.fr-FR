---
title: 'Lync Server 2013 : configuration des certificats pour le proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e5bf87e02dbcdebeb8b1bb5a7a360c2c91ab00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509871"
---
# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="e4a02-102">Configurer des certificats pour le proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4a02-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4a02-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e4a02-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e4a02-p101">Chaque serveur de proxy inverse nécessite un certificat de serveur web à la disposition du service d’écoute. Le certificat de serveur web doit être émis par une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="e4a02-p101">Each reverse proxy server requires a web server certificate for use by the listening service. The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="e4a02-106">Pour plus d’informations à ce sujet et sur d’autres exigences de certificat, voir [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e4a02-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="e4a02-107">Pour configurer un certificat de services web pour le serveur proxy inverse</span><span class="sxs-lookup"><span data-stu-id="e4a02-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="e4a02-108">Vous devriez déjà avoir configuré votre proxy inverse, y compris la configuration du certificat de services Web.</span><span class="sxs-lookup"><span data-stu-id="e4a02-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="e4a02-109">Si vous ne l’avez pas fait avant de commencer le déploiement de vos serveurs Edge, suivez les procédures décrites dans [Setting up Reverse Proxy Servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) pour créer une demande et installer le certificat de services Web, puis créez chaque règle de publication Web et configurez-la pour utiliser le certificat.</span><span class="sxs-lookup"><span data-stu-id="e4a02-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

