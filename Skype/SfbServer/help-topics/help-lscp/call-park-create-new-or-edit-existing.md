---
title: Appel Park, créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Les plages de numéros appel Park définissent les numéros temporaires où sont conservés les appels en stationnement jusqu'à ce qu’une personne récupère les ou délai d’attente.
ms.openlocfilehash: 840caf654e1264d7355f117303e8ded9efbca7d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="call-park-create-new-or-edit-existing"></a><span data-ttu-id="475fd-103">Parcage d’appel : création d’un parcage ou modification d’un parcage existant</span><span class="sxs-lookup"><span data-stu-id="475fd-103">Call Park: Create New or Edit Existing</span></span>
 
<span data-ttu-id="475fd-104">Les plages de numéros appel Park définissent les numéros temporaires où sont conservés les appels en stationnement jusqu'à ce qu’une personne récupère les ou délai d’attente.</span><span class="sxs-lookup"><span data-stu-id="475fd-104">Call Park number ranges define the temporary numbers where parked calls are held until someone retrieves them or they time out.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="475fd-105">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="475fd-105">UI Reference</span></span>

<span data-ttu-id="475fd-106">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="475fd-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="475fd-107">**Nom** Tapez un nom descriptif qui identifie la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="475fd-107">**Name** Type a descriptive name that identifies the number range.</span></span> <span data-ttu-id="475fd-108">Après avoir enregistré la plage de numéros, ce nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="475fd-108">After you save the number range, this name cannot be changed.</span></span>
    
- <span data-ttu-id="475fd-109">**Numéro de gamme** Dans le premier champ, tapez le numéro de début de la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="475fd-109">**Number range** In the first field, type the beginning number of the number range.</span></span> <span data-ttu-id="475fd-110">Dans le second champ, tapez le numéro de fin de la plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="475fd-110">In the second field, type the ending number of the number range.</span></span>
    
  - <span data-ttu-id="475fd-111">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="475fd-111">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
  - <span data-ttu-id="475fd-112">La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="475fd-112">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
  - <span data-ttu-id="475fd-p103">La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.</span><span class="sxs-lookup"><span data-stu-id="475fd-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>
    
  - <span data-ttu-id="475fd-115">Si la plage de numéros commence par le caractère \* ou #, la plage doit être supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="475fd-115">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>
    
  - <span data-ttu-id="475fd-116">Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d 0,8 {}).</span><span class="sxs-lookup"><span data-stu-id="475fd-116">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="475fd-117">Cela signifie que la valeur doit être une chaîne commençant par un caractère \* ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être un zéro).</span><span class="sxs-lookup"><span data-stu-id="475fd-117">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="475fd-118">Si le premier caractère est \* ou #, le caractère suivant doit être un nombre de 1 à 9 (il ne peut pas être un zéro).</span><span class="sxs-lookup"><span data-stu-id="475fd-118">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="475fd-119">Les autres caractères peuvent être n’importe quel nombre de 0 à 9 jusqu'à sept caractères supplémentaires (par exemple, « #6000 », «\*92000","\*95551212" et « 915551212 »).</span><span class="sxs-lookup"><span data-stu-id="475fd-119">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="475fd-120">Si le premier caractère n’est pas \* ou #, le premier caractère doit être un numéro de 1 à 9 (il ne peut pas être égal à zéro), suivi de huit caractères, chaque un nombre de 0 à 9 (par exemple : 915551212 ; 41212 ; 300).</span><span class="sxs-lookup"><span data-stu-id="475fd-120">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example: 915551212;41212;300).</span></span>
    
  - <span data-ttu-id="475fd-p105">En tout, il ne doit pas y avoir plus de 50 000 numéros par pool. Chaque plage de numéros comporte en général un maximum de 100 numéros, mais peut être beaucoup plus importante et inclure jusqu’à 10 000 numéros. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, envisagez de spécifier « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="475fd-p105">You should not have more than a total of 50,000 numbers per pool. Each number range typically encompasses 100 or fewer numbers, but it can be much larger as long as it includes fewer than 10,000 numbers. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>
    
- <span data-ttu-id="475fd-124">**Nom de domaine complet du serveur de destination** Sélectionnez le nom de domaine pleinement qualifié (FQDN) ou l’ID du service d’Application qui héberge l’application Park de l’appel de service.</span><span class="sxs-lookup"><span data-stu-id="475fd-124">**FQDN of destination server** Select the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="475fd-125">Tous les appels calée en nombres dans une plage spécifiée par le numéro de départ et numéro de fin de la plage de numéros est routé vers ce serveur ou le pool.</span><span class="sxs-lookup"><span data-stu-id="475fd-125">All calls parked to numbers within the range specified by the start number and end number in the number range will be routed to this server or pool.</span></span>
    
<span data-ttu-id="475fd-126">Pour plus d’informations sur les fonctionnalités d’appel Park de, voir [planification de parc d’appel dans Skype pour entreprise 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="475fd-126">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="475fd-127">Pour plus d’informations sur l’utilisation des plages de numéros d’appel Park, consultez [Configurer les Extensions numéro de téléphone pour les appels de stationnement](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="475fd-127">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

