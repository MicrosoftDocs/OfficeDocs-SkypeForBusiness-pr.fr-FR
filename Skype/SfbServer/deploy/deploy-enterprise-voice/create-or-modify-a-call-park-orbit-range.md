---
title: Créer ou modifier une plage d’orbites de parcage d’appel dans Skype pour les entreprises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Créer ou modifier une table de plage des orbites de parcage d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 23de2c42ff7b7e8bf3c020eaf3bb5050524b87d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212529"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="ba28b-103">Créer ou modifier une plage d’orbites de parcage d’appel dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="ba28b-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="ba28b-104">Créer ou modifier une table de plage des orbites de parcage d’appel dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ba28b-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="ba28b-105">Mise en garde d’appels utilise des orbites de parcage d’appels.</span><span class="sxs-lookup"><span data-stu-id="ba28b-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="ba28b-106">Avant que les utilisateurs peuvent mettre en garde et récupérer des appels, vous devez configurer la table d’orbites de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="ba28b-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="ba28b-107">Vous devez spécifier les plages de numéros de poste (orbites) que votre organisation sera réserver pour le parcage d’appels et définir le routage de ces plages en spécifiant le pool de parcage d’appel gère chaque plage.</span><span class="sxs-lookup"><span data-stu-id="ba28b-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="ba28b-108">Lorsque vous définissez des plages d’orbites, l’objectif est de disposer de suffisamment d’orbites pour ne pas avoir à réutiliser trop rapidement une orbite, mais sans que leur nombre soit trop élevé afin de pouvoir limiter le nombre de postes disponibles pour les utilisateurs ou d’autres services.</span><span class="sxs-lookup"><span data-stu-id="ba28b-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="ba28b-109">Vous pouvez créer plusieurs plages d’orbites de parcage d’appel pour chaque Skype pour pool Business Server où l’application de parcage d’appel est déployée.</span><span class="sxs-lookup"><span data-stu-id="ba28b-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="ba28b-110">Chaque plage d’orbites de parcage d’appel doit avoir un nom unique et un ensemble unique d’extensions.</span><span class="sxs-lookup"><span data-stu-id="ba28b-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba28b-p102">Une plage d’orbites comprend généralement au moins 100 orbites. Chaque plage peut être plus importante à condition qu’elle contienne moins de 10 000 orbites et que chaque pool comporte moins de 50 000 orbites. Si une plage est trop petite, les orbites sont réutilisées plus rapidement.</span><span class="sxs-lookup"><span data-stu-id="ba28b-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="ba28b-114">Utilisez des blocs de postes virtuels (postes attribués à aucun utilisateur ni téléphone) pour vos plages d’orbites.</span><span class="sxs-lookup"><span data-stu-id="ba28b-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="ba28b-115">Affectation de numéros de Direct Inward Dialing (DID) comme numéros d’orbites dans la mise en garde d’appels table des orbites n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="ba28b-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="ba28b-116">Pour créer ou modifier une plage d’orbites de parcage d’appel, utilisez l’une des procédures ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ba28b-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="ba28b-117">Utiliser Skype pour Business Server Control Panel pour créer ou modifier une plage de numéros pour le parcage d’appels</span><span class="sxs-lookup"><span data-stu-id="ba28b-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="ba28b-118">Ouvrez une session l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ba28b-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ba28b-119">Pour plus d’informations, voir **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="ba28b-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="ba28b-120">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="ba28b-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ba28b-121">Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="ba28b-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="ba28b-122">Dans la page **Parcage d’appel**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba28b-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="ba28b-p104">Pour créer une plage d’orbites, cliquez sur **Nouveau**. Dans **Nom**, tapez un nom permettant d’identifier cette plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="ba28b-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ba28b-125">Une fois que vous avez validé la plage d’orbites dans la base de données, vous ne pouvez plus modifier ce nom.</span><span class="sxs-lookup"><span data-stu-id="ba28b-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="ba28b-p105">Pour modifier une plage d’orbites existante, tapez une partie ou l’ensemble du nom de la plage d’orbites dans le champ de recherche. Dans la liste des orbites, cliquez sur l’orbite voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ba28b-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="ba28b-128">Dans le premier champ **Plage de numéros**, tapez le premier numéro de la plage de postes pour cette orbite de parcage d’appel et, dans le deuxième champ **Plage de numéros**, tapez le dernier numéro de la plage.</span><span class="sxs-lookup"><span data-stu-id="ba28b-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="ba28b-129">Gardez à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="ba28b-129">Be aware:</span></span>

   - <span data-ttu-id="ba28b-130">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="ba28b-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="ba28b-131">La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="ba28b-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="ba28b-p107">La plage d’orbites doit être unique. Cette plage ne peut pas chevaucher une autre plage.</span><span class="sxs-lookup"><span data-stu-id="ba28b-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="ba28b-134">Si la plage d’orbites commence par le caractère \* ou #, la plage doit être supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="ba28b-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="ba28b-135">Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\* | #] ? [1-9] \d{0,7}) | (\d [1-9]{0,8}).</span><span class="sxs-lookup"><span data-stu-id="ba28b-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="ba28b-136">Cela signifie que la valeur doit être une chaîne commençant par un caractère \* ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="ba28b-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="ba28b-137">Si le premier caractère est \* ou #, le caractère qui suit doit être un nombre de 1 à 9 (il ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="ba28b-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="ba28b-138">Les caractères suivants peuvent être n’importe quel nombre entre 0 et 9, jusqu'à sept caractères supplémentaires (par exemple, « #6000 », «\*92000"«\*95551212" et « 915551212 »).</span><span class="sxs-lookup"><span data-stu-id="ba28b-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="ba28b-139">Si le premier caractère n’est pas \* ou #, le premier caractère doit être un nombre de 1 à 9 (il ne peut pas être égal à zéro), suivi de huit caractères, chaque un nombre de 0 à 9 (par exemple, « 915551212 », « 41212 », « 300 »).</span><span class="sxs-lookup"><span data-stu-id="ba28b-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="ba28b-p109">Il ne doit pas y avoir plus de 50 000 orbites par pool. Chaque plage d’orbites comporte en général un maximum de 100 orbites. Mais les plages peuvent comporter jusqu’à 10 000 orbites. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, spécifiez « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="ba28b-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="ba28b-143">Dans **nom de domaine complet du serveur de destination**, cliquez sur le nom de domaine complet (FQDN) ou ID de service du service d’Application qui héberge l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="ba28b-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="ba28b-144">Tous les appels parqués sous forme de numéros dans la plage d’orbites spécifiée par le numéro de début et le numéro de fin seront routés vers ce serveur ou ce pool.</span><span class="sxs-lookup"><span data-stu-id="ba28b-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="ba28b-145">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ba28b-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="ba28b-146">Utiliser Skype pour Business Server Management Shell pour créer ou modifier une plage de numéros pour le parcage d’appels</span><span class="sxs-lookup"><span data-stu-id="ba28b-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="ba28b-147">Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.</span><span class="sxs-lookup"><span data-stu-id="ba28b-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="ba28b-148">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ba28b-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="ba28b-149">Utilisez **New-CsCallParkOrbit** pour créer une plage de numéros d’orbite.</span><span class="sxs-lookup"><span data-stu-id="ba28b-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="ba28b-150">Utilisez **Set-CsCallParkOrbit** pour modifier une plage existante de numéros d’orbite.</span><span class="sxs-lookup"><span data-stu-id="ba28b-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="ba28b-151">Dans la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ba28b-151">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="ba28b-152">Exemple :</span><span class="sxs-lookup"><span data-stu-id="ba28b-152">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="ba28b-153">L’exemple ci-dessous montre comment modifier les numéros d’une plage d’orbites existante,</span><span class="sxs-lookup"><span data-stu-id="ba28b-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="ba28b-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba28b-154">See also</span></span>

[<span data-ttu-id="ba28b-155">Nouvelle-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="ba28b-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="ba28b-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="ba28b-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="ba28b-157">Supprimer une plage d’orbites de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="ba28b-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
