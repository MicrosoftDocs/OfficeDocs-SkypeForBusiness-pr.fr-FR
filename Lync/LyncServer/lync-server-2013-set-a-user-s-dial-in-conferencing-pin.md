---
title: 'Lync Server 2013 : définition du code confidentiel de conférence rendez-vous d’un utilisateur'
description: 'Lync Server 2013 : définir le code confidentiel de conférence rendez-vous d’un utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 238c2a72da81a53b409d81c1b91c885f1ddabcbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543330"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="c1ecb-103">Définir le code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1ecb-103">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1ecb-104">_**Dernière modification de la rubrique :** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="c1ecb-104">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="c1ecb-105">Pour joindre une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur Lync Server 2013 avec les informations d’identification des services de domaine Active Directory (AD DS) nécessite un code confidentiel (PIN).</span><span class="sxs-lookup"><span data-stu-id="c1ecb-105">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="c1ecb-106">Si un utilisateur oublie le code confidentiel de la Conférence rendez-vous ou n’a pas défini le code confidentiel à l’aide de Lync Server, vous pouvez définir le code confidentiel de l’utilisateur à partir du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="c1ecb-107">Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-107">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1ecb-108">Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies en tant que stratégie.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-108">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="c1ecb-109">En plus de la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-109">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="c1ecb-110">Pour plus d’informations sur la configuration d’une stratégie de code confidentiel, voir <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurer des règles de code confidentiel (pin) pour les conférences rendez-vous dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-110">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="c1ecb-111">Pour définir le code confidentiel d’un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c1ecb-111">To set a user’s PIN</span></span>

1.  <span data-ttu-id="c1ecb-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c1ecb-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c1ecb-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c1ecb-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c1ecb-115">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c1ecb-116">Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1ecb-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="c1ecb-117">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="c1ecb-118">Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).</span><span class="sxs-lookup"><span data-stu-id="c1ecb-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="c1ecb-119">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="c1ecb-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="c1ecb-120">Cliquez sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="c1ecb-121">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="c1ecb-122">Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).</span><span class="sxs-lookup"><span data-stu-id="c1ecb-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="c1ecb-123">Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-123">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="c1ecb-124">Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="c1ecb-125">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-125">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1ecb-p104">Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur <STRONG>Action</STRONG>, puis sur <STRONG>Déverrouiller le code confidentiel</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="c1ecb-128">Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Définir le code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-128">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="c1ecb-129">Dans la boîte de dialogue **Définir le code confidentiel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1ecb-129">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="c1ecb-130">Pour permettre à Lync Server 2013 de générer le code confidentiel de l’utilisateur, sélectionnez **générer automatiquement un code confidentiel valide** (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="c1ecb-130">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="c1ecb-131">Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-131">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="c1ecb-132">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-132">Click **OK**.</span></span>

9.  <span data-ttu-id="c1ecb-133">Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1ecb-133">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="c1ecb-134">Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-134">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="c1ecb-p105">Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est automatiquement copié dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="c1ecb-138">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-138">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c1ecb-139">Affectation d’un code confidentiel d’utilisateur à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1ecb-139">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c1ecb-140">Vous pouvez également attribuer des numéros de code confidentiel à l’aide de la cmdlet Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-140">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="c1ecb-141">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-141">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c1ecb-142">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="c1ecb-142">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="c1ecb-143">Affectation automatique d’un code confidentiel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c1ecb-143">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="c1ecb-144">La commande suivante affecte un code confidentiel à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-144">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="c1ecb-145">Étant donné que le paramètre de code confidentiel n’est pas inclus, Lync Server génère et affecte automatiquement le numéro de code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-145">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="c1ecb-146">Pour affecter un numéro de code confidentiel spécifique à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c1ecb-146">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="c1ecb-147">Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-147">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="c1ecb-148">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="c1ecb-148">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1ecb-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1ecb-149">See Also</span></span>


<span data-ttu-id="c1ecb-150">[Numéro d’accès entrant](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c1ecb-150">[Dial-in Access Number](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="c1ecb-151">Configurer des règles de code confidentiel (PIN) de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1ecb-151">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

