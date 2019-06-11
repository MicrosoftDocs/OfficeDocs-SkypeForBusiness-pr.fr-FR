---
title: 'Lync Server 2013: afficher les informations du code confidentiel d’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb3d854f68e9e22e8d8fb1fa0d26f555f09af1ae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a><span data-ttu-id="9c6d0-102">Afficher les informations de code confidentiel utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c6d0-102">View user PIN information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c6d0-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9c6d0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9c6d0-104">Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur de Lync Server 2013 avec les informations d’identification d’AD DS (Active Directory Domain Services) nécessite un code confidentiel (PIN).</span><span class="sxs-lookup"><span data-stu-id="9c6d0-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="9c6d0-105">Vous pouvez afficher les informations du code confidentiel d’un utilisateur à partir du panneau de configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-105">You can view a user’s PIN information from Lync Server 2013 Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c6d0-106">Vous pouvez afficher les informations de statut du code confidentiel, qui indiquent, par exemple, si le code confidentiel a été défini ou lorsqu’il a été modifié pour la dernière fois, mais vous ne pouvez pas voir le code confidentiel actif en consultant le statut de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-106">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="9c6d0-107">Si un utilisateur a perdu son code confidentiel, vous pouvez le réinitialiser en suivant les procédures décrites dans la rubrique <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="9c6d0-107">If a user has lost their PIN, you can reset it by following the procedures in <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Set a user's dial-in conferencing PIN in Lync Server 2013</A></span></span>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="9c6d0-108">Pour afficher le code confidentiel d’un utilisateur dans le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9c6d0-108">To view a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9c6d0-109">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9c6d0-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9c6d0-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9c6d0-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9c6d0-112">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-112">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9c6d0-113">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c6d0-113">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9c6d0-114">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9c6d0-115">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="9c6d0-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9c6d0-116">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="9c6d0-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9c6d0-117">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-117">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9c6d0-118">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-118">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9c6d0-119">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Différent de**).</span><span class="sxs-lookup"><span data-stu-id="9c6d0-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9c6d0-120">Selon la propriété utilisateur sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-120">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="9c6d0-121">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-121">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="9c6d0-122">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-122">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9c6d0-p104">Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur <STRONG>Action</STRONG>, puis sur <STRONG>Déverrouiller le code confidentiel</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="9c6d0-125">Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Afficher le statut du code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-125">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9c6d0-126">Affichage des informations de code confidentiel utilisateur à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c6d0-126">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9c6d0-127">Vous pouvez afficher les informations relatives au code confidentiel de l’utilisateur à l’aide de l’applet de commande Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-127">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="9c6d0-128">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c6d0-128">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9c6d0-129">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="9c6d0-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-user-pin-information"></a><span data-ttu-id="9c6d0-130">Pour afficher les informations relatives au code confidentiel de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="9c6d0-130">To view user PIN information</span></span>

  - <span data-ttu-id="9c6d0-131">Pour afficher les informations de code confidentiel d’un utilisateur, tapez une commande similaire à celle qui suit dans Lync Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="9c6d0-131">To view PIN information for a user, type a command similar to the following in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    <span data-ttu-id="9c6d0-132">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="9c6d0-132">That will return information similar to this:</span></span>
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

<span data-ttu-id="9c6d0-133">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .</span><span class="sxs-lookup"><span data-stu-id="9c6d0-133">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c6d0-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c6d0-134">See Also</span></span>


[<span data-ttu-id="9c6d0-135">Définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c6d0-135">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[<span data-ttu-id="9c6d0-136">Verrouiller ou déverrouiller un code confidentiel d’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c6d0-136">Lock or unlock a user PIN in Lync Server 2013</span></span>](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

