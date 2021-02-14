---
title: Créer ou modifier une plage de numéros de prise d’appel de groupe dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Créez ou modifiez une plage de numéros de prise d’appel de groupe dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: f487c277b8eaa03a5b31ce0dc9696b0efe712340
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822404"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="7d6cd-103">Créer ou modifier une plage de numéros de prise d’appel de groupe dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="7d6cd-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="7d6cd-104">Créez ou modifiez une plage de numéros de prise d’appel de groupe dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="7d6cd-105">La prise d’appel de groupe est basée sur l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="7d6cd-106">Lorsque vous déployez la prise d’appel de groupe, vous devez configurer la table des orbites de parcage d’appel avec des plages de numéros de téléphone désignés comme numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="7d6cd-107">Ces numéros de groupe sont les numéros que les utilisateurs composent pour prendre les appels qui sonnent pour un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="7d6cd-108">Comme les numéros d’orbite de parcage d’appel, les numéros de groupe de prise d’appel doivent être des extensions virtuelles qui ne sont pas affectées à un utilisateur ou à un téléphone.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="7d6cd-109">Chaque pool frontal sur lequel vous déployez la prise d’appel de groupe peut avoir une ou plusieurs plages de numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="7d6cd-110">Les plages de numéro de groupe doivent être globalement uniques dans votre déploiement et doivent être affectées en tant que type **GroupPickup.**</span><span class="sxs-lookup"><span data-stu-id="7d6cd-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="7d6cd-111">Utilisez la procédure suivante pour créer ou modifier une plage de numéro de groupe de prise d’appel dans la table des orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="7d6cd-112">Vous devez utiliser Skype Entreprise Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de prise d’appel de groupe dans la table des numéros d’appels par parcage.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="7d6cd-113">Les plages de numéros de prise d’appel de groupe ne sont pas disponibles dans le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="7d6cd-114">Les plages de numéro de groupe de prise d’appel doivent respecter les règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d6cd-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="7d6cd-115">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="7d6cd-116">La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="7d6cd-p104">La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="7d6cd-119">Si la plage de nombres commence par le caractère ou #, la plage doit être supérieure \* à 100.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="7d6cd-120">Valeurs valides : doit correspondre à la chaîne d’expression régulière ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="7d6cd-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="7d6cd-121">Cela signifie que la valeur doit être une chaîne commençant par le caractère ou # ou un nombre de 1 à 9 (le premier caractère ne peut \* pas être un zéro).</span><span class="sxs-lookup"><span data-stu-id="7d6cd-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="7d6cd-122">Si le premier caractère est ou #, le caractère suivant doit être un nombre \* de 1 à 9 (il ne peut pas être un zéro).</span><span class="sxs-lookup"><span data-stu-id="7d6cd-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="7d6cd-123">Les caractères suivants peuvent être n’importe quel nombre de 0 à 9, jusqu’à sept caractères supplémentaires (par exemple, « #6000 », « \* 92000 », « \* 95551212 » et « 915551212 »).</span><span class="sxs-lookup"><span data-stu-id="7d6cd-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="7d6cd-124">Si le premier caractère n’est pas ou #, le premier caractère doit être un nombre de 1 à 9 (il ne peut pas être zéro), suivi de huit caractères au plus, chacun un nombre de 0 à \* 9 (par exemple, « 915551212 », « 41212 », « 300 »).</span><span class="sxs-lookup"><span data-stu-id="7d6cd-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="7d6cd-125">Pour créer ou modifier une plage de groupes de prise d’appel</span><span class="sxs-lookup"><span data-stu-id="7d6cd-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="7d6cd-126">Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans déléguer les **autorisations** d’installation.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="7d6cd-127">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="7d6cd-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="7d6cd-128">Utilisez **New-CsCallParkOrbit** pour créer une nouvelle plage de numéros de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="7d6cd-129">Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="7d6cd-130">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7d6cd-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="7d6cd-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="7d6cd-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="7d6cd-132">L’exemple suivant montre comment modifier une plage de numéros des orbites de parcage d’appel aux groupes de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="7d6cd-133">Utilisez cette cmdlet pour modifier le type affecté aux plages de nombres uniquement si vous avez initialement spécifié le type incorrect et que la plage de groupes n’est pas encore en cours d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="7d6cd-134">Si vous modifiez la plage de numéro de CallPark en GroupPickup ou vice versa et que la plage de numéro est déjà en cours d’utilisation, le parcage d’appel ou la prise d’appel de groupe cesse de fonctionner pour cette plage de numéro.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="7d6cd-135">Par exemple, si vous modifiez une plage de numéro de CallPark en GroupPick, l’application de parcage d’appel ne peut plus utiliser cette plage d’orbites pour parer des appels.</span><span class="sxs-lookup"><span data-stu-id="7d6cd-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d6cd-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d6cd-136">See also</span></span>

[<span data-ttu-id="7d6cd-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="7d6cd-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="7d6cd-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="7d6cd-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="7d6cd-139">Supprimer une plage d’orbites de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="7d6cd-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
