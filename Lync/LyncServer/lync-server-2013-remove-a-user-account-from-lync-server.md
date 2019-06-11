---
title: 'Lync Server 2013: supprimer un compte d’utilisateur de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780e19fb608855d9c820285cc87582787ff896d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="fee8e-102">Supprimer un compte d’utilisateur de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fee8e-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fee8e-103">_**Dernière modification de la rubrique:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="fee8e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="fee8e-104">Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur déjà ajouté dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fee8e-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fee8e-105">La suppression d’un utilisateur entraîne la perte des paramètres que vous avez configurés pour le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fee8e-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="fee8e-106">Si vous voulez désactiver temporairement un compte d’utilisateur à la place, reportez-vous à la rubrique <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">désactiver ou réactiver un compte d’utilisateur pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fee8e-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="fee8e-107">Pour supprimer un compte d’utilisateur à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="fee8e-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="fee8e-108">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="fee8e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fee8e-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fee8e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fee8e-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fee8e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fee8e-111">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="fee8e-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fee8e-112">Dans la boîte de dialogue **Rechercher des utilisateurs** , entrez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité, adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur que vous souhaitez désactiver ou réactiver. puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="fee8e-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="fee8e-113">Dans la table, cliquez sur le compte d’utilisateur que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="fee8e-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="fee8e-114">Dans le menu **action** , sélectionnez **supprimer de Lync Server**et une boîte de dialogue s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fee8e-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="fee8e-115">Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fee8e-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fee8e-116">Suppression de comptes d’utilisateur à l’aide des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fee8e-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fee8e-117">Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de passe Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="fee8e-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="fee8e-118">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fee8e-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="fee8e-119">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="fee8e-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="fee8e-120">Pour supprimer un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="fee8e-120">To remove a user account</span></span>

  - <span data-ttu-id="fee8e-121">Pour supprimer un compte d’utilisateur, utilisez l’applet de passe Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="fee8e-121">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="fee8e-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fee8e-122">For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="fee8e-123">Après avoir exécuté cette commande, il est impossible de réactiver le compte et ses paramètres précédents.</span><span class="sxs-lookup"><span data-stu-id="fee8e-123">After this command has run there is no way to re-enable the account and its previous settings.</span></span> <span data-ttu-id="fee8e-124">Au lieu de cela, vous devez utiliser l’applet de passe Enable-CsUser pour créer un nouveau compte pour Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="fee8e-124">Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="fee8e-125">Pour plus d’informations, reportez-vous à la rubrique d’aide de l’applet de la cmdlet [Disable-Csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="fee8e-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fee8e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fee8e-126">See Also</span></span>


[<span data-ttu-id="fee8e-127">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fee8e-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="fee8e-128">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fee8e-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

