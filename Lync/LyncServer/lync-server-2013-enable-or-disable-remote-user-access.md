---
title: 'Lync Server 2013 : Activation ou désactivation de l’accès des utilisateurs distants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="6d44f-102">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d44f-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d44f-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6d44f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6d44f-104">Les utilisateurs distants sont les utilisateurs de votre organisation qui ont une identité Active Directory persistante au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="6d44f-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="6d44f-105">Les utilisateurs distants se connectent souvent à Lync Server depuis l’extérieur de votre réseau via un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d44f-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="6d44f-106">Les utilisateurs distants incluent des employés travaillant à la maison ou en déplacement, ainsi que d’autres travailleurs distants, tels que des fournisseurs approuvés qui ont reçu des informations d’identification d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6d44f-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="6d44f-107">Si vous autorisez l’accès des utilisateurs distants pour les utilisateurs distants, les utilisateurs distants pris en charge se connectent via Internet et n’ont pas besoin de se connecter à l’aide d’un VPN pour collaborer avec des utilisateurs internes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d44f-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="6d44f-108">Pour prendre en charge l’accès des utilisateurs distants, vous devez activer l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="6d44f-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="6d44f-109">Lorsque vous activez l’accès des utilisateurs distants, vous les activez pour l’ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d44f-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="6d44f-110">Si vous souhaitez empêcher l’accès des utilisateurs distants de manière temporaire ou définitive, vous pouvez le désactiver pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d44f-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="6d44f-111">Suivez la procédure décrite dans cette section pour activer ou désactiver l’accès des utilisateurs distants au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6d44f-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d44f-112">L’activation de l’accès des utilisateurs distants indique uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge les communications avec les utilisateurs distants, mais qu’ils ne peuvent pas participer à la messagerie instantanée ou aux conférences au sein de votre organisation tant que vous n’avez pas également configuré au moins une stratégie pour gérer l’utilisation de l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="6d44f-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="6d44f-113">Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6d44f-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="6d44f-114">Le niveau de priorité de la stratégie de serveur Lync est défini comme suit: la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence).</span><span class="sxs-lookup"><span data-stu-id="6d44f-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="6d44f-115">Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="6d44f-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="6d44f-116">Pour plus d’informations sur la configuration des stratégies pour l’utilisation de l’accès des utilisateurs distants, voir <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6d44f-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="6d44f-117">Pour activer ou désactiver l’accès des utilisateurs distants pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="6d44f-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="6d44f-118">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="6d44f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d44f-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d44f-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6d44f-120">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6d44f-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6d44f-121">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="6d44f-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="6d44f-122">Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="6d44f-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6d44f-123">Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="6d44f-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="6d44f-124">Pour autoriser l’accès des utilisateurs distants pour votre organisation, activez la case à cocher **activer l’accès aux utilisateurs** distants.</span><span class="sxs-lookup"><span data-stu-id="6d44f-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="6d44f-125">Pour désactiver l’accès des utilisateurs distants pour votre organisation, décochez la case **activer l’accès distant aux utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="6d44f-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="6d44f-126">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="6d44f-126">Click **Commit**.</span></span>

<span data-ttu-id="6d44f-127">Pour permettre aux utilisateurs distants de se connecter à des serveurs exécutant Lync Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="6d44f-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="6d44f-128">Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="6d44f-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6d44f-129">Activation ou désactivation de l’accès des utilisateurs distants à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d44f-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6d44f-130">L’accès des utilisateurs distants peut être géré à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6d44f-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="6d44f-131">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d44f-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6d44f-132">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="6d44f-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="6d44f-133">Pour autoriser l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="6d44f-133">To enable remote user access</span></span>

  - <span data-ttu-id="6d44f-134">Pour autoriser l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($true):</span><span class="sxs-lookup"><span data-stu-id="6d44f-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="6d44f-135">Pour désactiver l’accès des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="6d44f-135">To disable remote user access</span></span>

  - <span data-ttu-id="6d44f-136">Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur false ($false):</span><span class="sxs-lookup"><span data-stu-id="6d44f-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

