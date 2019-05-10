---
title: Processus de mise à jour des équipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Découvrez comment le client de bureau équipes est mis à jour.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829095"
---
# <a name="teams-update-process"></a><span data-ttu-id="316ec-103">Processus de mise à jour des équipes</span><span class="sxs-lookup"><span data-stu-id="316ec-103">Teams update process</span></span>

<span data-ttu-id="316ec-104">Les équipes Web App est mis à jour toutes les semaines.</span><span class="sxs-lookup"><span data-stu-id="316ec-104">The Teams Web App is updated weekly.</span></span>

<span data-ttu-id="316ec-105">Les équipes client de bureau sont mises à jour toutes les deux semaines après rigoureux interne et la validation par le biais de notre programme TAP (Technology Adoption).</span><span class="sxs-lookup"><span data-stu-id="316ec-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="316ec-106">Cela est généralement réalisée un mardi.</span><span class="sxs-lookup"><span data-stu-id="316ec-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="316ec-107">Si une mise à jour critique est requise, les équipes seront contourner cette planification et version de la mise à jour dès qu’elle est disponible.</span><span class="sxs-lookup"><span data-stu-id="316ec-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="316ec-108">Le client de bureau se met à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="316ec-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="316ec-109">Vérifie les équipes met à jour toutes les quelques heures en arrière-plan, télécharge et puis attend que l’ordinateur doit être inactif avant la mise à jour en mode silencieux.</span><span class="sxs-lookup"><span data-stu-id="316ec-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="316ec-110">Les utilisateurs peuvent télécharger manuellement les mises à jour en cliquant sur **vérifier les mises à jour** dans le menu déroulant **profil** sur la partie supérieure droite de l’application.</span><span class="sxs-lookup"><span data-stu-id="316ec-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="316ec-111">Si une mise à jour est disponible, il sera téléchargé et installé en mode silencieux lorsque l’ordinateur est inactif.</span><span class="sxs-lookup"><span data-stu-id="316ec-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="316ec-112">Les utilisateurs doivent être connectés les mises à jour à télécharger.</span><span class="sxs-lookup"><span data-stu-id="316ec-112">Users need to be signed in for updates to be downloaded.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="316ec-113">Qu’advient-il des mises à jour pour Office 365 ProPlus ?</span><span class="sxs-lookup"><span data-stu-id="316ec-113">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="316ec-114">Les équipes est installé par défaut avec les nouvelles installations d’Office 365 ProPlus, comme décrit dans [Déployer les équipes Microsoft Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="316ec-114">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="316ec-115">Les équipes suit son propre processus de mise à jour, comme indiqué ci-dessus et non le processus de mise à jour pour les autres applications de bureaux, telles que Word et Excel.</span><span class="sxs-lookup"><span data-stu-id="316ec-115">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="316ec-116">Qu’advient-il des mises à jour des équipes sur VDI ?</span><span class="sxs-lookup"><span data-stu-id="316ec-116">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="316ec-117">Clients équipes sur l’Infrastructure VDI (Virtual Desktop) ne sont pas automatiquement mis à jour la façon dont les clients non - VDI équipes.</span><span class="sxs-lookup"><span data-stu-id="316ec-117">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="316ec-118">Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau fichier MSI, comme décrit dans les instructions pour [Installer les équipes sur VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="316ec-118">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="316ec-119">Vous devez désinstaller la version actuelle de mise à jour vers une version plus récente.</span><span class="sxs-lookup"><span data-stu-id="316ec-119">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="316ec-120">Administrateurs peuvent déployer des mises à jour au lieu des équipes de mise à jour automatique ?</span><span class="sxs-lookup"><span data-stu-id="316ec-120">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="316ec-121">Les équipes ne donne pas d’administrateurs de déployer des mises à jour par le biais de tout mécanisme de livraison.</span><span class="sxs-lookup"><span data-stu-id="316ec-121">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
