---
title: 'Lync Server 2013 : suppression d’un compte d’utilisateur de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11a02be3dc013ff385adfe9e0437bb5b430b905c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="f737e-102">Supprimer un compte d’utilisateur de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f737e-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f737e-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f737e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f737e-104">Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur ajouté précédemment dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f737e-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f737e-105">La suppression d’un utilisateur entraînera la perte de tous les paramètres associés au compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f737e-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="f737e-106">Si vous souhaitez désactiver temporairement un compte d’utilisateur, reportez-vous à la rubrique désactiver ou réactiver le <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">compte d’utilisateur pour Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f737e-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="f737e-107">Pour supprimer un compte d’utilisateur à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f737e-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f737e-108">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f737e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f737e-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f737e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f737e-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f737e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f737e-111">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f737e-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f737e-112">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f737e-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="f737e-113">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="f737e-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="f737e-114">Dans le menu **Action**, sélectionnez **Supprimer de Lync Server** et une boîte de dialogue apparaît.</span><span class="sxs-lookup"><span data-stu-id="f737e-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="f737e-115">Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f737e-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f737e-116">Suppression de comptes d’utilisateur à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f737e-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f737e-117">Vous pouvez supprimer des comptes d’utilisateurs à l’aide de l’applet de commande Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="f737e-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="f737e-118">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f737e-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="f737e-119">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="f737e-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="f737e-120">Pour supprimer un compte d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="f737e-120">To remove a user account</span></span>

  - <span data-ttu-id="f737e-p104">Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f737e-p104">To remove a user account, use the Disable-CsUser cmdlet. For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="f737e-p105">Une fois cette commande exécutée, il n’y a aucun moyen de réactiver le compte et ses anciens paramètres. En revanche, vous pouvez utiliser l’applet de commande Enable-CsUser pour créer un tout nouveau compte pour Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f737e-p105">After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="f737e-125">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Disable-Csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="f737e-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f737e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f737e-126">See Also</span></span>


[<span data-ttu-id="f737e-127">Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f737e-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="f737e-128">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f737e-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

