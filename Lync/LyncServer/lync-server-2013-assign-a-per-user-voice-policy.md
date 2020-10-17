---
title: 'Lync Server 2013 : affecter une stratégie de voix par utilisateur'
description: 'Lync Server 2013 : affectez une stratégie de voix par utilisateur.'
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
ms.openlocfilehash: e7ea0b171e10302b4c466187c54324cc2548e821
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563560"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="70815-103">Affecter une stratégie de voix par utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70815-103">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="70815-104">Les stratégies de voix globale et de niveau site sont automatiquement attribuées à tous les comptes d’utilisateur Lync Server 2013 qui sont activés pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="70815-104">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="70815-105">Vous pouvez également affecter des stratégies de voix à des utilisateurs spécifiques à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="70815-105">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="70815-106">Utilisez les procédures de cette rubrique pour attribuer explicitement des stratégies par utilisateur aux utilisateurs de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70815-106">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="70815-107">Pour affecter une stratégie de voix spécifique à l’utilisateur à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="70815-107">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="70815-108">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="70815-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="70815-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70815-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="70815-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="70815-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="70815-111">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="70815-111">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="70815-112">Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="70815-112">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="70815-113">Dans **Modifier l’utilisateur Lync Server** sous **Stratégie de voix**, sélectionnez la stratégie d’utilisateur à appliquer.</span><span class="sxs-lookup"><span data-stu-id="70815-113">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="70815-114">Les paramètres <STRONG> &lt; automatiques &gt; </STRONG> appliquent les paramètres de stratégie globale ou de serveur par défaut.</span><span class="sxs-lookup"><span data-stu-id="70815-114">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assign-per-user-voice-policies"></a><span data-ttu-id="70815-115">Affecter des stratégies de voix par utilisateur</span><span class="sxs-lookup"><span data-stu-id="70815-115">Assign per-user voice policies</span></span>

<span data-ttu-id="70815-116">Vous pouvez affecter des stratégies de voix par utilisateur à l’aide de Windows PowerShell et de la cmdlet **Grant-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="70815-116">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="70815-117">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70815-117">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="70815-118">Pour en savoir plus sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, lisez ce billet de blog Windows PowerShell Lync Server : [démarrage rapide : gestion de Microsoft Lync server 2010 à l’aide de PowerShell à distance](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="70815-118">To learn about using remote Windows PowerShell to connect to Lync Server, read this Lync Server Windows PowerShell blog post: [Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span>

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="70815-119">Affecter une stratégie de voix par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="70815-119">Assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="70815-120">La commande suivante assigne la stratégie de voix par utilisateur RedmondVoicePolicy à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="70815-120">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="70815-121">Affecter une stratégie de voix par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="70815-121">Assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="70815-122">Cette commande assigne la stratégie de voix par utilisateur FinanceVoicePolicy à tous les utilisateurs qui ont des comptes dans l’unité d’organisation Finance dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70815-122">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="70815-123">Pour plus d’informations sur le paramètre OU utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="70815-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a><span data-ttu-id="70815-124">Annuler l’affectation d’une stratégie de voix par utilisateur</span><span class="sxs-lookup"><span data-stu-id="70815-124">Unassign a per-user voice policy</span></span>

  - <span data-ttu-id="70815-p105">La commande suivante annule l’assignation d’une stratégie de voix par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="70815-p105">The following command unassigns any per-user voice policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="70815-128">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="70815-128">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="70815-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70815-129">See Also</span></span>


[<span data-ttu-id="70815-130">Désactivation d’un utilisateur pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70815-130">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="70815-131">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="70815-131">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

