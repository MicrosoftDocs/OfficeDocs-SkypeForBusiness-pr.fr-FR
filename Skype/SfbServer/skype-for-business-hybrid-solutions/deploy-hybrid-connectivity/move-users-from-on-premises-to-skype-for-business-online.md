---
title: Déplacer les utilisateurs vers Skype Entreprise Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 'Résumé : Apprenez à migrer les paramètres utilisateur et de déplacer des utilisateurs vers Skype pour l’activité en ligne.'
ms.openlocfilehash: dada94d1bc198a86a06c468dc959fa0684e706d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="aeb8d-103">Déplacer les utilisateurs vers Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="aeb8d-103">Move users from on premises to Skype for Business Online</span></span>
 
<span data-ttu-id="aeb8d-104">**Résumé :** Apprenez à migrer les paramètres utilisateur et de déplacer des utilisateurs vers Skype pour l’activité en ligne.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>
  
<span data-ttu-id="aeb8d-p101">Avant de déplacer l’utilisateur vers Office 365, vous devez d’abord confirmer que les comptes utilisateur sont synchronisés avec le cloud et vous devez lui attribuer une licence. À cet effet, vous devez utiliser le Centre d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-p101">Before actually moving the user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license. To do this, you use the Office 365 Admin Center.</span></span>
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="aeb8d-107">Pour confirmer qu’un compte d’utilisateur local a été synchronisé avec Office 365</span><span class="sxs-lookup"><span data-stu-id="aeb8d-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="aeb8d-108">Un compte d’administrateur de clients, ouvrez le [Centre d’administration Office 365](https://portal.office.com/) pour vos clients.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-108">Using an tenant admin account, open the [Office 365 admin center](https://portal.office.com/) for your tenant.</span></span>
    
2. <span data-ttu-id="aeb8d-109">Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sur **Utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-109">On the left navigation pane, click **Users** and then **Active Users**.</span></span>
    
3. <span data-ttu-id="aeb8d-110">Cliquez sur **Rechercher un utilisateur** et tapez le nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-110">Click **Search for a User**, and type the name of the user.</span></span>
    
4. <span data-ttu-id="aeb8d-111">Vérifiez que l’utilisateur s’affiche et que son statut est **Synchronisé avec Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-111">Confirm that you see the user, and that their status is **Synched with Active Directory**.</span></span>
    
    <span data-ttu-id="aeb8d-112">Si l’utilisateur n’est pas encore synchronisé, la synchronisation automatique doit avoir lieu dans les trois heures.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-112">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="aeb8d-113">Vous pouvez également forcer une synchronisation plus tôt.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-113">You can also force a synchronization sooner.</span></span> <span data-ttu-id="aeb8d-114">Pour plus d’informations, consultez [Force la synchronisation d’annuaire](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span><span class="sxs-lookup"><span data-stu-id="aeb8d-114">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>
    
<span data-ttu-id="aeb8d-115">Pour attribuer la licence dans Office 365, voir [attribution de licences pour Office 365 pour entreprises](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="aeb8d-115">To assign the license in Office 365, see [Assign licenses for Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="aeb8d-116">Migration des paramètres utilisateur à Skype pour professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="aeb8d-116">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="aeb8d-117">Avant de commencer la migration des utilisateurs vers Skype pour professionnels en ligne, vous devez sauvegarder les données de l’utilisateur associées à déplacer.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-117">Before you start migrating users to Skype for Business Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="aeb8d-118">Les données utilisateur ne sont pas toutes déplacées avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-118">Not all user data is moved with the user account.</span></span> <span data-ttu-id="aeb8d-119">Pour plus d’informations, consultez [les exigences de restauration et de sauvegarde : données](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span><span class="sxs-lookup"><span data-stu-id="aeb8d-119">For information, see [Backup and Restoration Requirements: Data](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>
  
<span data-ttu-id="aeb8d-p104">Les paramètres utilisateur sont déplacés en même temps que le compte d’utilisateur. Certains paramètres locaux ne sont pas déplacés avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-p104">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>
  
## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="aeb8d-122">Déplacer les utilisateurs pilotes à Skype pour professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="aeb8d-122">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="aeb8d-123">Avant de commencer à déplacer les utilisateurs vers Skype pour professionnels en ligne, vous souhaiterez déplacer quelques utilisateurs pilotes afin de confirmer que votre environnement est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-123">Before you begin to move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="aeb8d-124">Vous pouvez alors vérifier que les fonctionnalités et les services fonctionnent comme prévu avant d’essayer de déplacer d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-124">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>
  
<span data-ttu-id="aeb8d-125">Pour déplacer un utilisateur local vers votre Skype pour clients d’entreprise en ligne, exécuter les applets de commande suivantes dans le Skype pour Business Server Management Shell, en utilisant les informations d’identification d’administrateur pour vos clients de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-125">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="aeb8d-126">Remplacez « nomutilisateur@contoso.com » par les informations de l’utilisateur à déplacer.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-126">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="aeb8d-127">Déplacement des utilisateurs vers Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="aeb8d-127">Move users to Skype for Business Online</span></span>

<span data-ttu-id="aeb8d-128">Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de commande [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) -paramètre de filtre pour sélectionner les utilisateurs à une propriété spécifique affectée aux comptes d’utilisateurs, par exemple RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-128">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="aeb8d-129">Vous pouvez ensuite canaliser les utilisateurs retournées à l’applet de commande [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , comme illustré dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-129">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example.</span></span>
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

<span data-ttu-id="aeb8d-130">Vous pouvez également utiliser le paramètre - unité d’organisation pour récupérer tous les utilisateurs dans l’unité d’organisation spécifiée, comme illustré dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-130">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>
  
```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds 
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="aeb8d-131">Vérification des paramètres utilisateur et des fonctionnalités en ligne</span><span class="sxs-lookup"><span data-stu-id="aeb8d-131">Verify online user settings and features</span></span>

<span data-ttu-id="aeb8d-132">Vous pouvez vérifier que le déplacement d’un utilisateur a réussi des deux manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="aeb8d-132">You can verify that the user was moved successfully in the following ways:</span></span>
  
- <span data-ttu-id="aeb8d-p108">Affichez le statut de l’utilisateur dans le Panneau de configuration de Skype Entreprise Online. L’indicateur visuel des utilisateurs locaux et des utilisateurs en ligne est différent.</span><span class="sxs-lookup"><span data-stu-id="aeb8d-p108">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>
    
- <span data-ttu-id="aeb8d-135">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="aeb8d-135">Run the following cmdlet:</span></span>
    
  ```
  Get-CsUser -Identity
  ```


