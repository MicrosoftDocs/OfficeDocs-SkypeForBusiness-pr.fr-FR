---
title: Déplacer les utilisateurs vers Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Découvrez comment déplacer des utilisateurs vers Skype pour Business Online.
ms.openlocfilehash: 083f2f52fd07439d85d017db9c4b035b8ea326b6
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27243996"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="6753e-103">Déplacer les utilisateurs vers Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="6753e-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="6753e-104">Une fois que vous déplacez un utilisateur sur site à Skype pour Business Online, l’utilisateur interagit avec Skype pour Business Online pour ses fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="6753e-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="6753e-105">Les contacts qui existaient sur site sera disponibles dans Skype pour Business Online, et toutes les réunions organisée par l’utilisateur pour l’avenir existantes sont mises à jour afin que les liens pointent sur Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="6753e-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="6753e-106">Si l’utilisateur est activé pour une audioconférence, les réunions inclut également les coordonnées du rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="6753e-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="6753e-107">Pour déplacer les utilisateurs d’un environnement sur site vers Skype pour Business Online, utilisez l’applet de commande Move-CsUser ou le Skype pour Business Server Control Panel, qui sont tous deux outils locale.</span><span class="sxs-lookup"><span data-stu-id="6753e-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="6753e-108">Avant de déplacer des utilisateurs, veillez à consulter les [conditions requises](move-users-between-on-premises-and-cloud.md#prerequisites) pour déplacer des utilisateurs vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="6753e-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="6753e-109">Déplacer les utilisateurs avec Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="6753e-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="6753e-110">Move-CsUser est disponible à partir d’un Skype locale de fenêtre Business Management Shell PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6753e-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="6753e-111">Vous devez disposer de privilèges suffisants dans les deux l’environnement local ainsi que dans le client Office 365 comme décrit dans [requis des informations d’identification administratives](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="6753e-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="6753e-112">Vous pouvez utiliser un seul compte disposant de privilèges dans les deux environnements, ou vous pouvez démarrer une Skype dans les locaux de fenêtre Business Server Management Shell avec des informations d’identification dans les locaux et utiliser le `-Credential` paramètre pour spécifier les informations d’identification pour un Office 365 compte doté du rôle d’administration Office 365 nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6753e-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="6753e-113">Pour déplacer un utilisateur en ligne à l’aide de Move-CsUser :</span><span class="sxs-lookup"><span data-stu-id="6753e-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="6753e-114">Spécifiez l’utilisateur à déplacer à l’aide du paramètre Identity.</span><span class="sxs-lookup"><span data-stu-id="6753e-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="6753e-115">Spécifiez-paramètre cible avec la valeur « sipfed.online.lync. <span>com ».</span><span class="sxs-lookup"><span data-stu-id="6753e-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="6753e-116">Si vous ne disposez pas d’un compte disposant des autorisations suffisantes dans les locaux et Office 365, utilisez le paramètre - credential pour fournir un compte disposant des autorisations suffisantes dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="6753e-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="6753e-117">Si le compte possédant des autorisations dans Office 365 ne se termine pas par « on.microsoft. <span>com », vous devez spécifier le paramètre - HostedMigrationOverrideUrl, avec la valeur correcte, comme décrit dans [requis des informations d’identification administratives](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span><span class="sxs-lookup"><span data-stu-id="6753e-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="6753e-118">La séquence d’applet de commande suivante permet de déplacer un utilisateur à Skype pour Business Online et suppose que les informations d’identification Office 365 est un compte distinct et fourni comme entrée pour l’invite de Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="6753e-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```
## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="6753e-119">Déplacer les utilisateurs avec Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="6753e-119">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="6753e-120">Ouvrez le Skype pour le contrôle serveur Business application du Panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="6753e-120">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="6753e-121">Dans la navigation de gauche, choisissez **utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6753e-121">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="6753e-122">Utiliser la **recherche** pour localiser les utilisateurs que vous souhaitez déplacer vers Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="6753e-122">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="6753e-123">Sélectionnez l’ou les utilisateurs, puis, dans la liste déroulante **Action** au-dessus de la liste, cliquez sur **déplacer les utilisateurs sélectionnés à Skype pour Business Online**.</span><span class="sxs-lookup"><span data-stu-id="6753e-123">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="6753e-124">Dans l’Assistant, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6753e-124">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="6753e-125">Si vous y êtes invité, connectez-vous à Office 365, avec un compte qui se termine par. onmicrosoft.com et dispose des autorisations suffisantes.</span><span class="sxs-lookup"><span data-stu-id="6753e-125">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="6753e-126">Cliquez sur **suivant**, puis **suivant** une fois plus de déplacer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6753e-126">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="6753e-127">Notez que les messages d’état en ce qui concerne la réussite ou l’échec sont fournis dans la partie supérieure de l’application le panneau de configuration principale, pas dans l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="6753e-127">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="6753e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6753e-128">See also</span></span>

[<span data-ttu-id="6753e-129">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="6753e-129">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)