---
title: Utiliser l’outil de récupération de Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cet article décrit l’utilisation de l’outil de récupération pour Salles Microsoft Teams, que vous utiliseriez pour mettre un système hors limites à l’état pris en charge.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117492"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="3f24a-103">Utiliser l’outil de récupération de Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="3f24a-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="3f24a-104">Cet article décrit l’utilisation de l’outil de récupération pour Salles Microsoft Teams, que vous utiliseriez pour mettre un système hors limites à l’état pris en charge.</span><span class="sxs-lookup"><span data-stu-id="3f24a-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="3f24a-105">Cet outil doit être appliqué lorsque la console de Salles Microsoft Teams affiche une erreur « la config système est à jour » ou avant d’effectuer une restauration d’usine du bouton [de](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)commande.</span><span class="sxs-lookup"><span data-stu-id="3f24a-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f24a-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="3f24a-106">Prerequisites</span></span>

<span data-ttu-id="3f24a-107">Téléchargez le [package d Salles Microsoft Teams d’installation](https://go.microsoft.com/fwlink/?linkid=851168) le plus récent et extrayez-le sur une clé USB ou un partage réseau accessible à Salles Microsoft Teams appareil.</span><span class="sxs-lookup"><span data-stu-id="3f24a-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="3f24a-108">L’extraction des fichiers du fichier MSI peut être réalisée par de nombreux moyens.</span><span class="sxs-lookup"><span data-stu-id="3f24a-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="3f24a-109">Tout mécanisme qui extrait tous les fichiers et préserve leur structure d’annuaire est acceptable.</span><span class="sxs-lookup"><span data-stu-id="3f24a-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="3f24a-110">Une de ces manières consiste à utiliser la commande qui représente le chemin d’accès complet au package d’installation de Microsoft Teams Room et représente le chemin d’accès complet au dossier dans lequel vous souhaitez extraire les `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` fichiers.</span><span class="sxs-lookup"><span data-stu-id="3f24a-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="3f24a-111">Exécution de l’outil</span><span class="sxs-lookup"><span data-stu-id="3f24a-111">Running the tool</span></span>

1) <span data-ttu-id="3f24a-112">Connectez-vous au compte d’administrateur sur Salles Microsoft Teams appareil, puis lancez une invite de commandes avec élévation de privilèges.</span><span class="sxs-lookup"><span data-stu-id="3f24a-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="3f24a-113">Vérifiez à partir Salles Microsoft Teams l’appareil que vous pouvez accéder au fichier inclus dans les fichiers extraits du `RecoveryTool.ps1 file` package d’installation Salles Microsoft Teams’installation.</span><span class="sxs-lookup"><span data-stu-id="3f24a-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="3f24a-114">Le kit est possible sur le partage réseau ou le lecteur USB utilisé lors de la préparation des conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="3f24a-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="3f24a-115">`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`Exécuter.</span><span class="sxs-lookup"><span data-stu-id="3f24a-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="3f24a-116">Pour effectuer une restauration d’usine :</span><span class="sxs-lookup"><span data-stu-id="3f24a-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="3f24a-117">Lorsque le script vous y invite, sélectionnez l’option 2 : **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="3f24a-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="3f24a-118">Si BitLocker est désactivé, suivez les instructions fournies à la fin de la sortie du script pour la désactiver.</span><span class="sxs-lookup"><span data-stu-id="3f24a-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="3f24a-119">Effectuez la restauration d’usine.</span><span class="sxs-lookup"><span data-stu-id="3f24a-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="3f24a-120">Ouvrez **l’Paramètres,** puis sélectionnez Mettre à jour **& sécurité**</span><span class="sxs-lookup"><span data-stu-id="3f24a-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="3f24a-121">Accédez à **l’onglet** Récupération.</span><span class="sxs-lookup"><span data-stu-id="3f24a-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="3f24a-122">Sous **Réinitialiser ce PC,** **sélectionnez Commencer**</span><span class="sxs-lookup"><span data-stu-id="3f24a-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="3f24a-123">Sélectionnez **Supprimer tout,** puis **Suivant et** **Réinitialiser**</span><span class="sxs-lookup"><span data-stu-id="3f24a-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="3f24a-124">L Salles Microsoft Teams de messagerie peut devenir inutilisable si l’option Conserver mes fichiers - Supprime les applications et les **paramètres,** mais conserve votre option de fichiers personnels est sélectionnée pendant le Windows réinitialiser.</span><span class="sxs-lookup"><span data-stu-id="3f24a-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="3f24a-125">Ne sélectionnez pas cette option.</span><span class="sxs-lookup"><span data-stu-id="3f24a-125">Do not select this option.</span></span>
      5. <span data-ttu-id="3f24a-126">Le système redémarre plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="3f24a-126">The system will reboot multiple times.</span></span> <span data-ttu-id="3f24a-127">Une fois la réinitialisation terminée, le système s’affiche Windows’écran « Out-of-box Experience » (OOBE).</span><span class="sxs-lookup"><span data-stu-id="3f24a-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="3f24a-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f24a-128">See also</span></span>

[<span data-ttu-id="3f24a-129">Aide Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="3f24a-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="3f24a-130">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="3f24a-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)