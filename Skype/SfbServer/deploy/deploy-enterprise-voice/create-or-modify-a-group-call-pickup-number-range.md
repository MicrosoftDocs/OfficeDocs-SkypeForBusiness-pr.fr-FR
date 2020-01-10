---
title: Création ou modification d’une plage de numéros de téléphone dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Créez ou modifiez une plage de numéros de téléphone dans Skype entreprise Server Voice.
ms.openlocfilehash: 546fefd996286678aae77338b4e0867285670a57
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001714"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="c3b94-103">Création ou modification d’une plage de numéros de téléphone dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="c3b94-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="c3b94-104">Créez ou modifiez une plage de numéros de téléphone dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="c3b94-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="c3b94-105">Le prélèvement d’appels de groupe est basé sur l’application de parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="c3b94-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="c3b94-106">Lorsque vous déployez le prélèvement d’appels de groupe, vous devez configurer la table orbite du parc d’appels avec des plages de numéros de téléphone désignés comme numéros de groupe de cueillette d’appel.</span><span class="sxs-lookup"><span data-stu-id="c3b94-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="c3b94-107">Ces numéros de groupe sont les numéros que les utilisateurs composent pour prendre des appels qui sonnent pour un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3b94-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="c3b94-108">Tout comme les numéros d’appels parqués, les numéros de groupe de prise d’appel doivent être des extensions virtuelles auxquelles aucun utilisateur ou téléphone n’est affecté.</span><span class="sxs-lookup"><span data-stu-id="c3b94-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="c3b94-109">Chaque pool frontal sur lequel vous déployez la capture d’appels de groupe peut avoir une ou plusieurs gammes de numéros de groupe de cueillette d’appel.</span><span class="sxs-lookup"><span data-stu-id="c3b94-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="c3b94-110">Les plages de numéro de groupe doivent être globalement uniques dans votre déploiement, et doivent être affectées comme étant de type **GroupPickup**.</span><span class="sxs-lookup"><span data-stu-id="c3b94-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="c3b94-111">La procédure suivante vous permet de créer ou de modifier une plage de numéros de groupe de prise d’appel dans la table des numéros d’appel parqué.</span><span class="sxs-lookup"><span data-stu-id="c3b94-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="c3b94-112">Vous devez utiliser Skype entreprise Server Management Shell pour créer, modifier, supprimer et afficher les plages de numéros des numéros de téléphone dans la table de stationnement du parc.</span><span class="sxs-lookup"><span data-stu-id="c3b94-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="c3b94-113">Les plages de numéros de capture d’appels de groupe ne sont pas disponibles dans le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c3b94-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="c3b94-114">Les plages de numéros de groupe de prise d’appel doivent respecter les règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3b94-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="c3b94-115">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="c3b94-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="c3b94-116">La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="c3b94-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="c3b94-p104">La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.</span><span class="sxs-lookup"><span data-stu-id="c3b94-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="c3b94-119">Si la plage numérique commence par le caractère \* ou #, la plage doit être supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="c3b94-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="c3b94-120">Valeurs valides : doit correspondre à la chaîne\\d’expression régulière 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="c3b94-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="c3b94-121">Cela signifie que la valeur doit être une chaîne commençant par le caractère \* ou # ou par un nombre 1 à 9 (le premier caractère ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="c3b94-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="c3b94-122">Si le premier caractère est \* ou #, le caractère suivant doit être un nombre 1 à 9 (il ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="c3b94-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="c3b94-123">Les caractères suivants peuvent être n’importe quelle valeur comprise entre 0 et 9 (par exemple, "#6000"\*, "92000"\*, "95551212" et "915551212").</span><span class="sxs-lookup"><span data-stu-id="c3b94-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="c3b94-124">Si le premier caractère n’est \* pas ou #, le premier caractère doit être un nombre compris entre 1 et 9 (il ne peut pas être zéro), suivi de huit caractères au maximum (par exemple, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="c3b94-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="c3b94-125">Pour créer ou modifier une plage de numéros de groupe de prise d’appel</span><span class="sxs-lookup"><span data-stu-id="c3b94-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="c3b94-126">Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **autorisations de configuration de délégué**.</span><span class="sxs-lookup"><span data-stu-id="c3b94-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="c3b94-127">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c3b94-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="c3b94-128">Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="c3b94-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="c3b94-129">Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="c3b94-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="c3b94-130">Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c3b94-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="c3b94-131">Exemple :</span><span class="sxs-lookup"><span data-stu-id="c3b94-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="c3b94-132">L’exemple suivant montre comment convertir une plage de numéros d’appel parqué en une plage de numéros de groupes de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="c3b94-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="c3b94-133">N’utilisez cet applet de commande pour modifier le type affecté aux plages de numéros que si vous avez initialement spécifié un type incorrect et que la plage de groupe n’est pas encore utilisée.</span><span class="sxs-lookup"><span data-stu-id="c3b94-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="c3b94-134">Si vous modifiez la plage de numéros en remplaçant CallPark par GroupPickup ou inversement et que la plage de numéros est déjà utilisée, CallPark et GroupPickup cesseront tous les deux de fonctionner pour cette plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="c3b94-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="c3b94-135">Par exemple, si vous modifiez une plage de nombres de CallPark à GroupPick, l’application de parc d’appels ne peut plus utiliser cette gamme d’orbites pour les appels de parc.</span><span class="sxs-lookup"><span data-stu-id="c3b94-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3b94-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3b94-136">See also</span></span>

[<span data-ttu-id="c3b94-137">Nouveau-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="c3b94-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="c3b94-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="c3b94-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="c3b94-139">Supprimer une gamme de stationnement d’appel</span><span class="sxs-lookup"><span data-stu-id="c3b94-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
