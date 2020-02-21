---
title: 'Lync Server 2013 : activation ou désactivation de l’accès des utilisateurs anonymes'
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
ms.openlocfilehash: 076cfd8b787c85ba94d3538c5510d7c12ca11b22
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="fb925-102">Activer ou désactiver l’accès des utilisateurs anonymes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb925-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb925-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fb925-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fb925-104">Les utilisateurs anonymes sont des utilisateurs qui ne disposent pas d’un compte d’utilisateur dans les services de domaine Active Directory de votre organisation ou dans un domaine fédéré pris en charge, mais qui peuvent être invités à participer à distance à une conférence locale.</span><span class="sxs-lookup"><span data-stu-id="fb925-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="fb925-105">En autorisant la participation anonyme aux réunions, vous autorisez les utilisateurs anonymes (c’est-à-dire, les utilisateurs dont l’identité est vérifiée par le biais de la réunion ou de la clé de conférence uniquement) pour participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="fb925-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="fb925-106">Autoriser la participation anonyme nécessite de l’activer pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fb925-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="fb925-107">Si vous souhaitez ultérieurement empêcher temporairement ou définitivement l’accès par des utilisateurs anonymes, vous pouvez le désactiver pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fb925-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="fb925-108">Utilisez la procédure décrite dans cette section pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fb925-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb925-109">En activant l’accès des utilisateurs anonymes pour votre organisation, vous spécifiez uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès par des utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="fb925-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="fb925-110">Les utilisateurs anonymes ne peuvent pas participer à des réunions dans votre organisation tant que vous n’avez pas configuré au moins une stratégie de conférence et que vous l’appliquez à un ou plusieurs utilisateurs ou groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fb925-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="fb925-111">Les seuls utilisateurs qui peuvent inviter des utilisateurs anonymes à des réunions sont les utilisateurs auxquels une stratégie de conférence est configurée pour prendre en charge les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="fb925-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="fb925-112">Pour plus d’informations sur la configuration des stratégies de conférence pour la prise en charge des utilisateurs anonymes, consultez la rubrique <A href="lync-server-2013-conferencing-policies.md">stratégies de conférence dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fb925-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="fb925-113">Pour activer ou désactiver l’accès des utilisateurs anonymes pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="fb925-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="fb925-114">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="fb925-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fb925-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fb925-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fb925-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fb925-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fb925-117">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="fb925-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="fb925-118">Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="fb925-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="fb925-119">Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb925-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="fb925-120">Pour activer l’accès utilisateur anonyme pour votre organisation, activez la case à cocher **autoriser les communications avec des utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="fb925-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="fb925-121">Pour désactiver l’accès des utilisateurs anonymes pour votre organisation, désactivez la case à cocher **autoriser les communications avec des utilisateurs anonymes** .</span><span class="sxs-lookup"><span data-stu-id="fb925-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="fb925-122">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="fb925-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fb925-123">Activation ou désactivation de l’accès des utilisateurs anonymes à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb925-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fb925-124">Vous pouvez gérer l’accès des utilisateurs anonymes à l’aide de Windows PowerShell et de la cmdlet **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fb925-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="fb925-125">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fb925-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fb925-126">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="fb925-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="fb925-127">Pour activer l’accès des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="fb925-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="fb925-128">Pour activer l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($true) :</span><span class="sxs-lookup"><span data-stu-id="fb925-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="fb925-129">Pour désactiver l’accès des utilisateurs anonymes</span><span class="sxs-lookup"><span data-stu-id="fb925-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="fb925-130">Pour désactiver l’accès des utilisateurs anonymes, définissez la valeur de la propriété **AllowAnonymousUsers** sur false ($false) :</span><span class="sxs-lookup"><span data-stu-id="fb925-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb925-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb925-131">See Also</span></span>


[<span data-ttu-id="fb925-132">Référence des paramètres de stratégie de conférence pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb925-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

