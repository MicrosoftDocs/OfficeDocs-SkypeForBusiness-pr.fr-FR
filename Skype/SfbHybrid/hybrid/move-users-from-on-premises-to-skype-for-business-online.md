---
title: Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online
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
ms.openlocfilehash: 4d74cdebc5477d0204f69b64c2c05a4435212b3f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110620"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="1b476-103">Déplacer les utilisateurs de l’environnement local vers Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="1b476-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="1b476-104">Après avoir fait passer un utilisateur de l’local à Skype Entreprise Online, l’utilisateur interagit avec Skype Entreprise Online pour sa fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1b476-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="1b476-105">Tous les contacts qui existaient en local seront disponibles dans Skype Entreprise Online, et toutes les réunions existantes organisées par l’utilisateur à l’avenir sont mises à jour de sorte que les liens pointent vers Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="1b476-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="1b476-106">Si l’utilisateur est activé pour l’audioconférence, les réunions incluent également des coordonnées d’accès.</span><span class="sxs-lookup"><span data-stu-id="1b476-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="1b476-107">Pour déplacer des utilisateurs d’un environnement local vers Skype Entreprise Online, utilisez la cmdlet Move-CsUser ou le Panneau de contrôle Skype Entreprise Server, qui sont tous deux des outils locaux.</span><span class="sxs-lookup"><span data-stu-id="1b476-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="1b476-108">Avant de déplacer des utilisateurs, veillez à passer en revue les conditions préalables pour déplacer les [utilisateurs](move-users-between-on-premises-and-cloud.md#prerequisites) vers le cloud.</span><span class="sxs-lookup"><span data-stu-id="1b476-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="1b476-109">Déplacer des utilisateurs avec Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="1b476-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="1b476-110">Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype Entreprise Management Shell sur site.</span><span class="sxs-lookup"><span data-stu-id="1b476-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="1b476-111">Vous devez avoir des privilèges suffisants à la fois dans l’environnement local et dans l’organisation Microsoft 365/Office 365, comme décrit dans les informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="1b476-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="1b476-112">Vous pouvez utiliser un seul compte spécifiant des privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype Entreprise Server Management Shell sur site avec des informations d’identification sur site et utiliser le paramètre pour spécifier les informations d’identification d’un compte `-Credential` Microsoft 365 ou Office 365 avec le rôle d’administration nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1b476-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="1b476-113">Pour déplacer un utilisateur en ligne à l’aide de Move-CsUser :</span><span class="sxs-lookup"><span data-stu-id="1b476-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="1b476-114">Spécifiez l’utilisateur à déplacer à l’aide du paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="1b476-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="1b476-115">Spécifiez le paramètre -Target avec la valeur « sipfed.online.lync. <span> com ».</span><span class="sxs-lookup"><span data-stu-id="1b476-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="1b476-116">Si vous n’avez pas un compte avec des autorisations suffisantes à la fois en local et dans Office 365, utilisez le paramètre -credential pour fournir à un compte des autorisations suffisantes dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b476-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="1b476-117">Si le compte avec des autorisations dans Office 365 ne se termine pas par « .onmicrosoft. <span> com », puis vous devez spécifier le paramètre -HostedMigrationOverrideUrl, avec la valeur correcte comme décrit dans les informations d’identification [administratives requises.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="1b476-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="1b476-118">La séquence de cmdlet suivante peut être utilisée pour déplacer un utilisateur vers Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="1b476-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="1b476-119">Il suppose que les informations d’identification Microsoft 365 ou Office 365 sont un compte distinct et fournies en tant qu’entrées pour lGet-Credential indexe.</span><span class="sxs-lookup"><span data-stu-id="1b476-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="1b476-120">Si le compte d’administrateur est activé pour l’authentification multifacteur, ne spécifiez pas le paramètre -Credential.</span><span class="sxs-lookup"><span data-stu-id="1b476-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="1b476-121">L’administrateur est invité à obtenir des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="1b476-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="1b476-122">Déplacer des utilisateurs avec le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b476-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="1b476-123">Ouvrez l’application Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b476-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="1b476-124">Dans le navigation de gauche, sélectionnez **Utilisateurs.**</span><span class="sxs-lookup"><span data-stu-id="1b476-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="1b476-125">Utilisez **Find** pour localiser les utilisateurs que vous souhaitez déplacer vers Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="1b476-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="1b476-126">Sélectionnez le(s) utilisateur(s), puis, dans la liste dropdown **Action** au-dessus de la liste, sélectionnez Déplacer les utilisateurs sélectionnés **vers Skype Entreprise Online.**</span><span class="sxs-lookup"><span data-stu-id="1b476-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="1b476-127">Dans l'Assistant, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1b476-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="1b476-128">Si vous y êtes invité, connectez-vous à Microsoft 365 ou Office 365 avec un compte qui se termine par .onmicrosoft.com et dispose d’autorisations suffisantes.</span><span class="sxs-lookup"><span data-stu-id="1b476-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="1b476-129">Cliquez **sur** Suivant, puis **sur Suivant** une fois de plus pour déplacer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1b476-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="1b476-130">Notez que les messages d’état concernant la réussite ou l’échec sont fournis en haut de l’application principale du Panneau de contrôle, et non dans l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="1b476-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b476-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b476-131">See also</span></span>

[<span data-ttu-id="1b476-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="1b476-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)