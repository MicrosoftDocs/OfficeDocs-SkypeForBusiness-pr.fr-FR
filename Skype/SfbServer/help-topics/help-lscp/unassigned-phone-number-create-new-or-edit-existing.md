---
title: Unassigned Phone Number Create New or Edit Existing
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 51c3f640bd9d98bcda9d5dd69406461e9c8393fd
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711741"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="fd5c2-104">Numéro de téléphone non attribué : créer un nouveau ou modifier un numéro existant</span><span class="sxs-lookup"><span data-stu-id="fd5c2-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="fd5c2-p102">Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd5c2-p103">Lorsque vous avez terminé de créer une nouvelle plage de numéros non affectés ou d’en modifier une existante, cliquez sur **OK** pour retourner à la page **Numéro non attribué** qui répertorie toutes les plages de numéros. Les modifications que vous avez apportées dans la page **Nouvelle plage de numéros non attribués** et la page **Modifier la plage de numéros non attribués** sont validées dans la base de données seulement lorsque vous cliquez sur **Valider tout** dans la page **Numéro non attribué**.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-p103">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="fd5c2-109">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="fd5c2-109">UI Reference</span></span>

<span data-ttu-id="fd5c2-110">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="fd5c2-111">**Nom** Tapez un nom descriptif qui identifie la plage de numéro non assignés.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="fd5c2-112">Une fois que vous avez enregistrez la plage, ce nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="fd5c2-113">**Plage de nombres** Dans le premier champ, tapez le numéro de début de la plage de numéro non assignés.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="fd5c2-114">Dans le deuxième champ, tapez le numéro de fin de la plage.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="fd5c2-115">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="fd5c2-116">Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="fd5c2-117">Le nombre doit correspondre à l’expression régulière `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` .</span><span class="sxs-lookup"><span data-stu-id="fd5c2-117">The number must match the regular expression `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?`.</span></span> <span data-ttu-id="fd5c2-118">Cela signifie que le numéro peut commencer par la chaîne (si vous ne spécifiez pas cette chaîne, elle sera automatiquement ajoutée pour vous), un signe plus (+) et un chiffre de 1 à `tel:` 9.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-118">This means the number may begin with the string `tel:` (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="fd5c2-119">Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="fd5c2-120">**Service d’annonce** Sélectionnez **Annonce** pour que l’application Annonce gère l’appel entrant ou la um **Exchange** pour qu’une Standard automatique exchange gère l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="fd5c2-121">Si vous avez sélectionné **Annonce** comme **Service d’annonce** :</span><span class="sxs-lookup"><span data-stu-id="fd5c2-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="fd5c2-122">**FQDN du serveur de destination** Sélectionnez l’ID de service du service d’application qui exécute l’application d’annonce qui gérera les appels entrants vers cette plage de numéros non assignés.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="fd5c2-123">**Annonce** Sélectionnez l’annonce à lire pour cette plage de numéros non signés.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="fd5c2-124">Si vous avez sélectionné **Messagerie unifiée Exchange** comme **Service d’annonce** :</span><span class="sxs-lookup"><span data-stu-id="fd5c2-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="fd5c2-125">**Standard automatique numéro de téléphone** Sélectionnez le numéro de téléphone de la Standard automatique de la Standard automatique.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="fd5c2-126">Pour plus d’informations sur les fonctionnalités d’annonce, voir [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="fd5c2-127">Pour plus d’informations sur l’utilisation de plages de numéros non attribués, voir [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="fd5c2-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


