---
title: Déplacer des utilisateurs de l’organisation locale vers Skype entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: Découvrez comment déplacer des utilisateurs vers Skype entreprise online.
ms.openlocfilehash: ddf25614afae48ef647dc325e53ccbab8ac2e5d0
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963022"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="a7e46-103">Déplacer des utilisateurs de l’organisation locale vers Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a7e46-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="a7e46-104">Une fois que vous avez déplacé un utilisateur de l’environnement local vers Skype entreprise Online, l’utilisateur interagit avec Skype entreprise Online pour ses fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="a7e46-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="a7e46-105">Tous les contacts qui existaient sur site seront disponibles dans Skype entreprise Online, et les réunions existantes organisées par l’utilisateur pour le futur seront mises à jour vers de sorte que les liens pointent vers Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="a7e46-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="a7e46-106">Si l’utilisateur est activé pour l’audioconférence, les réunions incluent également des coordonnées d’accès.</span><span class="sxs-lookup"><span data-stu-id="a7e46-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="a7e46-107">Pour déplacer des utilisateurs d’un environnement local vers Skype entreprise Online, utilisez l’applet de commande Move-CsUser ou le panneau de configuration de Skype entreprise Server, qui sont tous deux des outils locaux.</span><span class="sxs-lookup"><span data-stu-id="a7e46-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="a7e46-108">Avant de déplacer des utilisateurs, veillez à passer en revue les [éléments prérequis](move-users-between-on-premises-and-cloud.md#prerequisites) pour déplacer les utilisateurs vers le Cloud.</span><span class="sxs-lookup"><span data-stu-id="a7e46-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="a7e46-109">Déplacer des utilisateurs à l’aide de Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="a7e46-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="a7e46-110">Move-CsUser est disponible à partir d’une fenêtre PowerShell Skype entreprise Management Shell locale.</span><span class="sxs-lookup"><span data-stu-id="a7e46-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="a7e46-111">Vous devez disposer de privilèges suffisants dans l’environnement local et dans le client Office 365, comme décrit dans la rubrique [Required Credentials Requirements](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="a7e46-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="a7e46-112">Vous pouvez utiliser un compte unique qui dispose de privilèges dans les deux environnements, ou vous pouvez démarrer une fenêtre Skype entreprise Server Management Shell locale avec des informations d’identification locales et utiliser le `-Credential` paramètre pour spécifier des informations d’identification pour un compte Office 365 avec le rôle d’administration Office 365 nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a7e46-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="a7e46-113">Pour déplacer un utilisateur vers en ligne à l’aide de Move-CsUser :</span><span class="sxs-lookup"><span data-stu-id="a7e46-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="a7e46-114">Spécifier l’utilisateur à déplacer à l’aide du paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="a7e46-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="a7e46-115">Spécifiez le paramètre-Target avec la valeur «sipfed. online. Lync. <span>com».</span><span class="sxs-lookup"><span data-stu-id="a7e46-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="a7e46-116">Si vous ne disposez pas d’un compte avec des autorisations suffisantes dans local et Office 365, utilisez le paramètre-Credential pour fournir un compte avec des autorisations suffisantes dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7e46-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="a7e46-117">Si le compte avec des autorisations dans Office 365 ne se termine pas par «sur. Microsoft. <span>com», vous devez spécifier le paramètre-HostedMigrationOverrideUrl, avec la valeur correcte, comme décrit dans la rubrique [Required Credentials Requirements](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="a7e46-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

 > [!NOTE]
 > <span data-ttu-id="a7e46-118">Vous devez déterminer la valeur HostedMigrationOverrideUrl correcte pour votre client.</span><span class="sxs-lookup"><span data-stu-id="a7e46-118">You must determine the correct HostedMigrationOverrideUrl value for your tenant.</span></span> <span data-ttu-id="a7e46-119">vous pouvez facilement effectuer cette opération en accédant au centre d’administration Skype entreprise hérité.</span><span class="sxs-lookup"><span data-stu-id="a7e46-119">this can be easily done by navigating to the Legacy Skype for Business admin center.</span></span> <span data-ttu-id="a7e46-120">déterminer le préfixe-XXXXXXX.online.lync.com et ajouter/HostedMigration/hostedmigrationservice.svc.</span><span class="sxs-lookup"><span data-stu-id="a7e46-120">determine the prefix - XXXXXXX.online.lync.com and append /HostedMigration/hostedmigrationservice.svc.</span></span> <span data-ttu-id="a7e46-121">par exemple : https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc une fois que vous avez identifié la valeur, utilisez-la pour la variable $URL comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a7e46-121">for example: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc Once you identified the value, use it for the $url variable as shown below.</span></span>

<span data-ttu-id="a7e46-122">La séquence d’applets de commande suivante peut être utilisée pour déplacer un utilisateur vers Skype entreprise Online et suppose que les informations d’identification Office 365 sont un compte distinct et fourni comme entrée pour l’invite Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="a7e46-122">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="a7e46-123">Si le compte administrateur est activé pour l’authentification multifacteur (MFA), ne spécifiez pas le paramètre-Credential.</span><span class="sxs-lookup"><span data-stu-id="a7e46-123">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="a7e46-124">L’administrateur sera invité à entrer les informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="a7e46-124">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="a7e46-125">Déplacer des utilisateurs avec le panneau de configuration de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a7e46-125">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="a7e46-126">Ouvrez l’application du panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a7e46-126">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="a7e46-127">Dans le volet de navigation de gauche, choisissez **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a7e46-127">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="a7e46-128">Utilisez **Rechercher** pour localiser le ou les utilisateurs que vous souhaitez déplacer vers Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="a7e46-128">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="a7e46-129">Sélectionnez le ou les utilisateurs, puis, dans la liste déroulante **action** située au-dessus de la liste, sélectionnez **déplacer les utilisateurs sélectionnés vers Skype entreprise Online**.</span><span class="sxs-lookup"><span data-stu-id="a7e46-129">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="a7e46-130">Dans l'Assistant, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a7e46-130">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="a7e46-131">Si vous y êtes invité, connectez-vous à Office 365, avec un compte qui se termine par. onmicrosoft.com et qui dispose des autorisations suffisantes.</span><span class="sxs-lookup"><span data-stu-id="a7e46-131">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="a7e46-132">Cliquez sur **suivant**, puis une **nouvelle** fois pour déplacer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a7e46-132">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="a7e46-133">Notez que les messages d’État concernant la réussite ou l’échec sont fournis en haut de l’application principale du panneau de configuration, et non dans l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="a7e46-133">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7e46-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7e46-134">See also</span></span>

[<span data-ttu-id="a7e46-135">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="a7e46-135">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
