---
title: Création ou modification d’une plage de numéros de prise d’appel de groupe dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- IT_Skype16
ms.custom:
- Strat_SB_Admin
- Strat_SB_Admin
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Créer ou modifier une plage de numéros de collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 3a717f5607764ef1d5677e7bc70368f8803fc854
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business-2015"></a><span data-ttu-id="fdf0c-103">Création ou modification d’une plage de numéros de prise d’appel de groupe dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="fdf0c-103">Create or modify a Group Call Pickup number range in Skype for Business 2015</span></span>
 
<span data-ttu-id="fdf0c-104">Créer ou modifier une plage de numéros de collecte d’appeler groupe dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fdf0c-105">Collecte d’appeler groupe est basé sur l’application d’appel Park.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="fdf0c-106">Lorsque vous déployez le groupe appeler remise en mains propres, vous devez configurer la table des appels park orbite avec des plages de numéros de téléphone qui sont désignés comme des numéros de groupe collecte d’appel.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="fdf0c-107">Ces numéros de groupe sont les numéros que les utilisateurs composent pour prendre des appels qui sonnent pour un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>
  
<span data-ttu-id="fdf0c-108">Tout comme les numéros d’appels parqués, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="fdf0c-109">Chaque pool frontal où vous déployez collecte d’appeler groupe peut avoir une ou plusieurs plages appel collecte des numéros de groupe.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="fdf0c-110">Les plages de numéro de groupe doivent être globalement uniques dans votre déploiement, et doivent être affectées comme étant de type **GroupPickup**.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>
  
<span data-ttu-id="fdf0c-111">La procédure suivante vous permet de créer ou de modifier une plage de numéros de groupe de prise d’appel dans la table des numéros d’appel parqué.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fdf0c-112">Vous devez utiliser Skype pour Business Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de prise d’appel de groupe dans la table des appels park orbite.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="fdf0c-113">Plages de numéros de prise d’appel de groupe ne sont pas disponibles dans Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="fdf0c-114">Les plages de numéros de groupe de prise d’appel doivent respecter les règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="fdf0c-114">The call pickup group number ranges must comply with the following rules:</span></span>
  
- <span data-ttu-id="fdf0c-115">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
- <span data-ttu-id="fdf0c-116">La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
- <span data-ttu-id="fdf0c-p104">La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>
    
- <span data-ttu-id="fdf0c-119">Si la plage de numéros commence par le caractère \* ou #, la plage doit être supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>
    
- <span data-ttu-id="fdf0c-120">Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d 0,8 {}).</span><span class="sxs-lookup"><span data-stu-id="fdf0c-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="fdf0c-121">Cela signifie que la valeur doit être une chaîne commençant par un caractère \* ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être un zéro).</span><span class="sxs-lookup"><span data-stu-id="fdf0c-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="fdf0c-122">Si le premier caractère est \* ou #, le caractère suivant doit être un nombre de 1 à 9 (il ne peut pas être un zéro).</span><span class="sxs-lookup"><span data-stu-id="fdf0c-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="fdf0c-123">Les autres caractères peuvent être n’importe quel nombre de 0 à 9 jusqu'à sept caractères supplémentaires (par exemple, « #6000 », «\*92000","\*95551212" et « 915551212 »).</span><span class="sxs-lookup"><span data-stu-id="fdf0c-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="fdf0c-124">Si le premier caractère n’est pas \* ou #, le premier caractère doit être un numéro de 1 à 9 (il ne peut pas être égal à zéro), suivi de huit caractères, chaque un nombre de 0 à 9 (par exemple, « 915551212 », « 41212 », « 300 »).</span><span class="sxs-lookup"><span data-stu-id="fdf0c-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="fdf0c-125">Pour créer ou modifier une plage de numéros de groupe de prise d’appel</span><span class="sxs-lookup"><span data-stu-id="fdf0c-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="fdf0c-126">Ouvrez une session sur l’ordinateur où est installé Skype pour Business Server Management Shell en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires, comme décrit dans **Déléguer les autorisations de configuration**.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="fdf0c-127">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fdf0c-128">**Nouveau-CsCallParkOrbit** permet de créer une nouvelle plage d’appel collecte des numéros de groupe.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="fdf0c-129">**Set-CsCallParkOrbit** permet de modifier une plage existante de numéros de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="fdf0c-130">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="fdf0c-130">At the command line, run:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="fdf0c-131">Exemple :</span><span class="sxs-lookup"><span data-stu-id="fdf0c-131">For example:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="fdf0c-132">L’exemple suivant montre comment convertir une plage de numéros d’appel parqué en une plage de numéros de groupes de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="fdf0c-133">N’utilisez cet applet de commande pour modifier le type affecté aux plages de numéros que si vous avez initialement spécifié un type incorrect et que la plage de groupe n’est pas encore utilisée.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="fdf0c-134">Si vous modifiez la plage de numéros en remplaçant CallPark par GroupPickup ou inversement et que la plage de numéros est déjà utilisée, CallPark et GroupPickup cesseront tous les deux de fonctionner pour cette plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="fdf0c-135">Par exemple, si vous modifiez une plage de numéros à partir de CallPark à GroupPick, l’application d’appel Park peut ne plus utiliser cette plage d’orbites aux appels du parc.</span><span class="sxs-lookup"><span data-stu-id="fdf0c-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fdf0c-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdf0c-136">See also</span></span>

#### 

[<span data-ttu-id="fdf0c-137">Nouvelle-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="fdf0c-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="fdf0c-138">Ensemble-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="fdf0c-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="fdf0c-139">Supprimer une plage d’orbite de parc d’appel</span><span class="sxs-lookup"><span data-stu-id="fdf0c-139">Delete a Call Park Orbit Range</span></span>](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

