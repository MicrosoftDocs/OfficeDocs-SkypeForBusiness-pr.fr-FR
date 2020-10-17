---
title: 'Lync Server 2013 : création ou modification d’une plage d’orbites de parcage d’appel'
description: 'Lync Server 2013 : création ou modification d’une plage d’orbites de parcage d’appel.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3889f30264593bedcffb54811dd5bd844f48f0cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553840"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="bba42-103">Création ou modification d’une plage d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bba42-103">Create or modify a Call Park orbit range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bba42-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bba42-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bba42-105">Utilisez l’une des procédures suivantes pour créer ou modifier une plage d’orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="bba42-105">Use one of the following procedures to create or modify a call park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="bba42-106">Pour utiliser le panneau de configuration Lync Server pour créer ou modifier une plage de numéros pour les appels de parking</span><span class="sxs-lookup"><span data-stu-id="bba42-106">To use Lync Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="bba42-107">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bba42-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bba42-108">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="bba42-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bba42-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bba42-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bba42-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bba42-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bba42-111">Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="bba42-111">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="bba42-112">Dans la page **Parcage d’appel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bba42-112">On the **Call Park** page, do one of the following:</span></span>
    
      - <span data-ttu-id="bba42-p103">Pour créer une plage d’orbites, cliquez sur **Nouveau**. Dans **Nom**, tapez un nom permettant d’identifier cette plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="bba42-p103">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bba42-115">Une fois que vous avez validé la plage d’orbites dans la base de données, vous ne pouvez plus modifier ce nom.</span><span class="sxs-lookup"><span data-stu-id="bba42-115">After you commit the orbit range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="bba42-p104">Pour modifier une plage d’orbites existante, tapez une partie ou l’ensemble du nom de la plage d’orbites dans le champ de recherche. Dans la liste des orbites, cliquez sur l’orbite voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="bba42-p104">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="bba42-118">Dans le premier champ **Plage de numéros**, tapez le premier numéro de la plage de postes pour cette orbite de parcage d’appel et, dans le deuxième champ **Plage de numéros**, tapez le dernier numéro de la plage.</span><span class="sxs-lookup"><span data-stu-id="bba42-118">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="bba42-119">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="bba42-119">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="bba42-120">La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="bba42-120">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="bba42-p105">La plage d’orbites doit être unique. Cette plage ne peut pas chevaucher une autre plage.</span><span class="sxs-lookup"><span data-stu-id="bba42-p105">The orbit range must be unique. This range cannot overlap with any other range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="bba42-123">Si la plage d’orbites commence avec le caractère \* ou #, la plage doit être supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="bba42-123">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="bba42-124">Valeurs valides : doivent correspondre à la chaîne d’expression régulière ([ \* | #] ? [ 1-9] \d {0,7} ) | ([1-9] \d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="bba42-124">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="bba42-125">Ainsi, chaque valeur doit être une chaîne commençant soit par le caractère \* ou #, soit par un nombre de 1 à 9 (le premier caractère ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="bba42-125">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="bba42-126">Si le premier caractère est \* ou #, le caractère qui suit doit être un nombre de 1 à 9 (il ne peut être zéro).</span><span class="sxs-lookup"><span data-stu-id="bba42-126">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="bba42-127">Les caractères suivants peuvent être n’importe quelle valeur comprise entre 0 et 9, jusqu’à sept caractères supplémentaires (par exemple, « #6000 », «*92000 », «* 95551212 » et « 915551212 »).</span><span class="sxs-lookup"><span data-stu-id="bba42-127">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "* 95551212", and "915551212").</span></span> <span data-ttu-id="bba42-128">Si le premier caractère n’est pas \* ou #, il doit être un nombre de 1 à 9 (pas de zéro) suivi de huit caractères maximum, chacun étant un nombre de 0 à 9 (par exemple : « 915551212 », « 41212 », « 300 »).</span><span class="sxs-lookup"><span data-stu-id="bba42-128">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span></P>
    > <LI>
    > <P><span data-ttu-id="bba42-p107">Il ne doit pas y avoir plus de 50 000 orbites par pool. Chaque plage d’orbites comporte en général un maximum de 100 orbites. Mais les plages peuvent comporter jusqu’à 10 000 orbites. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, spécifiez « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="bba42-p107">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="bba42-132">Dans nom **de domaine complet du serveur de destination**, cliquez sur le nom de domaine complet (FQDN) ou l’ID de service du service d’application qui héberge l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="bba42-132">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="bba42-133">Tous les appels parqués sous forme de numéros dans la plage d’orbites spécifiée par le numéro de début et le numéro de fin seront routés vers ce serveur ou ce pool.</span><span class="sxs-lookup"><span data-stu-id="bba42-133">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7.  <span data-ttu-id="bba42-134">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="bba42-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="bba42-135">Pour utiliser Windows PowerShell afin de créer ou de modifier une plage de numéros pour les appels de parking</span><span class="sxs-lookup"><span data-stu-id="bba42-135">To use Windows PowerShell to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="bba42-136">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="bba42-136">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bba42-137">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bba42-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bba42-138">Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros d’orbite.</span><span class="sxs-lookup"><span data-stu-id="bba42-138">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="bba42-139">Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros d’orbite.</span><span class="sxs-lookup"><span data-stu-id="bba42-139">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="bba42-140">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="bba42-140">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    <span data-ttu-id="bba42-141">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="bba42-141">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    <span data-ttu-id="bba42-142">L’exemple suivant montre comment modifier les numéros d’une plage d’orbites existante,</span><span class="sxs-lookup"><span data-stu-id="bba42-142">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bba42-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bba42-143">See Also</span></span>


[<span data-ttu-id="bba42-144">Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bba42-144">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="bba42-145">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="bba42-145">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="bba42-146">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="bba42-146">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

