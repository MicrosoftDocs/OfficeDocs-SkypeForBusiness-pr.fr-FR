---
title: 'Lync Server 2013 : affecter une stratégie vocale par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3818ae60cd9ae3e8537bf17bee01508e32dfa26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723404"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="9958b-102">Affecter une stratégie vocale par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9958b-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="9958b-103">Les stratégies de voix globale et de niveau site sont automatiquement affectées à tous les comptes d’utilisateurs Lync Server 2013 activés pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9958b-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="9958b-104">Vous pouvez également attribuer des stratégies vocales à des utilisateurs spécifiques à l’aide du panneau de configuration de Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9958b-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="9958b-105">Suivez les procédures décrites dans cette rubrique pour affecter explicitement des stratégies par utilisateur aux utilisateurs de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9958b-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="9958b-106">Pour attribuer une stratégie vocale spécifique à l’utilisateur à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9958b-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9958b-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9958b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9958b-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9958b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9958b-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9958b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9958b-110">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.</span><span class="sxs-lookup"><span data-stu-id="9958b-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="9958b-111">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="9958b-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9958b-112">Dans **modifier l’utilisateur de Lync Server** sous **stratégie vocale**, sélectionnez la stratégie d’utilisateur que vous voulez appliquer.</span><span class="sxs-lookup"><span data-stu-id="9958b-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="9958b-113">Les <STRONG> &lt;paramètres&gt; automatiques</STRONG> appliquent le serveur par défaut ou les paramètres de stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="9958b-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9958b-114">Attribution d’une stratégie vocale par utilisateur à l’aide des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9958b-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9958b-115">Vous pouvez affecter des stratégies vocales par utilisateur à l’aide de Windows PowerShell et de l’applet **de passe Grant-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="9958b-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="9958b-116">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9958b-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9958b-117">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="9958b-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="9958b-118">Pour attribuer une stratégie vocale par utilisateur à un utilisateur unique</span><span class="sxs-lookup"><span data-stu-id="9958b-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="9958b-119">La commande suivante affecte le RedmondVoicePolicy de la stratégie vocale par utilisateur à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="9958b-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="9958b-120">Pour affecter une stratégie vocale par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9958b-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="9958b-121">Cette commande affecte le FinanceVoicePolicy de la stratégie vocale par utilisateur à tous les utilisateurs disposant de comptes dans l’unité d’organisation Finance dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9958b-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="9958b-122">Pour plus d’informations sur le paramètre de l’unité d’organisation utilisée dans cette commande, voir la documentation relative à l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="9958b-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="9958b-123">Pour annuler l’affectation d’une stratégie vocale par utilisateur</span><span class="sxs-lookup"><span data-stu-id="9958b-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="9958b-124">La commande suivante réattribue toutes les stratégies vocales par utilisateur précédemment affectées à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="9958b-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="9958b-125">Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local.</span><span class="sxs-lookup"><span data-stu-id="9958b-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="9958b-126">Une stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="9958b-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="9958b-127">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="9958b-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="9958b-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9958b-128">See Also</span></span>


[<span data-ttu-id="9958b-129">Désactiver un utilisateur pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9958b-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="9958b-130">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="9958b-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

