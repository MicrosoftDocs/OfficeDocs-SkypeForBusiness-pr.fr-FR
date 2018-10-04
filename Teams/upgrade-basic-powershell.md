---
title: Mise à niveau des commandes PowerShell base - Microsoft Teams
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisoires pour la mise à niveau vers les équipes si le centre d’administration n’a pas activée dans votre client
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b5b3907a34d88dfebe5ad085ccc77da61d2237e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373234"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="fc4ce-103">Mettre à niveau vos utilisateurs Skype pour Business Online vers Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc4ce-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="fc4ce-104">Les commandes décrites dans cet article sont conçus pour être utilisés dans le cadre de la liste de contrôle [De mise à niveau de base](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="fc4ce-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="fc4ce-105">Les aspects techniques de migration de votre mise à niveau en avertir les utilisateurs que Skype pour les entreprises sera mise à niveau vers les équipes et puis en les déplaçant vers un mode **d’équipes uniquement** .</span><span class="sxs-lookup"><span data-stu-id="fc4ce-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="fc4ce-106">Ces étapes peuvent être effectuées via un Skype pour la session Windows PowerShell à distance Business ou par le biais du Microsoft Teams & Skype entreprise centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="fc4ce-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams & Skype for Business Admin Center.</span></span> 
 
<span data-ttu-id="fc4ce-107">Nous allons présentant activement mise à niveau d’outils dans les [équipes Microsoft & Skype entreprise centre d’administration](manage-teams-skypeforbusiness-admin-center.md)et il doit être disponible prochainement sur votre client.</span><span class="sxs-lookup"><span data-stu-id="fc4ce-107">We're actively rolling out upgrade tooling in the [Microsoft Teams & Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="fc4ce-108">Dès qu’elle est disponible, vous trouverez des informations sur la migration de vos utilisateurs dans la [définition de votre coexistence et les paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="fc4ce-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span> 
 
<span data-ttu-id="fc4ce-109">Si vous êtes prêt à mettre à niveau dès aujourd'hui, vous pouvez utiliser les commandes [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fc4ce-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span> 
 

|     <span data-ttu-id="fc4ce-110">Mise à niveau de base étape #</span><span class="sxs-lookup"><span data-stu-id="fc4ce-110">Upgrade Basic step #</span></span>     |                                                                      <span data-ttu-id="fc4ce-111">Mode</span><span class="sxs-lookup"><span data-stu-id="fc4ce-111">Mode</span></span>                                                                      |                                                                                                                       <span data-ttu-id="fc4ce-112">Commande PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc4ce-112">PowerShell command</span></span>                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [<span data-ttu-id="fc4ce-113">5</span><span class="sxs-lookup"><span data-stu-id="fc4ce-113">5</span></span>](upgrade-basic.md#step-5) |            <span data-ttu-id="fc4ce-114">Îles + avertir le Skype pour l’utilisateur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="fc4ce-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="fc4ce-115">(Utilisez cette commande si des utilisateurs sont actuellement en mode **(îles)** (par défaut))</span><span class="sxs-lookup"><span data-stu-id="fc4ce-115">(Use this command if users are currently in **Islands** mode (default))</span></span>             | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="fc4ce-116">*(par exemple, $SipAddress = 'TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="fc4ce-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="fc4ce-117">5</span><span class="sxs-lookup"><span data-stu-id="fc4ce-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="fc4ce-118">Skype pour les entreprises uniquement + avertir le Skype pour l’utilisateur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="fc4ce-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="fc4ce-119">(Utilisez cette commande si des utilisateurs sont actuellement en mode **Skype pour les entreprises uniquement** )</span><span class="sxs-lookup"><span data-stu-id="fc4ce-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> |                                ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress```                                |
| [<span data-ttu-id="fc4ce-120">7</span><span class="sxs-lookup"><span data-stu-id="fc4ce-120">7</span></span>](upgrade-basic.md#step-7) |                                                                   <span data-ttu-id="fc4ce-121">Équipes uniquement</span><span class="sxs-lookup"><span data-stu-id="fc4ce-121">Teams Only</span></span>                                                                   |                               ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress```                                |

