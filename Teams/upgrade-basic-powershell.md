---
title: Base PowerShell mise à niveau | Les équipes Microsoft | Stratégie de mise à niveau Grant interopérabilité
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisoires pour la mise à niveau vers les équipes si le centre d’administration n’a pas activée dans votre client
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f81e796d893ef17138398c8a5739a4284bcfc4a3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459739"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="b182f-103">Mettre à niveau vos utilisateurs Skype pour Business Online vers Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b182f-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="b182f-104">Les commandes décrites dans cet article sont conçus pour être utilisés dans le cadre de la liste de contrôle [De mise à niveau de base](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="b182f-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="b182f-105">Les aspects techniques de migration de votre mise à niveau en avertir les utilisateurs que Skype pour les entreprises sera mise à niveau vers les équipes et puis en les déplaçant vers un mode **d’équipes uniquement** .</span><span class="sxs-lookup"><span data-stu-id="b182f-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="b182f-106">Ces étapes peuvent être accomplies via un Skype pour la session Windows PowerShell à distance Business ou via le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b182f-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="b182f-107">Nous allons présentant activement mise à niveau d’outils dans le [Centre d’administration de Microsoft équipes](manage-teams-skypeforbusiness-admin-center.md), et il doit être disponible prochainement sur votre client.</span><span class="sxs-lookup"><span data-stu-id="b182f-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="b182f-108">Dès qu’elle est disponible, vous trouverez des informations sur la migration de vos utilisateurs dans la [définition de votre coexistence et les paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="b182f-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="b182f-109">Si vous êtes prêt à mettre à niveau dès aujourd'hui, vous pouvez utiliser les commandes [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="b182f-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="b182f-110">Mise à niveau de base étape #</span><span class="sxs-lookup"><span data-stu-id="b182f-110">Upgrade Basic step #</span></span> | <span data-ttu-id="b182f-111">Mode</span><span class="sxs-lookup"><span data-stu-id="b182f-111">Mode</span></span> | <span data-ttu-id="b182f-112">Commande PowerShell</span><span class="sxs-lookup"><span data-stu-id="b182f-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="b182f-113">5</span><span class="sxs-lookup"><span data-stu-id="b182f-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="b182f-114">Îles + avertir le Skype pour l’utilisateur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="b182f-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="b182f-115">(Utilisez cette commande si des utilisateurs sont actuellement en mode **(îles)** (par défaut))</span><span class="sxs-lookup"><span data-stu-id="b182f-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="b182f-116">*(par exemple, $SipAddress = 'TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="b182f-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="b182f-117">5</span><span class="sxs-lookup"><span data-stu-id="b182f-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="b182f-118">Skype pour les entreprises uniquement + avertir le Skype pour l’utilisateur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="b182f-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="b182f-119">(Utilisez cette commande si des utilisateurs sont actuellement en mode **Skype pour les entreprises uniquement** )</span><span class="sxs-lookup"><span data-stu-id="b182f-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="b182f-120">7</span><span class="sxs-lookup"><span data-stu-id="b182f-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="b182f-121">Équipes uniquement</span><span class="sxs-lookup"><span data-stu-id="b182f-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |