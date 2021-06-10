---
title: Mise à niveau de base de PowerShell| Microsoft Teams| Accorder une stratégie Interop de mise à niveau
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez un stopgap pour la mise à niveau vers Microsoft Teams’administration si le Centre d’administration n’est pas allumé dans votre client.
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
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120538"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="5ef66-103">Mise à niveau de vos utilisateurs de Skype Entreprise Online vers Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ef66-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="5ef66-104">Les commandes décrites dans cet article sont conçues pour être utilisées dans le cadre de la liste de contrôle [Mise à](./upgrade-start-here.md) niveau de base.</span><span class="sxs-lookup"><span data-stu-id="5ef66-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="5ef66-105">Les aspects de la migration technique de votre mise à niveau impliquent d’informer vos utilisateurs que Skype Entreprise va mettre à niveau vers Teams puis les déplacer vers un **mode** Teams seul.</span><span class="sxs-lookup"><span data-stu-id="5ef66-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="5ef66-106">Ces étapes peuvent être réalisées via une session Skype Entreprise’administration Windows PowerShell distance ou via le Microsoft Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="5ef66-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="5ef66-107">Nous travaillons activement au déploiement des [](manage-teams-skypeforbusiness-admin-center.md)outils de mise à niveau dans le Microsoft Teams d’administration, qui doivent bientôt être disponibles sur votre client.</span><span class="sxs-lookup"><span data-stu-id="5ef66-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="5ef66-108">Dès qu’elle est disponible, vous trouverez des informations sur la migration de vos utilisateurs dans La définition de vos paramètres de coexistence et de mise [à niveau.](./setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5ef66-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="5ef66-109">Si vous êtes prêt à mettre à niveau dès aujourd’hui, vous pouvez utiliser les commandes [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5ef66-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="5ef66-110">Étape de base de la mise à niveau #</span><span class="sxs-lookup"><span data-stu-id="5ef66-110">Upgrade Basic step #</span></span> | <span data-ttu-id="5ef66-111">Mode</span><span class="sxs-lookup"><span data-stu-id="5ef66-111">Mode</span></span> | <span data-ttu-id="5ef66-112">Commande PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ef66-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="5ef66-113">5</span><span class="sxs-lookup"><span data-stu-id="5ef66-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="5ef66-114">Islands + Notify the Skype Entreprise User</span><span class="sxs-lookup"><span data-stu-id="5ef66-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="5ef66-115">(Utilisez cette commande si les utilisateurs sont actuellement en mode **Îles** (par défaut))</span><span class="sxs-lookup"><span data-stu-id="5ef66-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="5ef66-116">*(par exemple, $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="5ef66-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="5ef66-117">5</span><span class="sxs-lookup"><span data-stu-id="5ef66-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="5ef66-118">Skype Entreprise + Informer l’utilisateur Skype Entreprise’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5ef66-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="5ef66-119">(Utilisez cette commande si les utilisateurs sont actuellement en **Skype Entreprise** mode uniquement)</span><span class="sxs-lookup"><span data-stu-id="5ef66-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="5ef66-120">7</span><span class="sxs-lookup"><span data-stu-id="5ef66-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="5ef66-121">Teams Uniquement</span><span class="sxs-lookup"><span data-stu-id="5ef66-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |