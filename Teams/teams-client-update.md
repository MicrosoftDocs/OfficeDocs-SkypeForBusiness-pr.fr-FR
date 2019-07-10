---
title: Mises à jour de teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Découvrez les mises à jour du client de bureau Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5280e03e316dfcde3bda9b62520fa513f3157a
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2019
ms.locfileid: "35602270"
---
# <a name="teams-update-process"></a><span data-ttu-id="a9bd3-103">Processus de mise à jour des équipes</span><span class="sxs-lookup"><span data-stu-id="a9bd3-103">Teams update process</span></span>

<span data-ttu-id="a9bd3-104">Team Web App est mis à jour chaque semaine.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="a9bd3-105">Les mises à jour du client de bureau teams sont divulguées toutes les deux semaines après un test interne rigoureux et une validation par le biais de notre programme d’adoption de technologie (TAP).</span><span class="sxs-lookup"><span data-stu-id="a9bd3-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="a9bd3-106">Cette opération est généralement effectuée sur un mardi.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="a9bd3-107">Si une mise à jour critique est requise, teams ignorera ce planning et libérera la mise à jour dès qu’il sera disponible.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="a9bd3-108">Le client de bureau est mis à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="a9bd3-109">Teams vérifie les mises à jour toutes les heures en coulisse, télécharge, puis attend que l’ordinateur soit inactif avant d’installer la mise à jour en silence.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="a9bd3-110">Les utilisateurs peuvent également télécharger manuellement les mises à jour en cliquant sur **Rechercher les mises à jour** dans le menu déroulant **Profil** en haut à droite de l’application.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="a9bd3-111">Si une mise à jour est disponible, elle est téléchargée et installée en silence lorsque l’ordinateur est inactif.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="a9bd3-112">Les utilisateurs doivent être connectés pour pouvoir télécharger les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="a9bd3-113">À compter du 9 juillet, 2019, les mises à jour du client teams utilisent une bande passante réseau nettement inférieure au cours de la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-113">Starting July 9, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="a9bd3-114">Cette option est activée par défaut et ne nécessite aucune action de la part des administrateurs ou des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-114">This is turned on by default and requires no action from admins or users.</span></span>


## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="a9bd3-115">À propos des mises à jour d’Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="a9bd3-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="a9bd3-116">Teams est installé par défaut avec les nouvelles installations d’Office 365 ProPlus, comme décrit dans la rubrique [déploiement de Microsoft teams avec Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="a9bd3-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="a9bd3-117">Teams suit son propre processus de mise à jour, tel que décrit ci-dessus, mais pas le processus de mise à jour des autres applications Office, telles que Word et Excel.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="a9bd3-118">Pour en savoir plus, voir [Présentation des canaux de mise à jour d’Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="a9bd3-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="a9bd3-119">À propos des mises à jour apportées aux équipes sur VDI</span><span class="sxs-lookup"><span data-stu-id="a9bd3-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="a9bd3-120">Les clients teams de l’infrastructure de bureau virtuel (VDI) ne sont pas automatiquement mis à jour de manière à ce qu’ils soient.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="a9bd3-121">Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau MSI comme décrit dans les instructions d' [installation d’teams sur VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="a9bd3-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="a9bd3-122">Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="a9bd3-123">Les administrateurs peuvent-ils déployer des mises à jour au lieu de la mise à jour automatique des équipes?</span><span class="sxs-lookup"><span data-stu-id="a9bd3-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="a9bd3-124">Teams ne donne pas aux administrateurs la possibilité de déployer des mises à jour par le biais d’un mécanisme de remise.</span><span class="sxs-lookup"><span data-stu-id="a9bd3-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
