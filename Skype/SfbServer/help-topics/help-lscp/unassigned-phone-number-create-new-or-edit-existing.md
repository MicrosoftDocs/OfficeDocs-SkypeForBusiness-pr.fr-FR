---
title: Numéro de téléphone non affecté création d’un nouveau ou modification existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 27977490b1cd55af9ae3011cfeb56878a5da6876
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821906"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="ec48d-104">Numéro de téléphone non attribué : en créer un autre ou en modifier un existant</span><span class="sxs-lookup"><span data-stu-id="ec48d-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="ec48d-p102">Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="ec48d-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec48d-107">Lorsque vous avez terminé de créer une nouvelle plage de numéros non attribués ou d’en modifier une, cliquez sur **OK** pour revenir à la page **numéro non affecté** qui recense toutes les plages de nombres.</span><span class="sxs-lookup"><span data-stu-id="ec48d-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="ec48d-108">Les modifications que vous avez effectuées dans la page **nouvelle plage de numéros non attribués** ou la page **modifier le numéro non affecté** ne sont pas validées dans la base de données tant que vous n’avez pas cliqué sur **valider tout** dans la page **numéro non attribué** .</span><span class="sxs-lookup"><span data-stu-id="ec48d-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ec48d-109">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="ec48d-109">UI Reference</span></span>

<span data-ttu-id="ec48d-110">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="ec48d-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="ec48d-111">**Nom** Tapez un nom descriptif identifiant la plage de nombres non attribués.</span><span class="sxs-lookup"><span data-stu-id="ec48d-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="ec48d-112">Ce nom ne peut pas être modifié après enregistrement de la plage.</span><span class="sxs-lookup"><span data-stu-id="ec48d-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="ec48d-113">**Plage de nombres** Dans le premier champ, tapez le numéro de début de la plage de nombres non attribués.</span><span class="sxs-lookup"><span data-stu-id="ec48d-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="ec48d-114">Dans le deuxième champ, tapez le nombre de fin de la plage.</span><span class="sxs-lookup"><span data-stu-id="ec48d-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="ec48d-115">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="ec48d-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="ec48d-116">Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.</span><span class="sxs-lookup"><span data-stu-id="ec48d-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="ec48d-117">Le numéro doit correspondre à l’expression régulière (tel :) ? ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="ec48d-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="ec48d-118">Cela signifie que le numéro peut commencer par la chaîne « tel : » (si vous ne spécifiez pas cette chaîne, il sera automatiquement ajouté pour vous), un signe plus (+) et un chiffre 1 à 9.</span><span class="sxs-lookup"><span data-stu-id="ec48d-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="ec48d-119">Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="ec48d-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="ec48d-120">**Service d’annonce** Sélectionner **annonce** pour que l’application d’annonce gère l’appel entrant ou la **messagerie unifiée Exchange** pour qu’un standard automatique de messagerie unifiée Exchange gère l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="ec48d-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="ec48d-121">Si vous avez sélectionné **annonce** pour le **service d’annonce**:</span><span class="sxs-lookup"><span data-stu-id="ec48d-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="ec48d-122">**Nom de domaine complet du serveur de destination** Sélectionnez l’ID du service d’application qui exécute l’application d’annonce qui traitera les appels entrants de cette plage de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="ec48d-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="ec48d-123">**Annonce** Sélectionnez l’annonce à lire pour cette série de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="ec48d-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="ec48d-124">Si vous avez sélectionné **Exchange um** pour le **service d’annonce**:</span><span class="sxs-lookup"><span data-stu-id="ec48d-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="ec48d-125">**Numéro de téléphone du standard automatique** Sélectionnez le numéro de téléphone du standard automatique de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="ec48d-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="ec48d-126">Pour plus d’informations sur les fonctionnalités et fonctionnalités d’annonce, voir [planifier l’application d’annonce dans Skype entreprise 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ec48d-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="ec48d-127">Pour plus d’informations sur l’utilisation de plages de numéros non attribués, reportez-vous à la rubrique [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="ec48d-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


