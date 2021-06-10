---
title: Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Découvrez comment déplacer des utilisateurs vers Skype Entreprise Online.
ms.openlocfilehash: 883db98a424c254e6792fd651594b02201a311f9
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863195"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="f5163-103">Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f5163-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="f5163-104">Après avoir fait passer un utilisateur de l’local vers Skype Entreprise Online, l’utilisateur interagit avec Skype Entreprise Online pour sa fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="f5163-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="f5163-105">Tous les contacts qui existaient en local seront disponibles dans Skype Entreprise Online, et toutes les réunions existantes organisées par l’utilisateur à l’avenir sont mises à jour de sorte que les liens pointent vers Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="f5163-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="f5163-106">Si l’utilisateur est activé pour l’audioconférence, les réunions incluent également des coordonnées d’accès.</span><span class="sxs-lookup"><span data-stu-id="f5163-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="f5163-107">Pour déplacer des utilisateurs d’un environnement local vers Skype Entreprise Online, utilisez la cmdlet Move-CsUser ou le Panneau de Skype Entreprise Server, qui sont tous deux des outils locaux.</span><span class="sxs-lookup"><span data-stu-id="f5163-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="f5163-108">Avant de déplacer des utilisateurs, veillez à passer en revue les conditions préalables pour déplacer les [utilisateurs](move-users-between-on-premises-and-cloud.md#prerequisites) vers le cloud.</span><span class="sxs-lookup"><span data-stu-id="f5163-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="f5163-109">En préparation du retrait à venir de Skype Entreprise Online, Microsoft a simplifié la façon dont les organisations se déplacent vers Teams.</span><span class="sxs-lookup"><span data-stu-id="f5163-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="f5163-110">Lors du déplacement des utilisateurs de l’local vers le cloud, le mode TeamsOnly est désormais automatiquement affecté aux utilisateurs et leurs réunions depuis l’local sont automatiquement converties en réunions Teams, comme si le commutateur avait été spécifié, que le commutateur soit ou non réellement `-MoveToTeams` spécifié.</span><span class="sxs-lookup"><span data-stu-id="f5163-110">When moving users from on-premises to the cloud, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch was actually specified.</span></span>  <span data-ttu-id="f5163-111">Avant le retrait de Skype Entreprise Online, les organisations qui nécessitent le déplacement d’utilisateurs locaux vers Skype Entreprise Online peuvent y parvenir en deux étapes en mettant à jour le mode de l’utilisateur après son déplacement vers *TeamsOnly.*</span><span class="sxs-lookup"><span data-stu-id="f5163-111">Prior to retirement of Skype for Business Online, organizations that require moving users from on-premises to Skype for Business Online can achieve this in two steps by updating the user's mode *after the user is moved to TeamsOnly*.</span></span> <span data-ttu-id="f5163-112">Toutefois, dans un futur proche, il ne sera plus possible d’attribuer un mode autre que TeamsOnly aux utilisateurs qui sont dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="f5163-112">However in the near future, it will no longer be possible to assign a mode other than TeamsOnly to users homed in the cloud.</span></span>  
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="f5163-113">Déplacer des utilisateurs avec Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="f5163-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="f5163-114">Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype Entreprise Management Shell sur site.</span><span class="sxs-lookup"><span data-stu-id="f5163-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="f5163-115">Vous devez avoir des privilèges suffisants à la fois dans l’environnement local et dans l’organisation Microsoft 365 comme décrit dans Les informations d’identification [administratives requises](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="f5163-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="f5163-116">Vous pouvez utiliser un seul compte spécifiant des privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype Entreprise Server Management Shell sur site avec des informations d’identification sur site et utiliser le paramètre pour spécifier les informations d’identification d’un compte Microsoft 365 avec le rôle d’administration `-Credential` nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f5163-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="f5163-117">Pour déplacer un utilisateur en ligne à l’aide de Move-CsUser :</span><span class="sxs-lookup"><span data-stu-id="f5163-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="f5163-118">Spécifiez l’utilisateur à déplacer à l’aide du paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="f5163-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="f5163-119">Spécifiez le paramètre -Target avec la valeur « sipfed.online.lync. <span> com ».</span><span class="sxs-lookup"><span data-stu-id="f5163-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="f5163-120">Si vous n’avez pas un compte avec des autorisations suffisantes à la fois en local et dans Microsoft 365, utilisez le paramètre -credential pour fournir à un compte des autorisations suffisantes dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5163-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="f5163-121">Si le compte avec des autorisations dans Microsoft 365 ne se termine pas par « .onmicrosoft. <span> com », puis vous devez spécifier le paramètre -HostedMigrationOverrideUrl, avec la valeur correcte comme décrit dans les informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="f5163-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="f5163-122">La séquence de cmdlet suivante peut être utilisée pour déplacer un utilisateur vers Skype Entreprise Online et affecte le mode client par défaut à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5163-122">The following cmdlet sequence can be used to move a user to Skype for Business Online and assigns the tenant default mode to the user.</span></span> <span data-ttu-id="f5163-123">Il suppose que les informations d Microsoft 365 sont un compte distinct et fournies en tant qu’entrées pour Get-Credential invite.</span><span class="sxs-lookup"><span data-stu-id="f5163-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

<span data-ttu-id="f5163-124">Si le compte d’administrateur est activé pour l’authentification multifacteur, ne spécifiez pas le paramètre -Credential.</span><span class="sxs-lookup"><span data-stu-id="f5163-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="f5163-125">L’administrateur est invité à obtenir des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="f5163-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a><span data-ttu-id="f5163-126">Déplacer des utilisateurs Skype Entreprise Server panneau de Teams et du Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="f5163-126">Move users with Skype for Business Server Control Panel and Teams Admin Center</span></span>

1. <span data-ttu-id="f5163-127">Ouvrez l Skype Entreprise Server du Panneau de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f5163-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="f5163-128">Dans le navigation de gauche, sélectionnez **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="f5163-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="f5163-129">Utilisez **Find** pour localiser les utilisateurs que vous souhaitez déplacer vers Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="f5163-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="f5163-130">Sélectionnez le(s) utilisateur(s), puis, dans la liste dropdown **Action** au-dessus de la liste, sélectionnez Déplacer les utilisateurs sélectionnés vers **Skype Entreprise Online** ou Déplacer les utilisateurs sélectionnés vers **Teams**.</span><span class="sxs-lookup"><span data-stu-id="f5163-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online** or **Move selected users to Teams**.</span></span> <span data-ttu-id="f5163-131">Les deux options déplacent initialement l’utilisateur vers le mode TeamsOnly, mais après le déplacement, vous pouvez attribuer un autre mode.</span><span class="sxs-lookup"><span data-stu-id="f5163-131">Either option will initially move the user to TeamsOnly mode but after the move you can assign another mode.</span></span> 
5. <span data-ttu-id="f5163-132">Dans l'Assistant, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f5163-132">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="f5163-133">Si vous y êtes invité, connectez-vous Microsoft 365 un compte qui se termine par .onmicrosoft.com et dispose d’autorisations suffisantes.</span><span class="sxs-lookup"><span data-stu-id="f5163-133">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="f5163-134">Cliquez **sur** Suivant, puis **sur Suivant** une fois de plus pour déplacer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f5163-134">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="f5163-135">Notez que les messages d’état concernant la réussite ou l’échec sont fournis en haut de l’application principale du Panneau de contrôle, et non dans l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="f5163-135">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
9. <span data-ttu-id="f5163-136">Ouvrez le Teams admin center et sélectionnez « Utilisateurs » dans le navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="f5163-136">Open the Teams Admin Center and select "Users" in the left hand navigation.</span></span> 
10. <span data-ttu-id="f5163-137">Cliquez sur l’utilisateur souhaité dans l’listview.</span><span class="sxs-lookup"><span data-stu-id="f5163-137">Click on the desired user in the listview.</span></span> 
11. <span data-ttu-id="f5163-138">Cliquez sur **Modifier dans** la section qui indique Teams mise **à niveau.**</span><span class="sxs-lookup"><span data-stu-id="f5163-138">Click the **Edit** in the section that says **Teams upgrade**.</span></span>
12. <span data-ttu-id="f5163-139">Dans le volant droit, sélectionnez le mode de coexistence souhaité, puis cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="f5163-139">In the right-hand flyout, select the desired coexistence mode and click **Apply**.</span></span>
 

## <a name="see-also"></a><span data-ttu-id="f5163-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5163-140">See also</span></span>

[<span data-ttu-id="f5163-141">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="f5163-141">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
