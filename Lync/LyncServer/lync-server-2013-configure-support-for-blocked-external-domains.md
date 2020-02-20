---
title: 'Lync Server 2013 : configuration de la prise en charge des domaines externes bloqués'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf1b7b1da08a8c573b782474d7f2deb4ea9358a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="603cb-102">Configurer la prise en charge des domaines externes bloqués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="603cb-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="603cb-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="603cb-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="603cb-104">Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez gérer les domaines qui n’auront pas accès à la fédération au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="603cb-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="603cb-105">La liste des domaines bloqués sert de liste rouge (liste d’entrées explicites qui doivent être interdites) et s’applique à la découverte des domaines fédérés, si cette option est activée.</span><span class="sxs-lookup"><span data-stu-id="603cb-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="603cb-106">Pour plus d’informations, consultez la rubrique [activation ou désactivation de la découverte de partenaires de Fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="603cb-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="603cb-p102">Empêchez un ou plusieurs domaines externes de se connecter à votre organisation. Pour ce faire, ajoutez le domaine à la liste des domaines bloqués.</span><span class="sxs-lookup"><span data-stu-id="603cb-p102">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="603cb-109">Pour ajouter un domaine externe à la liste des domaines bloqués</span><span class="sxs-lookup"><span data-stu-id="603cb-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="603cb-110">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="603cb-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="603cb-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="603cb-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="603cb-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="603cb-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="603cb-113">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**.</span><span class="sxs-lookup"><span data-stu-id="603cb-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="603cb-114">Cliquez sur **Domaines fédérés**, sur **Nouveau**, puis sur **Domaine bloqué**.</span><span class="sxs-lookup"><span data-stu-id="603cb-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="603cb-115">Dans **Nouveaux domaines fédérés**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="603cb-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="603cb-116">Dans **Nom de domaine complet (ou FQDN)**, tapez le nom de domaine du partenaire fédéré que vous souhaitez bloquer.</span><span class="sxs-lookup"><span data-stu-id="603cb-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="603cb-117">Il peut contenir jusqu’à 256 caractères.</span><span class="sxs-lookup"><span data-stu-id="603cb-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="603cb-p104">La recherche du nom de domaine du partenaire fédéré établit une correspondance à partir du suffixe. Par exemple, si vous tapez <STRONG>contoso.com</STRONG>, la recherche renverra également le domaine <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="603cb-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="603cb-120">Un domaine de partenaire fédéré ne peut pas être simultanément bloqué et autorisé.</span><span class="sxs-lookup"><span data-stu-id="603cb-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="603cb-121">Lync Server 2013 empêche ce problème de se produire afin que vous n’ayez pas besoin de synchroniser vos listes.</span><span class="sxs-lookup"><span data-stu-id="603cb-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="603cb-122">(Facultatif) Dans **Commentaire**, tapez les informations sur cette configuration que vous voulez partager avec les autres administrateurs système.</span><span class="sxs-lookup"><span data-stu-id="603cb-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="603cb-123">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="603cb-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="603cb-124">Répétez les étapes 4 à 6 pour chaque partenaire fédéré que vous souhaitez bloquer.</span><span class="sxs-lookup"><span data-stu-id="603cb-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="603cb-125">Pour activer l’accès des utilisateurs fédérés, vous devez aussi activer la prise en charge de l’accès des utilisateurs fédérés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="603cb-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="603cb-126">Pour plus d’informations, consultez la rubrique [activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="603cb-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="603cb-127">De plus, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à collaborer avec les utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="603cb-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="603cb-128">Pour plus d’informations, consultez la rubrique [configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="603cb-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

