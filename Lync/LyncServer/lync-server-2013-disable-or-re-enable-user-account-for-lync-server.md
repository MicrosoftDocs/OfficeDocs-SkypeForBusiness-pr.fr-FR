---
title: 'Lync Server 2013 : désactivation ou réactivation du compte d’utilisateur pour Lync Server'
description: 'Lync Server 2013 : désactivez ou réactivez le compte d’utilisateur pour Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b30d83d7a7f38b84f8e669ac06947eebf4a8545
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568170"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="2bb5c-103">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bb5c-103">Disable or re-enable user account for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bb5c-104">_**Dernière modification de la rubrique :** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="2bb5c-104">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="2bb5c-105">Vous pouvez utiliser la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Lync Server 2013 sans perdre les paramètres Lync Server que vous avez configurés pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-105">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="2bb5c-106">Étant donné que vous ne perdez pas les paramètres de compte d’utilisateur Lync Server, vous pouvez réactiver un compte d’utilisateur précédemment activé sans avoir à reconfigurer le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-106">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2bb5c-107">La simple désactivation d’un compte d’utilisateur dans Active Directory n' <STRONG>empêchera pas</STRONG> un utilisateur de se connecter à ou d’utiliser Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-107">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="2bb5c-108">En effet, Lync utilise l’authentification de certificat qui rationalise le processus d’authentification, et ces certificats clients sont valides pendant 180 jours.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-108">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="2bb5c-109">Si vous souhaitez arrêter les comptes Active Directory désactivés qui ont été activés pour que Lync ait accès à Lync Server, vous devez utiliser l’applet de commande <STRONG>Disable-Csuser</STRONG> ou utiliser le <STRONG>panneau de configuration Lync Server</STRONG> comme indiqué dans cet article.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-109">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="2bb5c-110">Une fois que l’utilisateur est désactivé dans Lync et que le magasin central de gestion a été répliqué dans l’environnement, les utilisateurs ne pourront plus se connecter.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-110">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="2bb5c-111">En outre, les utilisateurs qui sont connectés seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-111">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="2bb5c-112">Pour désactiver ou réactiver un compte d’utilisateur précédemment activé pour Lync Server</span><span class="sxs-lookup"><span data-stu-id="2bb5c-112">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="2bb5c-113">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2bb5c-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2bb5c-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2bb5c-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2bb5c-116">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="2bb5c-117">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="2bb5c-118">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-118">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="2bb5c-119">Dans le menu **Action**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2bb5c-119">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="2bb5c-120">Pour désactiver temporairement le compte d’utilisateur pour Lync Server 2013, cliquez sur **désactiver temporairement pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-120">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="2bb5c-121">Pour activer le compte d’utilisateur pour Lync Server 2013, cliquez sur **réactiver pour Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-121">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="2bb5c-122">Utilisation de Windows PowerShell pour désactiver ou réactiver des comptes d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="2bb5c-122">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="2bb5c-123">Les comptes d’utilisateur peuvent être temporairement désactivés, puis réactivés ultérieurement à l’aide de la cmdlet **Set-Csuser** .</span><span class="sxs-lookup"><span data-stu-id="2bb5c-123">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="2bb5c-124">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bb5c-124">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2bb5c-125">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="2bb5c-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="2bb5c-126">Pour désactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="2bb5c-126">To disable a user account</span></span>

  - <span data-ttu-id="2bb5c-127">Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur False ($False).</span><span class="sxs-lookup"><span data-stu-id="2bb5c-127">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="2bb5c-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2bb5c-128">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="2bb5c-129">Pour réactiver un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="2bb5c-129">To re-enable a user account</span></span>

  - <span data-ttu-id="2bb5c-130">Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur True ($True).</span><span class="sxs-lookup"><span data-stu-id="2bb5c-130">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="2bb5c-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2bb5c-131">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="2bb5c-132">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-Csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="2bb5c-132">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2bb5c-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2bb5c-133">See Also</span></span>


[<span data-ttu-id="2bb5c-134">Ajouter et activer un compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bb5c-134">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="2bb5c-135">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bb5c-135">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

