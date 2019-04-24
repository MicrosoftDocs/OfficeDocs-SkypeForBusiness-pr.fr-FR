---
title: Numéro de téléphone non attribués créer ou modifier une existant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 176e1b0485b9fc9584b770e4708cad0bf0662e00
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32221344"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="80d36-104">Numéro de téléphone non attribué : en créer un autre ou en modifier un existant</span><span class="sxs-lookup"><span data-stu-id="80d36-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="80d36-105">Messagerie unifiée Exchange reste disponible dans Skype pour Business Server 2019 lorsque vous intégrez Skype pour les entreprises 2019 avec Exchange 2013 ou 2016 Exchange.</span><span class="sxs-lookup"><span data-stu-id="80d36-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="80d36-106">En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est la déduplication emphasised au profit des fonctionnalités de la messagerie vocale dans le nuage et de standard automatique de nuage.</span><span class="sxs-lookup"><span data-stu-id="80d36-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="80d36-p103">Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="80d36-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80d36-109">Lorsque vous avez terminé de créer une nouvelle plage de numéros non attribuée ou modifier un existant, cliquez sur **OK** pour revenir à la page **Numéro non attribué** qui répertorie toutes les plages de numéros.</span><span class="sxs-lookup"><span data-stu-id="80d36-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="80d36-110">Les modifications effectuées sur la page **Nouveau Unassigned Number Range** ou la page **Modifier les Rage de numéro non attribué** ne sont pas validées dans la base de données jusqu'à ce que vous cliquez sur **valider tout** dans la page **Numéro non attribué** .</span><span class="sxs-lookup"><span data-stu-id="80d36-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="80d36-111">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="80d36-111">UI Reference</span></span>

<span data-ttu-id="80d36-112">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="80d36-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="80d36-113">**Nom** Tapez un nom descriptif qui identifie la plage de numéros non attribuée.</span><span class="sxs-lookup"><span data-stu-id="80d36-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="80d36-114">Une fois que vous enregistrez la plage, ce nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="80d36-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="80d36-115">**Numéro de plage** Dans le premier champ, tapez le numéro de début de la plage de numéros non attribué.</span><span class="sxs-lookup"><span data-stu-id="80d36-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="80d36-116">Dans le deuxième champ, tapez le numéro de fin de la plage.</span><span class="sxs-lookup"><span data-stu-id="80d36-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="80d36-117">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="80d36-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="80d36-118">Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.</span><span class="sxs-lookup"><span data-stu-id="80d36-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="80d36-119">Le numéro doit correspondre à l’expression régulière (Tél. :) ? (\+) ? [1-9] \d{0,17}( ; ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="80d36-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="80d36-120">Cela signifie que le nombre peut commencer par la chaîne tel : (si vous ne spécifiez pas cette chaîne il est automatiquement ajouté pour vous), un signe plus (+) et un chiffre 1 à 9.</span><span class="sxs-lookup"><span data-stu-id="80d36-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="80d36-121">Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="80d36-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="80d36-122">**Service d’annonce** Sélectionnez **annonce** pour que l’application d’annonce à gérer l’appel entrant ou **Messagerie unifiée Exchange** pour utiliser un standard automatique Exchange UM pour gérer l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="80d36-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="80d36-123">Si vous avez sélectionné **annonce** comme **service**d’annonce :</span><span class="sxs-lookup"><span data-stu-id="80d36-123">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="80d36-124">**Nom de domaine complet du serveur de destination** Sélectionnez l’ID de service du service d’Application qui exécute l’application d’annonce qui gèrera les appels entrants à cette plage de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="80d36-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="80d36-125">**Annonce** Sélectionnez l’annonce à associer à cette plage de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="80d36-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="80d36-126">Si vous avez sélectionné **La messagerie unifiée Exchange** pour **le service d’annonce**:</span><span class="sxs-lookup"><span data-stu-id="80d36-126">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="80d36-127">**Numéro de téléphone de standard automatique** Sélectionnez le numéro de téléphone du standard automatique Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="80d36-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="80d36-128">Pour plus d’informations sur les fonctionnalités d’annonce de, voir [planification de l’application d’annonce dans Skype pour les entreprises](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="80d36-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="80d36-129">Pour plus d’informations sur l’utilisation de plages de numéros non attribués, reportez-vous à la rubrique [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="80d36-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


