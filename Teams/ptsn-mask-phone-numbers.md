---
title: Masquez les numéros de téléphone dans les réunions Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrir comment masquage des numéros de téléphone dans les réunions Microsoft Teams
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117712"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="62034-103">Masquez les numéros de téléphone dans les réunions Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="62034-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="62034-104">Pour une confidentialité supplémentaire, les numéros de téléphone des participants qui se appellent à une réunion Teams à l’aide de l’audioconférence sont entièrement affichés aux participants internes.</span><span class="sxs-lookup"><span data-stu-id="62034-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="62034-105">Les numéros sont masqués des participants extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="62034-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="62034-106">Ce paramètre est le paramètre par défaut pour toutes les organisations.</span><span class="sxs-lookup"><span data-stu-id="62034-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="62034-107">Le nombre masqué s’affiche comme illustré dans l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="62034-107">The masked number is displayed as shown in the following image:</span></span>

![Exemple de numéro de téléphone masqué](media/hiddenPhoneNum.png)

<span data-ttu-id="62034-109">Pour des cas d’utilisation spécifiques dans le secteur, les administrateurs ont la possibilité de choisir l’organisation des numéros de téléphone des participants à l’audioconférence dans les réunions organisées dans leur client.</span><span class="sxs-lookup"><span data-stu-id="62034-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="62034-110">Les administrateurs ont le choix entre trois options :</span><span class="sxs-lookup"><span data-stu-id="62034-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="62034-111">Les numéros de téléphone ne sont masqués que pour les participants externes.</span><span class="sxs-lookup"><span data-stu-id="62034-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="62034-112">Les participants qui appartiennent au client de l’organisateur de la réunion voient toujours le numéro de téléphone complet.</span><span class="sxs-lookup"><span data-stu-id="62034-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="62034-113">Les numéros de téléphone sont masqués pour toutes les personnes de la réunion à l’exception de l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="62034-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="62034-114">Les numéros de téléphone ne sont pas tâches, ce qui les rend visibles à tous les autres personnes de la réunion.</span><span class="sxs-lookup"><span data-stu-id="62034-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="62034-115">Ce paramètre s’applique à toutes les surfaces de la réunion où les numéros de téléphone sont exposés.</span><span class="sxs-lookup"><span data-stu-id="62034-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="62034-116">Utiliser Microsoft PowerShell pour définir le masquage des numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="62034-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="62034-117">Pour modifier le paramètre de masquage du réseau téléphonique commuté (PSTN), définissez le paramètre de **`MaskPstnNumbersType`** l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) sur l’une des options disponibles.</span><span class="sxs-lookup"><span data-stu-id="62034-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="62034-118">Pour masquer les numéros de téléphone des participants externes uniquement, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="62034-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="62034-119">Pour masquer les numéros de téléphone de tous les participants à la réunion (à l’exception de l’organisateur), exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="62034-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="62034-120">Pour désactiver le masquage des numéros de téléphone, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="62034-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```