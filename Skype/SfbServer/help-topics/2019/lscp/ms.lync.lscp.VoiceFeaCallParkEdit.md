---
title: Mise en garde d’appels créer ou modifier une existant
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Plages de numéros de parcage d’appel définissent les numéros temporaires où mis en garde d’appels sont conservés jusqu'à ce que quelqu'un les récupère ou qu’ils délai d’expiration.
ms.openlocfilehash: 1beb1dc15916bb806fab89152245b4b781957e68
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993456"
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="1291c-103">Parcage d’appel : création d’un parcage ou modification d’un parcage existant</span><span class="sxs-lookup"><span data-stu-id="1291c-103">Call Park: Create New or Edit Existing</span></span>
 
<span data-ttu-id="1291c-104">Plages de numéros de parcage d’appel définissent les numéros temporaires où mis en garde d’appels sont conservés jusqu'à ce que quelqu'un les récupère ou qu’ils délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="1291c-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="1291c-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="1291c-105">UI Reference</span></span>

<span data-ttu-id="1291c-106">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="1291c-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="1291c-107">**Nom** Tapez un nom descriptif qui identifie la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="1291c-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="1291c-108">Une fois que vous enregistrez la plage de numéros, ce nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="1291c-108">After you save the number range, this name cannot be changed.</span></span>
    
- <span data-ttu-id="1291c-109">**Numéro de plage** Dans le premier champ, tapez le numéro de début de la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="1291c-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="1291c-110">Dans le deuxième champ, tapez le numéro de fin de la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="1291c-110">In the second field, type the ending number of the number range.</span></span>
    
  - <span data-ttu-id="1291c-111">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="1291c-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
  - <span data-ttu-id="1291c-112">La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="1291c-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
  - <span data-ttu-id="1291c-p103">La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.</span><span class="sxs-lookup"><span data-stu-id="1291c-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>
    
  - <span data-ttu-id="1291c-115">Si la plage de numéros commence par le caractère \* ou #, la plage doit être supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="1291c-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>
    
  - <span data-ttu-id="1291c-116">Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\* | #] ? [1-9] \d{0,7}) | (\d [1-9]{0,8}).</span><span class="sxs-lookup"><span data-stu-id="1291c-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="1291c-117">Cela signifie que la valeur doit être une chaîne commençant par un caractère \* ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="1291c-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="1291c-118">Si le premier caractère est \* ou #, le caractère qui suit doit être un nombre de 1 à 9 (il ne peut pas être zéro).</span><span class="sxs-lookup"><span data-stu-id="1291c-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="1291c-119">Les caractères suivants peuvent être n’importe quel nombre entre 0 et 9, jusqu'à sept caractères supplémentaires (par exemple, « #6000 », «\*92000"«\*95551212" et « 915551212 »).</span><span class="sxs-lookup"><span data-stu-id="1291c-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="1291c-120">Si le premier caractère n’est pas \* ou #, le premier caractère doit être un nombre de 1 à 9 (il ne peut pas être égal à zéro), suivi de huit caractères, chaque un numéro de 0 à 9 (par exemple : 915551212 ; 41212 ; 300).</span><span class="sxs-lookup"><span data-stu-id="1291c-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>
    
  - <span data-ttu-id="1291c-p105">En tout, il ne doit pas y avoir plus de 50 000 numéros par pool. Chaque plage de numéros comporte en général un maximum de 100 numéros, mais peut être beaucoup plus importante et inclure jusqu’à 10 000 numéros. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, envisagez de spécifier « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="1291c-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>
    
- <span data-ttu-id="1291c-124">**Nom de domaine complet du serveur de destination** Sélectionnez le nom de domaine complet (FQDN) ou ID de service du service d’Application qui héberge l’application de parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="1291c-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="1291c-125">Mise en garde de tous les appels de numéros dans la plage spécifiée par le numéro de départ et numéro de fin dans la plage de numéros est acheminé vers ce serveur ou ce pool.</span><span class="sxs-lookup"><span data-stu-id="1291c-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>
    
<span data-ttu-id="1291c-126">Pour plus d’informations sur les fonctionnalités de parcage d’appel, voir [planifier la mise en garde d’appels dans Skype pour les entreprises](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="1291c-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="1291c-127">Pour plus d’informations sur l’utilisation des plages de numéros de parcage d’appel, voir [Configurer les Extensions numéro de téléphone pour les appels parcage](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="1291c-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

