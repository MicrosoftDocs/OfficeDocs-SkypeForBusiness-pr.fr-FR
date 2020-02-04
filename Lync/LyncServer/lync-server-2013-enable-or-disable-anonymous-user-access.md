---
title: 'Lync Server 2013 : Activation ou désactivation de l’accès des utilisateurs anonymes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38d0d9f50ff06b2f7eb95944d9214c2c4c64a5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="70ac5-102">Activation ou désactivation de l’accès des utilisateurs anonymes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70ac5-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70ac5-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="70ac5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="70ac5-104">Les utilisateurs anonymes sont des utilisateurs qui n’ont pas de compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou qui sont invités à participer à distance dans une conférence locale.</span><span class="sxs-lookup"><span data-stu-id="70ac5-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="70ac5-105">La participation anonyme aux réunions vous permet d’activer les utilisateurs anonymes (c’est-à-dire les utilisateurs dont l’identité est vérifiée uniquement via la réunion ou la clé de conférence) pour participer aux réunions.</span><span class="sxs-lookup"><span data-stu-id="70ac5-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="70ac5-106">L’activation de la participation anonyme exige de l’activer pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="70ac5-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="70ac5-107">Si vous souhaitez suspendre temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="70ac5-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="70ac5-108">Pour activer ou désactiver l’accès anonyme aux utilisateurs de votre organisation, suivez la procédure décrite dans cette section.</span><span class="sxs-lookup"><span data-stu-id="70ac5-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70ac5-109">L’activation de l’accès anonyme aux utilisateurs de votre organisation consiste uniquement à indiquer que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès par des utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="70ac5-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="70ac5-110">Les utilisateurs anonymes ne peuvent pas participer à une réunion au sein de votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="70ac5-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="70ac5-111">Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont les utilisateurs auxquels une stratégie de conférence est affectée et qui est configurée pour prendre en charge les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="70ac5-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="70ac5-112">Pour plus d’informations sur la configuration des stratégies de conférence pour la prise en charge de l’invitation d’utilisateurs anonymes, voir <A href="lync-server-2013-conferencing-policies.md">stratégies de conférence dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="70ac5-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="70ac5-113">Pour activer ou désactiver l’accès anonyme aux utilisateurs de votre organisation</span><span class="sxs-lookup"><span data-stu-id="70ac5-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="70ac5-114">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="70ac5-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="70ac5-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70ac5-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="70ac5-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="70ac5-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="70ac5-117">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis cliquez sur **configuration d’Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="70ac5-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="70ac5-118">Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="70ac5-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="70ac5-119">Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="70ac5-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="70ac5-120">Pour activer l’accès anonyme aux utilisateurs de votre organisation, activez la case à cocher **activer les communications avec les utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="70ac5-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="70ac5-121">Pour désactiver l’accès anonyme aux utilisateurs de votre organisation, décochez la case **activer les communications avec les utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="70ac5-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="70ac5-122">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="70ac5-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="70ac5-123">Activation ou désactivation de l’accès utilisateur anonyme à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70ac5-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="70ac5-124">Vous pouvez gérer l’accès utilisateur anonyme à l’aide de Windows PowerShell et de l’applet **de connexion Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="70ac5-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="70ac5-125">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70ac5-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="70ac5-126">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="70ac5-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="70ac5-127">Pour autoriser l’accès des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="70ac5-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="70ac5-128">Pour autoriser l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($true) :</span><span class="sxs-lookup"><span data-stu-id="70ac5-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="70ac5-129">Pour désactiver l’accès des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="70ac5-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="70ac5-130">Pour désactiver l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur false ($false) :</span><span class="sxs-lookup"><span data-stu-id="70ac5-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70ac5-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70ac5-131">See Also</span></span>


[<span data-ttu-id="70ac5-132">Référence des paramètres de stratégie de conférence pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70ac5-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

