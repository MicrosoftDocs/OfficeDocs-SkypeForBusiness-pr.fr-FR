---
title: 'Lync Server 2013 : modifier ou configurer des URL simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e77d5ddf74d43cd277a701608e801a65262c929
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="2748e-102">Modifier ou configurer des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2748e-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2748e-103">_**Dernière modification de la rubrique :** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="2748e-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="2748e-p101">Pour effectuer cette procédure, il n’est pas nécessaire d’appartenir à un groupe d’administrateurs local ou de domaines privilégiés. Vous devez simplement ouvrir une session sur un ordinateur en tant qu’utilisateur standard.</span><span class="sxs-lookup"><span data-stu-id="2748e-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="2748e-106">Lync Server 2013 utilise des URL simples pour diriger les appels internes et externes vers des services sur le serveur frontal ou sur le directeur, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="2748e-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="2748e-107">Pour plus d’informations sur les URL simples, voir [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="2748e-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="2748e-108">Vous pouvez sélectionner le format de vos URL simples à partir de plusieurs options.</span><span class="sxs-lookup"><span data-stu-id="2748e-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="2748e-109">Pour plus d’informations sur ces options, consultez la rubrique [DNS Requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="2748e-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="2748e-110">Par défaut, les URL simples sont configurées sous la forme (par exemple, l’URL simple Dial-in) : https://dialin.\<SIP Domain.\></span><span class="sxs-lookup"><span data-stu-id="2748e-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="2748e-111">Pour configurer des URL simples</span><span class="sxs-lookup"><span data-stu-id="2748e-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="2748e-112">Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud **Lync Server** , puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2748e-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="2748e-113">Dans le volet **URL simples** , sélectionnez **URL d’accès téléphonique :** (accès à distance) ou **URL de réunion :** (réunion) pour modifier, puis cliquez sur **modifier l’URL**.</span><span class="sxs-lookup"><span data-stu-id="2748e-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="2748e-114">Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer.</span><span class="sxs-lookup"><span data-stu-id="2748e-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="2748e-115">L’exemple ci-dessous a modifié l’URL de connexion vers https://pool01.contoso.net/dialin.</span><span class="sxs-lookup"><span data-stu-id="2748e-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="2748e-116">Modifiez l’URL Meet en procédant de la même manière, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2748e-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="2748e-117">Pour définir l’URL simple Admin facultative</span><span class="sxs-lookup"><span data-stu-id="2748e-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="2748e-118">Dans le générateur de topologies, cliquez avec le bouton droit sur le nœud **Lync Server** , puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2748e-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="2748e-119">Dans la zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour l’accès administratif au panneau de configuration Lync Server 2013, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2748e-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2748e-120">Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin.</span><span class="sxs-lookup"><span data-stu-id="2748e-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="2748e-121">L’option la plus simple est <STRONG> https://admin.</STRONG> &lt;domaine&gt;.</span><span class="sxs-lookup"><span data-stu-id="2748e-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2748e-122">Si vous modifiez une URL simple après le déploiement initial, vous devez savoir quelles modifications ont un impact sur les enregistrements DNS (Domain Name System) et les certificats pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="2748e-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="2748e-123">Si la modification a un impact sur la base d’une URL simple, vous devez également modifier les enregistrements DNS et les certificats.</span><span class="sxs-lookup"><span data-stu-id="2748e-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="2748e-124">Par exemple, si vous https://lync.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de Lync.contoso.com en Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2748e-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="2748e-125">Si vous avez modifié l’URL simple https://lync.contoso.com/Meet vers https://lync.contoso.com/Meetings, l’url de base de Lync.contoso.com reste la même, de sorte qu’aucune modification de certificat ou de DNS n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2748e-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="2748e-126">Chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter l’applet de commande <STRONG>Enable-CsComputer</STRONG> sur chaque directeur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="2748e-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2748e-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2748e-127">See Also</span></span>


[<span data-ttu-id="2748e-128">Planification des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2748e-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

