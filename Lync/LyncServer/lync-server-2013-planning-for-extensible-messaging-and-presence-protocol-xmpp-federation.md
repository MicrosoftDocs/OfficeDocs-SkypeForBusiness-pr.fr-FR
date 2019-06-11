---
title: Planification de la Fédération des protocoles de messagerie et de présence extensibles
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4e1d8f9b7f164dd9e83f556dcc57809619278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="f803f-102">Planification de la Fédération des protocoles de messagerie et de présence extensibles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f803f-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f803f-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f803f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f803f-104">Les versions précédentes de Lync Server et d’Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP.</span><span class="sxs-lookup"><span data-stu-id="f803f-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="f803f-105">Dans Microsoft Lync Server 2013, la fonctionnalité XMPP peut être déployée en tant que fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="f803f-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="f803f-106">La fonctionnalité XMPP est installée en deux parties: un proxy XMPP qui s’exécute sur le serveur Edge et la passerelle XMPP qui s’exécute sur les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="f803f-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="f803f-107">Le déploiement et la configuration de XMPP sont abordés dans le déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) que vous envisagez de prendre en charge XMPP au sein de votre organisation en définissant des règles de port et de protocole sur votre pare-feu, la configuration des certificats et l’ajout de DNS registres.</span><span class="sxs-lookup"><span data-stu-id="f803f-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="f803f-108">Les rubriques suivantes de cette section résument les informations dont vous avez besoin pour planifier la Fédération XMPP pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="f803f-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f803f-p103">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="f803f-p103">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f803f-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f803f-111">In This Section</span></span>

  - [<span data-ttu-id="f803f-112">Résumé de certification-Fédération de protocoles de messagerie extensible et de présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f803f-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="f803f-113">Service de synthèse de port-extension de messagerie (XMPP) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f803f-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="f803f-114">Service DNS Summary-extensible Messaging and Presence Protocol (XMPP) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f803f-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f803f-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f803f-115">See Also</span></span>


[<span data-ttu-id="f803f-116">Configuration de la fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f803f-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="f803f-117">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f803f-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="f803f-118">Gestion des partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f803f-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="f803f-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f803f-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="f803f-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f803f-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="f803f-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f803f-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

