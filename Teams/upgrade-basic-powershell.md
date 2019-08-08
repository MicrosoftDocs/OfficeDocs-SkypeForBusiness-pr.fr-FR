---
title: PowerShell de mise à niveau de base | Microsoft teams | Accorder une stratégie d’interopérabilité de mise à niveau
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Stopgap pour la mise à niveau vers teams si le centre d’administration ne s’est pas allumé dans votre client
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 945422f6bb61fca8d2b17379a7c9bf4695e7dd09
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236540"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="55855-103">Mise à niveau de vos utilisateurs de Skype entreprise Online vers Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="55855-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="55855-104">Les commandes décrites dans cet article sont conçues pour être utilisées dans le cadre de la liste de vérification de base de la [mise à niveau](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="55855-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="55855-105">Les aspects de migration techniques de votre mise à niveau impliquent de notifier vos utilisateurs de la mise à niveau vers teams de Skype entreprise, puis de les déplacer vers le mode **équipes uniquement** .</span><span class="sxs-lookup"><span data-stu-id="55855-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="55855-106">Ces étapes peuvent être effectuées par le biais d’une session Windows PowerShell distante Skype entreprise ou du centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55855-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="55855-107">Le déploiement des outils de mise à niveau dans le [Centre d’administration de Microsoft teams](manage-teams-skypeforbusiness-admin-center.md), nous vous conseillons de le faire bientôt sur votre client.</span><span class="sxs-lookup"><span data-stu-id="55855-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="55855-108">Dès qu’il est disponible, vous pouvez trouver des informations sur la migration de vos utilisateurs dans le cadre de [la configuration de votre coexistence et de vos paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="55855-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="55855-109">Si vous êtes prêt à effectuer la mise à niveau vers la version actuelle, vous pouvez utiliser les commandes [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="55855-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="55855-110">Étape de mise à niveau de base #</span><span class="sxs-lookup"><span data-stu-id="55855-110">Upgrade Basic step #</span></span> | <span data-ttu-id="55855-111">Veille</span><span class="sxs-lookup"><span data-stu-id="55855-111">Mode</span></span> | <span data-ttu-id="55855-112">Commande PowerShell</span><span class="sxs-lookup"><span data-stu-id="55855-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="55855-113">5</span><span class="sxs-lookup"><span data-stu-id="55855-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="55855-114">Îles + informer l’utilisateur de Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="55855-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="55855-115">(Utilisez cette commande si les utilisateurs sont actuellement en mode **îlot** (par défaut))</span><span class="sxs-lookup"><span data-stu-id="55855-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="55855-116">*(par exemple, $SipAddress = 'TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="55855-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="55855-117">5</span><span class="sxs-lookup"><span data-stu-id="55855-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="55855-118">Skype entreprise uniquement + informer l’utilisateur de Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="55855-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="55855-119">(Utilisez cette commande si les utilisateurs sont actuellement en mode **Skype entreprise uniquement** )</span><span class="sxs-lookup"><span data-stu-id="55855-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="55855-120">7</span><span class="sxs-lookup"><span data-stu-id="55855-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="55855-121">Équipes uniquement</span><span class="sxs-lookup"><span data-stu-id="55855-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |
