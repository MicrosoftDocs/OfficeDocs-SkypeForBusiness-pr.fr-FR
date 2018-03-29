---
title: Déplacer les utilisateurs locaux à Skype pour professionnels en ligne
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Résumé : Informations sur le déplacement sur site aux utilisateurs de Skype pour les entreprises en ligne.'
ms.openlocfilehash: 9aa4c87d713af437f1fbb81cd23e354792559aa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a><span data-ttu-id="939ff-103">Déplacer les utilisateurs locaux à Skype pour professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="939ff-103">Move on-premises users to Skype for Business Online</span></span>
 
<span data-ttu-id="939ff-104">**Résumé :** Informations sur le déplacement des utilisateurs locaux à Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="939ff-104">**Summary:** Information about moving on-premises users to Skype for Business Online.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="939ff-105">Les appareils Lync Phone Edition DOIVENT être mis à jour vers les microprogrammes minimaux requis dans votre environnement local AVANT de passer à Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="939ff-105">Lync Phone Edition devices MUST be updated to minimum required firmware in your on premises environment PRIOR to moving to Skype for Business Online.</span></span> <span data-ttu-id="939ff-106">Si vous transférez les utilisateurs de votre déploiement local à la solution en ligne avant la mise à jour du microprogramme, les utilisateurs ne pourront pas se connecter en utilisant leur téléphone.</span><span class="sxs-lookup"><span data-stu-id="939ff-106">If you move your users from on-premises to online prior to updating the firmware, users will be unable to connect using their phones.</span></span> <span data-ttu-id="939ff-107">Pour résoudre ce problème, les utilisateurs doivent être transférés à nouveau vers l’environnement local pour que leur téléphone soit mis à jour avec le microprogramme minimal requis.</span><span class="sxs-lookup"><span data-stu-id="939ff-107">To correct this problem, users must be moved back to the on premises environment to have their phones updated to the minimum firmware.</span></span> <span data-ttu-id="939ff-108">N’ESSAYEZ PAS DE METTRE À JOUR LE MICROPROGRAMME MINIMAL REQUIS OU D’EFFECTUER UNE MISE À JOUR MATÉRIELLE DE VOTRE TÉLÉPHONE AVANT DE REPLACER L’UTILISATEUR DANS VOTRE ENVIRONNEMENT LOCAL.</span><span class="sxs-lookup"><span data-stu-id="939ff-108">DO NOT ATTEMPT TO UPDATE TO MINIMUM FIRMWARE OR HARD RESET THE PHONE PRIOR TO MOVING THE USER BACK TO YOUR ON PREMISES ENVIRONMENT.</span></span>
<span data-ttu-id="939ff-109">Si la réinitialisation matérielle est effectuée avant l’installation du microprogramme minimal requis sur l’appareil, celui-ci utilise par défaut l’authentification par code confidentiel, ce qui n’est pas pris en charge par Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="939ff-109">If a hard reset is performed while the device is not at minimum firmware it will default to using PIN Authentication, which is not supported in Skype for Business Online.</span></span> <span data-ttu-id="939ff-110">Pour plus d’informations, reportez-vous à la [Mise en route de téléphones pour Skype pour l’activité en ligne](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="939ff-110">For more information, please refer to [Getting Phones for Skype for Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="939ff-111">Il s’agit d’une étape facultative qui est uniquement nécessaire si vous déplacez les utilisateurs locaux à Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="939ff-111">This is an optional step that is required only if you are moving on-premises users to Skype for Business Online.</span></span> <span data-ttu-id="939ff-112">Avant de commencer à déplacer les utilisateurs vers Skype pour entreprise en ligne, vérifiez que le Skype pour connecteur de Business Online (module de Windows PowerShell) est déployée sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="939ff-112">Before you begin to move users to Skype for Business Online, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="939ff-113">Si elle n’est pas le cas, vous pouvez le télécharger à partir [du centre de téléchargement](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="939ff-113">If it isn't, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="939ff-114">Par ailleurs, pour préparer votre AD, vous devez configurer Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="939ff-114">Also, to prepare your AD, you'll need to configure Azure AD Connect.</span></span> <span data-ttu-id="939ff-115">La version d’AAD Connect que vous utilisez doit être de version 1.0.9125.0 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="939ff-115">The version of AAD Connect you use must be version 1.0.9125.0 or later.</span></span> <span data-ttu-id="939ff-116">Si vous utilisez des outils d'une version antérieure d’AAD Connect ou de DirSync, effectuez une mise à niveau vers la version prise en charge.</span><span class="sxs-lookup"><span data-stu-id="939ff-116">If you are using an earlier version of AAD Connect tools or DirSync, please upgrade to the supported version.</span></span> <span data-ttu-id="939ff-117">Vous pouvez mettre à niveau votre installation actuelle et conserver les règles personnalisées définies dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="939ff-117">You can upgrade your current installation and maintain any custom rules you have defined in your environment.</span></span>
  
<span data-ttu-id="939ff-118">Vous déplacez des utilisateurs à l’aide soit Skype pour panneau de commande du serveur Business ou Skype pour Business Server Management Shell dans votre déploiement sur site, mais vous devez disposer des informations d’identification de l’administrateur pour votre déploiement d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="939ff-118">You move users using either Skype for Business Server Control Panel or Skype for Business Server Management Shell in your on-premises deployment, but you must have administrator credentials for your Office 365 deployment.</span></span>
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a><span data-ttu-id="939ff-119">Déplacement d’utilisateurs à l’aide de Skype pour panneau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="939ff-119">Moving users by using Skype for Business Control Panel</span></span>

### <a name="to-move-a-user-to-skype-for-business-online"></a><span data-ttu-id="939ff-120">Pour atteindre un utilisateur Skype pour professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="939ff-120">To move a user to Skype for Business Online</span></span>

1. <span data-ttu-id="939ff-121">À partir d’un compte d’utilisateur qui est affecté à la rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne qui a Skype pour Business Server ou, au moins Skype pour les outils d’administration du serveur Business installé.</span><span class="sxs-lookup"><span data-stu-id="939ff-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment that has Skype for Business Server, or at least Skype for Business Server Admin tools installed.</span></span>
    
2. <span data-ttu-id="939ff-122">À partir du menu Démarrer ou d’un raccourci sur le bureau, ouvrez le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="939ff-122">From the Start menu or desktop shortcut, open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="939ff-123">Vous pouvez également accéder le Skype pour le panneau de configuration de Business Server à l’aide de l’URL d’administration si vous avez configuré un.</span><span class="sxs-lookup"><span data-stu-id="939ff-123">You can also access the Skype for Business Server Control Panel by using the Admin URL if you have configured one.</span></span>
    
3. <span data-ttu-id="939ff-124">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="939ff-124">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="939ff-125">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="939ff-125">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="939ff-126">Cliquez sur l’utilisateur, puis, dans le menu **Action**, cliquez sur **Déplacer les utilisateurs sélectionnés vers Skype Entreprise Online**.</span><span class="sxs-lookup"><span data-stu-id="939ff-126">Click the user, then in the **Action** menu, click **Move selected users to Skype for Business Online**.</span></span>
    
6. <span data-ttu-id="939ff-127">Dans la page **Déplacer des utilisateurs vers Skype Entreprise Online**, lisez les informations, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="939ff-127">On the **Move users to Skype For Business Online** page, read the information and then click **Next**.</span></span>
    
7. <span data-ttu-id="939ff-128">Sur la page suivante, si vous n’êtes pas encore connecté à Office 365, cliquez sur **se connecter à Office 365**, vos informations d’identification et cliquez sur **OK** et sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="939ff-128">On the next page, if you are not yet signed in to Office 365, click **Sign in to Office 365**, provide your credentials, and click **OK** and **Next**.</span></span>
    
8. <span data-ttu-id="939ff-129">Confirmez que le nombre d’utilisateurs à déplacer est correct, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="939ff-129">Confirm that the number of users to be moved is correct, and click **Next**.</span></span>
    
9. <span data-ttu-id="939ff-130">Dans la page suivante, vérifiez les résultats et cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="939ff-130">On the next page, review the results and click **Close**.</span></span>
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="939ff-131">Déplacement d’utilisateurs à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="939ff-131">Moving users by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="939ff-132">Pour déplacer un utilisateur local vers votre Skype pour clients d’entreprise en ligne, exécuter les applets de commande suivantes dans le Skype pour Business Server Management Shell, en utilisant les informations d’identification d’administrateur pour vos clients de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="939ff-132">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="939ff-133">Remplacez « nomutilisateur@contoso.com » par les informations de l’utilisateur à déplacer.</span><span class="sxs-lookup"><span data-stu-id="939ff-133">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

<span data-ttu-id="939ff-134">Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être une URL vers le pool dans lequel le service hébergé de Migration est en cours d’exécution, dans le format suivant : _Https://\<nom de domaine complet Pool\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="939ff-134">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
  
<span data-ttu-id="939ff-135">Vous pouvez déterminer l’URL pour le Service hébergé de la Migration en consultant l’URL pour le Skype pour le centre d’administration en ligne de Business pour votre compte de clients Office 365.</span><span class="sxs-lookup"><span data-stu-id="939ff-135">You can determine the URL to the Hosted Migration Service by viewing the URL for the Skype for Business Online Admin center for your Office 365 tenant account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="939ff-136">L’URL dépend des minuscules/majuscules.</span><span class="sxs-lookup"><span data-stu-id="939ff-136">The URL is case sensitive.</span></span> 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="939ff-137">Pour déterminer l’URL du service de migration hébergée de votre client Office 365</span><span class="sxs-lookup"><span data-stu-id="939ff-137">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="939ff-138">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="939ff-138">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="939ff-139">Ouvrez le **Centre d’administration Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="939ff-139">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="939ff-140">Une fois le **Centre d’administration Skype Entreprise** affiché, sélectionnez l’URL et copiez-la dans la barre d’adresse jusqu’à **lync.com**. L’URL doit se présenter comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="939ff-140">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="939ff-141">Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="939ff-141">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="939ff-142">Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationService.svc**.</span><span class="sxs-lookup"><span data-stu-id="939ff-142">Append the following string to the URL: **/HostedMigration/hostedmigrationService.svc**.</span></span>
    
    <span data-ttu-id="939ff-143">L’URL résultante, qui est la valeur de la **HostedMigrationOverrideUrl**, doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="939ff-143">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

