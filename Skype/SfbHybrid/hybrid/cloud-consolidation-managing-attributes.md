---
title: Décider de la façon de gérer les attributs après la mise hors service
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
ms.localizationpriority: medium
description: Cet article explique comment gérer les attributs après la désaffectation de votre environnement local.
ms.openlocfilehash: 2186a3e3c3c1858a9ae071932d5bf4f6d2c72c1c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592899"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Décider de la façon de gérer les attributs après la mise hors service

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Par défaut, tous les utilisateurs qui ont été activés pour Skype Entreprise Server puis déplacés vers le cloud ont toujours des attributs msRTCSIP configurés dans votre Active Directory local. 

Ces attributs, en particulier l’adresse sip (msRTCSIP-PrimaryUserAddress) et le numéro de téléphone (msRTCSIP-Line), continuent de se synchroniser Azure AD. Si des modifications sont requises pour l’un des attributs msRTCSIP, ces modifications doivent être apportées dans le Active Directory local puis synchronisées pour Azure AD. Toutefois, une fois le déploiement Skype Entreprise Server supprimé, les outils de Skype Entreprise Server ne seront pas disponibles pour gérer ces attributs.

Deux options sont disponibles pour gérer cette situation :

1. Laissez les utilisateurs qui ont été activés pour Skype Entreprise comptes de serveur tels qu’ils sont et gérez les attributs msRTCSIP à l’aide des outils Active Directory. Cette méthode garantit l’absence de perte de service pour les utilisateurs migrés et vous permet de supprimer le déploiement Skype Entreprise Server en éliminant (par exemple, la suppression) des serveurs, sans désaffectation complète. Toutefois, les utilisateurs nouvellement titulaires d’une licence n’auront pas ces attributs dans votre Active Directory local et devront être gérés en ligne.

2.  Clear all msRTCSIP attributes from migrated users in your Active Directory local and manage these attributes using online tools. Cette méthode permet une approche de gestion cohérente pour les utilisateurs existants et nouveaux. Toutefois, cela peut entraîner une perte temporaire de service pendant le processus de désaffectation local.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Méthode 1 : gérer les adresses SIP et les numéros de téléphone des utilisateurs dans Active Directory

Les administrateurs peuvent gérer les utilisateurs qui ont été déplacés d’une Skype Entreprise Server sur site vers le cloud, même après la désaffectation du déploiement local. 

Si vous souhaitez apporter des modifications à l’adresse sip d’un utilisateur ou au numéro de téléphone d’un utilisateur (et que l’adresse sip ou le numéro de téléphone a déjà une valeur dans le Active Directory local), vous devez effectuer la modification dans le Active Directory local et laisser les valeurs s’écouler jusqu’à Azure AD. Cette méthode ne nécessite PAS d’Skype Entreprise Server. Au lieu de cela, vous pouvez modifier ces attributs directement dans le Active Directory local, à l’aide du Utilisateurs et ordinateurs Active Directory du logiciel en ligne MMC (comme illustré ci-dessous) ou à l’aide de PowerShell. Si vous utilisez le logiciel en snap-in MMC, ouvrez la page des propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs et recherchez les attributs appropriés à modifier :

- Pour modifier l’adresse SIP d’un utilisateur, modifiez le `msRTCSIP-PrimaryUserAddress`.

    > [!NOTE]
    > Si l’attribut `ProxyAddresses` contient une adresse SIP, mettez également à jour cette valeur en tant que meilleure pratique. Bien que l’adresse sip soit `ProxyAddresses` ignorée par O365 `msRTCSIP-PrimaryUserAddress` si elle est remplie, elle peut être utilisée par d’autres composants locaux.

- Pour modifier le numéro de téléphone d’un utilisateur, modifiez `msRTCSIP-Line` *s’il a déjà une valeur*.

  ![Outil utilisateurs et ordinateurs Active Directory.](../media/disable-hybrid-1.png)


- Si l’utilisateur n’avait à l’origine pas de valeur pour l’environnement local avant le déplacement, vous pouvez modifier le numéro de téléphone à l’aide du paramètre de l’cmdlet `msRTCSIP-Line` [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) dans le module Teams PowerShell.`-PhoneNumber`

Ces étapes ne sont pas nécessaires pour les nouveaux utilisateurs créés après la désactivation de l’hybride, et ces utilisateurs peuvent être gérés directement dans le cloud. Si vous êtes à l’aise avec la combinaison de ces méthodes et que vous souhaitez laisser les attributs msRTCSIP en place dans votre Active Directory local, vous pouvez ré-imager les serveurs Skype Entreprise locaux. Toutefois, si vous préférez effacer tous les attributs msRTCSIP et faire une désinstallation traditionnelle de Skype Entreprise Server, utilisez la méthode 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Méthode 2 : effacer Skype Entreprise pour tous les utilisateurs locaux dans Active Directory

Cette option nécessite plus d’efforts et une planification appropriée, car les utilisateurs qui ont été déplacés d’un Skype Entreprise Server local vers le cloud doivent être réapprovisionnement. Ces utilisateurs peuvent être classés dans deux catégories différentes : les utilisateurs sans Système téléphonique et les utilisateurs Système téléphonique. Les utilisateurs Système téléphonique seront temporairement perdus du service téléphonique dans le cadre de la transition du numéro de téléphone de la gestion Active Directory local vers le cloud. **Il est recommandé d’effectuer un projet pilote impliquant un petit nombre d’utilisateurs avec Système téléphonique avant de démarrer des opérations utilisateur en bloc.** Pour les déploiements de grande taille, les utilisateurs peuvent être traitées par groupes plus petits dans différentes fenêtres de temps. 

> [!NOTE] 
> Ce processus est plus simple pour les utilisateurs qui ont une adresse sip correspondante et UserPrincipalName. Pour les organisations dont les utilisateurs ont des valeurs non correspondantes dans ces deux attributs, une attention supplémentaire doit être prise comme indiqué ci-dessous pour une transition fluide.

> [!NOTE]
> Si vous avez configuré des points de terminaison d’application hybride sur site pour les attendants automatiques ou les files d’attente d’appels, veillez à déplacer ces points de terminaison vers Microsoft 365 avant de désaffecter Skype Entreprise Server. Pour plus d’informations, voir [Migrate hybrid application endpoints before decommissioning your on-premises environment](decommission-move-on-prem-endpoints.md).  


1. Confirmez que l’Skype Entreprise cmdlet PowerShell suivante renvoie un résultat vide. Un résultat vide signifie qu’aucun utilisateur n’est installé en local et a été déplacé vers Microsoft 365 ou désactivé :

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Enregistrez le numéro de téléphone actuel des utilisateurs (LineUri), UserPrincipalName et les informations connexes en exécutant l’applet de Skype Entreprise Server PowerShell sur site suivante pour exporter les données utilisateur :

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Avant de poursuivre lSfbUserSettings.csv fichier et de confirmer que toutes les données utilisateur ont bien été exportées. Il est recommandé de conserver une copie de ce fichier.  N’utilisez pas ce fichier dans les étapes suivantes pour traiter les utilisateurs. 

3. Créez un fichier avec un groupe d’utilisateurs à utiliser dans les étapes suivantes. Une fois le premier groupe d’utilisateurs terminé, continuez avec le groupe d’utilisateurs suivant. Dans l’exemple ci-dessous, les groupes d’utilisateurs sont sélectionnés par ordre alphabétique. Vous pouvez filtrer les utilisateurs en fonction de critères qui correspond à la façon dont vous souhaitez traiter les utilisateurs.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Avant de poursuivre lSfbUsers.csv fichier et de confirmer que les données utilisateur ont bien été exportées. Vous aurez besoin de LineUri (numéro de téléphone), UserPrincipalName, SamAccountName et SipAddress à partir de ce fichier dans une étape ultérieure.

4. Supprimez les informations d’attribut Skype Entreprise Server d’Active Directory pour l’ensemble d’utilisateurs que vous êtes prêt à mettre à jour.  Ce processus se fait en deux étapes, comme illustré ci-dessous.

   > [!Important] 
   > Après le cycle de AAD Sync suivant après l’exécution de cette étape, les utilisateurs avec Système téléphonique qui ont été déplacés d’une Skype Entreprise Server sur site vers le cloud perdront la possibilité de prendre et de recevoir des appels jusqu’à ce que l’étape 8 soit correctement terminée et confirmée à l’étape 9. En outre, assurez-vous que vous avez enregistré les numéros de téléphone et les informations connexes de l’utilisateur à l’étape 2, car ces informations sont requises pour cette étape.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Ensuite, pour le même ensemble d’utilisateurs, déséfectez la valeur de msRTCSIP-DeploymentLocator à l’aide Active Directory local PowerShell :

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Pour rajouter une valeur d’adresse sip Active Directory local proxyAddresses, exécutez l’Active Directory local module pour Windows PowerShell cmdlet. Cette action empêche les problèmes d’interopérabilité qui reposent sur cet attribut. 

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

6. Exécuter Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Attendez la fin de la mise en service de l’utilisateur. Vous pouvez surveiller la progression de l’approvisionnement des utilisateurs en exécutant la commande powershell Teams suivante. La commande Teams PowerShell suivante renvoie un résultat vide dès que le processus est terminé.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (UserValidationErrors -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Pour attribuer des numéros de téléphone et activer les utilisateurs pour Système téléphonique, exécutez la commande PowerShell Teams suivante :


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  Si vous avez encore Skype Entreprise points de terminaison (clients Skype ou téléphones tiers), vous devez également définir -HostedVoiceMail sur $true. Si votre organisation utilise uniquement des points Teams pour les utilisateurs à reconnaissance vocale, ce paramètre n’est pas applicable à vos utilisateurs. 

9. Confirmez que les utilisateurs Système téléphonique fonctionnalités ont été correctement mis en service. La commande Teams PowerShell suivante renvoie un résultat vide dès que le processus est terminé.

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

10. Répétez les étapes 3 à 9 jusqu’à ce que tous les utilisateurs soient traitées.

11. Confirmez que tous les utilisateurs ont été correctement traitées en exécutant les deux commandes PowerShell suivantes.

    Commande PowerShell Skype Entreprise Server sur site :

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams commande PowerShell :

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 

12. Une fois que vous avez effectué toutes les [étapes](decommission-move-on-prem-endpoints.md) de la méthode 2, voir Déplacer des points de terminaison d’application hybride de l’local vers l’application en ligne et Supprimer votre Skype Entreprise Server local pour obtenir des [étapes](decommission-remove-on-prem.md) supplémentaires pour supprimer votre déploiement local Skype Entreprise Server.


## <a name="see-also"></a>Voir aussi

- [Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

