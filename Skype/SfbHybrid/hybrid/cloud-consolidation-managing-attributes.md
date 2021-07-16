---
title: Décider comment gérer les attributs après la désaffectation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cet article explique comment gérer les attributs après la désaffectation de votre environnement local.
ms.openlocfilehash: 1c862e8c0055fc2eb40efcc7d26bb9a1166ae550
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458984"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a><span data-ttu-id="8f37d-103">Décider comment gérer les attributs après la désaffectation</span><span class="sxs-lookup"><span data-stu-id="8f37d-103">Decide how to manage attributes after decommissioning</span></span>

<span data-ttu-id="8f37d-104">Par défaut, tous les utilisateurs qui ont été précédemment activés pour Skype Entreprise Server puis déplacés vers le cloud ont toujours des attributs msRTCSIP configurés dans votre active Directory local.</span><span class="sxs-lookup"><span data-stu-id="8f37d-104">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> 

<span data-ttu-id="8f37d-105">Ces attributs, en particulier l’adresse sip (msRTCSIP-PrimaryUserAddress) et potentiellement le numéro de téléphone (msRTCSIP-Line), continuent de se synchroniser avec Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8f37d-105">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="8f37d-106">Si des modifications sont requises pour l’un des attributs msRTCSIP, ces modifications doivent être apportées dans l’annuaire Active Directory local, puis synchronisées avec Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8f37d-106">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="8f37d-107">Toutefois, une fois le déploiement Skype Entreprise Server supprimé, les outils Skype Entreprise Server ne seront pas disponibles pour gérer ces attributs.</span><span class="sxs-lookup"><span data-stu-id="8f37d-107">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="8f37d-108">Deux options sont disponibles pour gérer cette situation :</span><span class="sxs-lookup"><span data-stu-id="8f37d-108">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="8f37d-109">Laissez les utilisateurs qui ont été activés pour Skype Entreprise comptes serveur tels qu’ils sont et gérez les attributs msRTCSIP à l’aide des outils Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8f37d-109">Leave users that were enabled for Skype for Business server accounts as is, and manage the msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="8f37d-110">Cela garantit l’absence de perte de service pour les utilisateurs migrés et vous permet de supprimer facilement le déploiement Skype Entreprise Server en éliminant (par exemple, la suppression) des serveurs, sans désaffectation complète.</span><span class="sxs-lookup"><span data-stu-id="8f37d-110">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="8f37d-111">Toutefois, les utilisateurs nouvellement titulaires d’une licence n’auront pas ces attributs dans votre annuaire Active Directory local et devront être gérés en ligne.</span><span class="sxs-lookup"><span data-stu-id="8f37d-111">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="8f37d-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span><span class="sxs-lookup"><span data-stu-id="8f37d-112">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="8f37d-113">Cette méthode permet une approche de gestion cohérente pour les utilisateurs existants et nouveaux, mais elle peut entraîner une perte temporaire de service pendant le processus de désaffectation sur site.</span><span class="sxs-lookup"><span data-stu-id="8f37d-113">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="8f37d-114">Méthode 1 : gérer les adresses SIP et les numéros de téléphone des utilisateurs dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="8f37d-114">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="8f37d-115">Les administrateurs peuvent gérer les utilisateurs qui ont été précédemment déplacés d’une Skype Entreprise Server sur site vers le cloud, même après la désaffectation du déploiement local.</span><span class="sxs-lookup"><span data-stu-id="8f37d-115">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> 

<span data-ttu-id="8f37d-116">Si vous souhaitez apporter des modifications à l’adresse SIP d’un utilisateur ou au numéro de téléphone d’un utilisateur (et que l’adresse sip ou le numéro de téléphone a déjà une valeur dans l’annuaire Active Directory local), vous devez le faire dans l’annuaire Active Directory local et laisser les valeurs s’écouler jusqu’à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8f37d-116">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="8f37d-117">Cela ne nécessite PAS de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8f37d-117">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="8f37d-118">Au lieu de cela, vous pouvez modifier ces attributs directement dans Active Directory local, à l’aide du logiciel en ligne MMC Utilisateurs et ordinateurs Active Directory (comme illustré ci-dessous) ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f37d-118">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="8f37d-119">Si vous utilisez le logiciel en snap-in MMC, ouvrez la page des propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs et recherchez les attributs appropriés à modifier :</span><span class="sxs-lookup"><span data-stu-id="8f37d-119">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="8f37d-120">Pour modifier l’adresse SIP d’un utilisateur, modifiez le `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="8f37d-120">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f37d-121">Si `ProxyAddresses` l’attribut contient une adresse SIP, mettez également à jour cette valeur en tant que meilleure pratique.</span><span class="sxs-lookup"><span data-stu-id="8f37d-121">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="8f37d-122">Bien que l’adresse sip soit ignorée par O365 si elle est remplie, elle peut être utilisée par d’autres `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` composants locaux.</span><span class="sxs-lookup"><span data-stu-id="8f37d-122">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="8f37d-123">Pour modifier le numéro de téléphone d’un utilisateur, modifiez `msRTCSIP-Line` *s’il a déjà une valeur.*</span><span class="sxs-lookup"><span data-stu-id="8f37d-123">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Outil utilisateurs et ordinateurs Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="8f37d-125">Si l’utilisateur n’avait à l’origine pas de valeur pour l’environnement local avant le déplacement, vous pouvez modifier le numéro de téléphone à l’aide du paramètre - dans `msRTCSIP-Line` l’cmdlet `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) du module Skype Entreprise Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f37d-125">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="8f37d-126">Ces étapes ne sont pas nécessaires pour les nouveaux utilisateurs créés après la désactivation de l’hybride, et ces utilisateurs peuvent être gérés directement dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="8f37d-126">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="8f37d-127">Si vous êtes à l’aise avec la combinaison de ces méthodes et si vous souhaitez laisser les attributs msRTCSIP en place dans votre environnement Active Directory local, vous pouvez simplement ré-imager les serveurs Skype Entreprise locaux.</span><span class="sxs-lookup"><span data-stu-id="8f37d-127">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="8f37d-128">Toutefois, si vous préférez effacer tous les attributs msRTCSIP et faire une désinstallation traditionnelle de Skype Entreprise Server, utilisez la méthode 2.</span><span class="sxs-lookup"><span data-stu-id="8f37d-128">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="8f37d-129">Méthode 2 : effacer Skype Entreprise pour tous les utilisateurs locaux dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="8f37d-129">Method 2 - Clear Skype for Business attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="8f37d-130">Cette option nécessite des efforts supplémentaires et une planification appropriée, car les utilisateurs qui ont été précédemment déplacés d’un Skype Entreprise Server local vers le cloud doivent être réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="8f37d-130">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="8f37d-131">Ces utilisateurs peuvent être classés dans deux catégories différentes : les utilisateurs sans Système téléphonique et les utilisateurs Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="8f37d-131">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="8f37d-132">Les utilisateurs Système téléphonique seront temporairement perdus du service téléphonique dans le cadre de la transition du numéro de téléphone de la gestion dans Active Directory local vers le cloud.</span><span class="sxs-lookup"><span data-stu-id="8f37d-132">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="8f37d-133">**Il est recommandé d’effectuer un projet pilote impliquant un petit nombre d’utilisateurs avec Système téléphonique avant de démarrer des opérations utilisateur en bloc.**</span><span class="sxs-lookup"><span data-stu-id="8f37d-133">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="8f37d-134">Pour les déploiements de grande taille, les utilisateurs peuvent être traitées par groupes plus petits dans différentes fenêtres de temps.</span><span class="sxs-lookup"><span data-stu-id="8f37d-134">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="8f37d-135">Ce processus est plus simple pour les utilisateurs qui ont une adresse sip correspondante et UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="8f37d-135">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="8f37d-136">Pour les organisations dont les utilisateurs ont des valeurs non correspondantes dans ces deux attributs, une attention supplémentaire doit être prise comme indiqué ci-dessous pour une transition fluide.</span><span class="sxs-lookup"><span data-stu-id="8f37d-136">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="8f37d-137">Si vous avez configuré des points de terminaison d’application hybride sur site pour les attendants automatiques ou les files d’attente d’appels, veillez à déplacer ces points de terminaison vers Microsoft 365 avant de désaffecter Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8f37d-137">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="8f37d-138">Confirmez que l’Skype Entreprise cmdlet PowerShell suivante renvoie un résultat vide.</span><span class="sxs-lookup"><span data-stu-id="8f37d-138">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="8f37d-139">Un résultat vide signifie qu’aucun utilisateur n’est installé en local et a été déplacé vers Microsoft 365 ou désactivé :</span><span class="sxs-lookup"><span data-stu-id="8f37d-139">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="8f37d-140">Enregistrez le numéro de téléphone actuel des utilisateurs (LineUri), UserPrincipalName et les informations associées en exécutant l’applet de Skype Entreprise Server PowerShell sur site suivante pour exporter les données utilisateur :</span><span class="sxs-lookup"><span data-stu-id="8f37d-140">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="8f37d-141">Avant de poursuivre lSfbUserSettings.csv fichier et de confirmer que toutes les données utilisateur ont bien été exportées.</span><span class="sxs-lookup"><span data-stu-id="8f37d-141">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="8f37d-142">Il est recommandé de conserver une copie de ce fichier.</span><span class="sxs-lookup"><span data-stu-id="8f37d-142">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="8f37d-143">N’utilisez pas ce fichier dans les étapes suivantes pour traiter les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8f37d-143">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="8f37d-144">Créez un fichier avec un groupe d’utilisateurs à utiliser dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="8f37d-144">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="8f37d-145">Une fois le premier groupe d’utilisateurs terminé, continuez avec le groupe d’utilisateurs suivant.</span><span class="sxs-lookup"><span data-stu-id="8f37d-145">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="8f37d-146">Dans l’exemple ci-dessous, les groupes d’utilisateurs sont sélectionnés par ordre alphabétique, mais vous pouvez filtrer les utilisateurs en fonction de critères qui correspond à la façon dont vous souhaitez traiter les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8f37d-146">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="8f37d-147">Avant de poursuivre lSfbUsers.csv fichier et de confirmer que les données utilisateur ont bien été exportées.</span><span class="sxs-lookup"><span data-stu-id="8f37d-147">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="8f37d-148">Vous aurez besoin de LineUri (numéro de téléphone), UserPrincipalName, SamAccountName et SipAddress à partir de ce fichier dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8f37d-148">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="8f37d-149">Supprimez les informations d’attribut Skype Entreprise Server d’Active Directory pour l’ensemble d’utilisateurs que vous êtes prêt à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="8f37d-149">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="8f37d-150">Ce processus est en deux étapes, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8f37d-150">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="8f37d-151">Après le cycle de AAD Sync suivant après l’exécution de cette étape, les utilisateurs avec Système téléphonique qui ont été précédemment déplacés d’une Skype Entreprise Server sur site vers le cloud perdront la possibilité d’effectuer et de recevoir des appels jusqu’à ce que l’étape 8 soit correctement terminée et confirmée à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="8f37d-151">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="8f37d-152">En outre, assurez-vous que vous avez enregistré les numéros de téléphone et les informations connexes de l’utilisateur à l’étape 2, car ces informations sont requises pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="8f37d-152">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="8f37d-153">Ensuite, pour le même ensemble d’utilisateurs, déséfectez la valeur de msRTCSIP-DeploymentLocator à l’aide d’Active Directory PowerShell local :</span><span class="sxs-lookup"><span data-stu-id="8f37d-153">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="8f37d-154">Exécutez le module Active Directory local suivant pour Windows PowerShell cmdlet pour rajouter une valeur d’adresse sip aux adresses proxy Active Directory sur site.</span><span class="sxs-lookup"><span data-stu-id="8f37d-154">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="8f37d-155">Cela permet d’éviter les problèmes d’interopérabilité qui dépendent de cet attribut.</span><span class="sxs-lookup"><span data-stu-id="8f37d-155">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="8f37d-156">Exécuter Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="8f37d-156">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="8f37d-157">Attendez la fin de la mise en service de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8f37d-157">Wait for user provisioning to complete.</span></span> <span data-ttu-id="8f37d-158">Vous pouvez surveiller la progression de l’approvisionnement des utilisateurs en exécutant la commande powershell Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="8f37d-158">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="8f37d-159">La commande Skype Entreprise Online PowerShell renvoie un résultat vide dès que le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="8f37d-159">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="8f37d-160">Exécutez la commande PowerShell Skype Entreprise Online suivante pour affecter des numéros de téléphone et activer les utilisateurs pour Système téléphonique :</span><span class="sxs-lookup"><span data-stu-id="8f37d-160">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="8f37d-161">Si vous avez encore Skype Entreprise points de terminaison (clients Skype ou téléphones tiers), vous devez également définir -HostedVoiceMail sur $true.</span><span class="sxs-lookup"><span data-stu-id="8f37d-161">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="8f37d-162">Si votre organisation utilise uniquement des points Teams pour les utilisateurs à reconnaissance vocale, ce paramètre n’est pas applicable à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8f37d-162">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="8f37d-163">Confirmez que les utilisateurs Système téléphonique fonctionnalités ont été correctement mis en service.</span><span class="sxs-lookup"><span data-stu-id="8f37d-163">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="8f37d-164">La commande Skype Entreprise Online PowerShell renvoie un résultat vide dès que le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="8f37d-164">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="8f37d-165">Répétez les étapes 3 à 9 jusqu’à ce que tous les utilisateurs soient traitées.</span><span class="sxs-lookup"><span data-stu-id="8f37d-165">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="8f37d-166">Confirmez que tous les utilisateurs ont été correctement traitées en exécutant les deux commandes PowerShell suivantes.</span><span class="sxs-lookup"><span data-stu-id="8f37d-166">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="8f37d-167">Commande PowerShell Skype Entreprise Server sur site :</span><span class="sxs-lookup"><span data-stu-id="8f37d-167">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="8f37d-168">Skype Entreprise Commande PowerShell en ligne :</span><span class="sxs-lookup"><span data-stu-id="8f37d-168">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="8f37d-169">Après avoir effectué toutes les étapes de la méthode 2, voir Déplacer des points de terminaison [d’application](decommission-move-on-prem-endpoints.md) hybride de l’local vers l’application en ligne et Supprimer votre Skype Entreprise Server sur site pour obtenir des [étapes](decommission-remove-on-prem.md) supplémentaires pour supprimer votre déploiement local Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8f37d-169">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="8f37d-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f37d-170">See also</span></span>

- [<span data-ttu-id="8f37d-171">Consolidation du cloud pour Teams et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="8f37d-171">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="8f37d-172">Mise hors service de votre environnement Skype pour entreprises sur site</span><span class="sxs-lookup"><span data-stu-id="8f37d-172">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

