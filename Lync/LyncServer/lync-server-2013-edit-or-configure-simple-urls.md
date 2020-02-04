---
title: 'Lync Server 2013 : Modification ou configuration des URL simples'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="1e204-102">Modification ou configuration des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e204-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e204-103">_**Dernière modification de la rubrique :** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="1e204-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="1e204-104">Cette procédure ne nécessite pas d’appartenance à un administrateur local ou à un groupe de domaines privilégiés.</span><span class="sxs-lookup"><span data-stu-id="1e204-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="1e204-105">Vous devez vous connecter à un ordinateur en tant qu’utilisateur standard.</span><span class="sxs-lookup"><span data-stu-id="1e204-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="1e204-106">Lync Server 2013 utilise des URL simples pour diriger les appels internes et externes vers des services du serveur frontal ou du réalisateur, s’il a été déployé.</span><span class="sxs-lookup"><span data-stu-id="1e204-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="1e204-107">Pour plus d’informations sur les URL simples, voir [planification d’URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1e204-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="1e204-108">Vous pouvez sélectionner le format de vos URL simples à partir de plusieurs options.</span><span class="sxs-lookup"><span data-stu-id="1e204-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="1e204-109">Pour plus d’informations sur ces options, voir [configurations DNS requises pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1e204-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="1e204-110">Par défaut, les URL simples seront configurées sous la forme (par exemple, l’URL de connexion simple) : https://dialin.\<SIP Domain\></span><span class="sxs-lookup"><span data-stu-id="1e204-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="1e204-111">Pour configurer des URL simples</span><span class="sxs-lookup"><span data-stu-id="1e204-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="1e204-112">Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud du **serveur Lync** , puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1e204-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="1e204-113">Dans le volet **URL simples**, sélectionnez **URL d’accès téléphonique :** (Dial-In) ou **URL de réunion :** (Meet) pour modifier l’URL, puis cliquez sur **Modifier l’URL**.</span><span class="sxs-lookup"><span data-stu-id="1e204-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="1e204-114">Mettez à jour l’URL comme vous le souhaitez puis cliquez sur **OK** pour enregistrer l’URL modifiée.</span><span class="sxs-lookup"><span data-stu-id="1e204-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="1e204-115">L’exemple présenté ici a modifié l’URL d’accès à la https://pool01.contoso.net/dialinConférence rendez-vous en.</span><span class="sxs-lookup"><span data-stu-id="1e204-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="1e204-116">Modifiez l’URL Meet en procédant de la même manière, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1e204-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="1e204-117">Pour définir l’URL simple Admin facultative</span><span class="sxs-lookup"><span data-stu-id="1e204-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="1e204-118">Dans le générateur de topologie, cliquez avec le bouton droit sur le nœud du **serveur Lync** , puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="1e204-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="1e204-119">Dans la zone **URL d’accès administratif** , entrez l’URL de votre choix pour l’accès administratif au panneau de configuration de Lync Server 2013, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e204-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1e204-120">Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="1e204-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="1e204-121">L’option la plus simple est <STRONG> https://admin.</STRONG> &lt;Domain&gt;(domaine).</span><span class="sxs-lookup"><span data-stu-id="1e204-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1e204-122">Si vous changez une URL simple après son déploiement initial, vous devez savoir quels changements impactent vos enregistrements et certificats DNS pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="1e204-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="1e204-123">Si le changement a un impact sur la base d’une URL simple, vous devez également modifier les enregistrements DNS et les certificats.</span><span class="sxs-lookup"><span data-stu-id="1e204-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="1e204-124">Par exemple, si vous https://lync.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de Lync.contoso.com à Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1e204-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="1e204-125">Si vous avez changé l’URL simple https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingsà, l’url de base de Lync.contoso.com reste inchangée et aucune modification du DNS ou du certificat n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1e204-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="1e204-126">Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter l’applet de passe <STRONG>Enable-CsComputer</STRONG> sur chaque réalisateur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="1e204-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e204-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e204-127">See Also</span></span>


[<span data-ttu-id="1e204-128">Planification des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e204-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

