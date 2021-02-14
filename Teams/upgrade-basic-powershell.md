---
title: Mise à niveau de base de PowerShell| Microsoft Teams| Accorder une stratégie Interop de mise à niveau
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez un stopgap pour la mise à niveau vers Microsoft Teams si le Centre d’administration n’a pas été allumé dans votre client.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809094"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="3b966-103">Mise à niveau de vos utilisateurs de Skype Entreprise Online vers Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b966-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="3b966-104">Les commandes décrites dans cet article sont conçues pour être utilisées dans le cadre de la liste de vérification [Mise à](https://aka.ms/UpgradeBasic) niveau de base.</span><span class="sxs-lookup"><span data-stu-id="3b966-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="3b966-105">Les aspects de la migration technique de votre mise à niveau impliquent d’informer vos utilisateurs que Skype Entreprise va mettre à niveau vers Teams, puis les déplacer vers un mode **Teams** uniquement.</span><span class="sxs-lookup"><span data-stu-id="3b966-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="3b966-106">Ces étapes peuvent être réalisées via une session d’Windows PowerShell à distance Skype Entreprise ou via le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3b966-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="3b966-107">Nous travaillons activement au déploiement des outils de mise à niveau dans le Centre d’administration [Microsoft Teams.](manage-teams-skypeforbusiness-admin-center.md)Celui-ci devrait bientôt être disponible sur votre client.</span><span class="sxs-lookup"><span data-stu-id="3b966-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="3b966-108">Dès qu’elle est disponible, des informations sur la migration de vos utilisateurs sont disponibles dans Paramètres de coexistence et de mise [à niveau.](https://aka.ms/SkypeToTeams-SetCoexistence)</span><span class="sxs-lookup"><span data-stu-id="3b966-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="3b966-109">Si vous êtes prêt à mettre à niveau dès aujourd’hui, vous pouvez utiliser les commandes [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="3b966-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="3b966-110">Étape de base de la mise à niveau #</span><span class="sxs-lookup"><span data-stu-id="3b966-110">Upgrade Basic step #</span></span> | <span data-ttu-id="3b966-111">Mode</span><span class="sxs-lookup"><span data-stu-id="3b966-111">Mode</span></span> | <span data-ttu-id="3b966-112">Commande PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b966-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="3b966-113">5</span><span class="sxs-lookup"><span data-stu-id="3b966-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="3b966-114">Islands + Notify the Skype for Business User</span><span class="sxs-lookup"><span data-stu-id="3b966-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="3b966-115">(Utilisez cette commande si les utilisateurs sont actuellement en mode **Îles** (par défaut))</span><span class="sxs-lookup"><span data-stu-id="3b966-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="3b966-116">*(par exemple, $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="3b966-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="3b966-117">5</span><span class="sxs-lookup"><span data-stu-id="3b966-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="3b966-118">Skype Entreprise + Notification à l’utilisateur Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="3b966-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="3b966-119">(Utilisez cette commande si les utilisateurs sont actuellement en mode **Skype** Entreprise uniquement)</span><span class="sxs-lookup"><span data-stu-id="3b966-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="3b966-120">7</span><span class="sxs-lookup"><span data-stu-id="3b966-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="3b966-121">Teams uniquement</span><span class="sxs-lookup"><span data-stu-id="3b966-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
