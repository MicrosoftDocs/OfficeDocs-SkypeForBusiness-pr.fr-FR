---
title: 'Lync Server 2013 : création ou modification d’une plage de numéros de prise d’appel de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdf2ee113682ccee44d2329de68dfa87ea5824be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="4e931-102">Création ou modification d’une plage de numéros de prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e931-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e931-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="4e931-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="4e931-104">Utilisez la procédure suivante pour créer ou modifier une plage de numéros de groupe de prise d’appel dans la table des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="4e931-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e931-105">Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de prise d’appel de groupe dans la table des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="4e931-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="4e931-106">Les plages de numéros de prise d’appel de groupe ne sont pas disponibles dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e931-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4e931-107">La plage de numéros de groupe de prise d’appel doit être affectée d’un type de GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="4e931-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="4e931-108">Les utilisateurs sont activés pour la prise d’appel de groupe uniquement si le numéro de groupe auquel ils sont attribués est de type GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="4e931-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="4e931-109">Les plages de numéros de groupe de prise d’appel doivent respecter les règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e931-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="4e931-110">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="4e931-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="4e931-111">La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="4e931-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="4e931-p103">La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.</span><span class="sxs-lookup"><span data-stu-id="4e931-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="4e931-114">Si la plage de numéros commence par le \* caractère \#ou, la plage doit être supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="4e931-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="4e931-115">Valeurs valides : doivent correspondre à la chaîne d'\[\\\*|\#\]expression\[ régulière ( ? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="4e931-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="4e931-116">Cela signifie que la valeur doit être une chaîne commençant par le caractère \* ou \# un nombre de 1 à 9 (le premier caractère ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="4e931-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="4e931-117">Si le premier caractère est \* ou \#, le caractère suivant doit être un nombre de 1 à 9 (il ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="4e931-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="4e931-118">Les caractères suivants peuvent être n’importe quelle valeur comprise entre 0 et 9, jusqu’à\#sept caractères supplémentaires (\*par exemple, «\*6000 », « 92000 », « 95551212 » et « 915551212 »).</span><span class="sxs-lookup"><span data-stu-id="4e931-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="4e931-119">Si le premier caractère n’est \* pas \#ou, le premier caractère doit être un nombre compris entre 1 et 9 (il ne peut pas être zéro), suivi de huit caractères au maximum, chacun compris entre 0 et 9 (par exemple, « 915551212 », « 41212 », « 300 »).</span><span class="sxs-lookup"><span data-stu-id="4e931-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="4e931-120">Pour créer ou modifier une plage de groupe de prise d’appel</span><span class="sxs-lookup"><span data-stu-id="4e931-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="4e931-121">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4e931-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4e931-122">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4e931-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4e931-123">Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="4e931-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="4e931-124">Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="4e931-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="4e931-125">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4e931-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="4e931-126">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4e931-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="4e931-127">L’exemple suivant montre comment modifier une plage de numéros entre les orbites de parcage d’appel et les groupes de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="4e931-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4e931-128">Utilisez cette applet de commande pour modifier le type affecté aux plages de numéros uniquement si vous avez initialement spécifié un type incorrect et que la plage de groupes n’est pas encore utilisée.</span><span class="sxs-lookup"><span data-stu-id="4e931-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="4e931-129">Si vous modifiez la plage de numéros de CallPark à GroupPickup ou inversement et que la plage de numéros est déjà utilisée, le parcage d’appel ou la prise d’appel de groupe cessera de fonctionner pour cette plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="4e931-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="4e931-130">Par exemple, si vous modifiez une plage de numéros de CallPark à GroupPick, l’application de parcage d’appel ne peut plus utiliser cette plage d’orbites pour les appels de parcage.</span><span class="sxs-lookup"><span data-stu-id="4e931-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e931-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e931-131">See Also</span></span>


[<span data-ttu-id="4e931-132">Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e931-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="4e931-133">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="4e931-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="4e931-134">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="4e931-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

