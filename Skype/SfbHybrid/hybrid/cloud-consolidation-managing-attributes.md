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
ms.openlocfilehash: 64ba4844a1958cfd386a177d91b9c4f2dff89102
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58736023"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Décider de la façon de gérer les attributs après la mise hors service

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Par défaut, tous les utilisateurs qui ont été précédemment activés pour Skype Entreprise Server puis déplacés vers le cloud ont toujours des attributs msRTCSIP configurés dans votre annuaire Active Directory local. 

Ces attributs, en particulier l’adresse sip (msRTCSIP-PrimaryUserAddress) et potentiellement le numéro de téléphone (msRTCSIP-Line), continuent de se synchroniser avec Azure AD. Si des modifications sont requises pour l’un des attributs msRTCSIP, ces modifications doivent être apportées dans l’annuaire Active Directory local, puis synchronisées avec Azure AD. Toutefois, une fois le déploiement Skype Entreprise Server supprimé, les outils Skype Entreprise Server ne seront pas disponibles pour gérer ces attributs.

Deux options sont disponibles pour gérer cette situation :

1. Laissez les utilisateurs qui ont été activés pour Skype Entreprise comptes serveur tels qu’ils sont et gérez les attributs msRTCSIP à l’aide des outils Active Directory. Cela garantit l’absence de perte de service pour les utilisateurs migrés et vous permet de supprimer facilement le déploiement Skype Entreprise Server en éliminant (par exemple, la suppression) des serveurs, sans désaffectation complète. Toutefois, les utilisateurs nouvellement titulaires d’une licence n’auront pas ces attributs dans votre annuaire Active Directory local et devront être gérés en ligne.

2.  Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools. Cette méthode permet une approche de gestion cohérente pour les utilisateurs existants et nouveaux, mais elle peut potentiellement entraîner une perte temporaire de service pendant le processus de mise hors service local.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Méthode 1 : gérer les adresses SIP et les numéros de téléphone des utilisateurs dans Active Directory

Les administrateurs peuvent gérer les utilisateurs qui ont été précédemment déplacés d’une Skype Entreprise Server sur site vers le cloud, même après la désaffectation du déploiement local. 

Si vous souhaitez apporter des modifications à l’adresse SIP d’un utilisateur ou au numéro de téléphone d’un utilisateur (et que l’adresse sip ou le numéro de téléphone a déjà une valeur dans l’annuaire Active Directory local), vous devez le faire dans l’annuaire Active Directory local et laisser les valeurs s’écouler jusqu’à Azure AD. Cela ne nécessite PAS de Skype Entreprise Server. Au lieu de cela, vous pouvez modifier ces attributs directement dans Active Directory local, à l’aide du logiciel en ligne MMC Utilisateurs et ordinateurs Active Directory (comme illustré ci-dessous) ou à l’aide de PowerShell. Si vous utilisez le logiciel en snap-in MMC, ouvrez la page des propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs et recherchez les attributs appropriés à modifier :

- Pour modifier l’adresse SIP d’un utilisateur, modifiez le `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Si `ProxyAddresses` l’attribut contient une adresse SIP, mettez également à jour cette valeur en tant que meilleure pratique. Bien que l’adresse sip dans soit ignorée par O365 si elle est remplie, elle peut être utilisée par d’autres `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` composants locaux.

- Pour modifier le numéro de téléphone d’un utilisateur, modifiez `msRTCSIP-Line` *s’il a déjà une valeur.*

  ![Outil utilisateurs et ordinateurs Active Directory.](../media/disable-hybrid-1.png)
  
-  Si l’utilisateur n’avait à l’origine pas de valeur pour l’environnement local avant le déplacement, vous pouvez modifier le numéro de téléphone à l’aide du paramètre - dans `msRTCSIP-Line` l’cmdlet `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) du module Teams PowerShell.

Ces étapes ne sont pas nécessaires pour les nouveaux utilisateurs créés après la désactivation de l’hybride, et ces utilisateurs peuvent être gérés directement dans le cloud. Si vous êtes à l’aise avec la combinaison de ces méthodes et si vous souhaitez laisser les attributs msRTCSIP en place dans votre environnement Active Directory local, vous pouvez simplement ré-imager les serveurs Skype Entreprise locaux. Toutefois, si vous préférez effacer tous les attributs msRTCSIP et faire une désinstallation traditionnelle de Skype Entreprise Server, utilisez la méthode 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Méthode 2 : effacer Skype Entreprise pour tous les utilisateurs locaux dans Active Directory

Cette option nécessite des efforts supplémentaires et une planification appropriée, car les utilisateurs qui ont été précédemment déplacés d’une Skype Entreprise Server sur site vers le cloud doivent être réapprovisionnement. Ces utilisateurs peuvent être classés dans deux catégories différentes : les utilisateurs sans Système téléphonique et les utilisateurs Système téléphonique. Les utilisateurs Système téléphonique seront temporairement perdus du service téléphonique dans le cadre de la transition du numéro de téléphone de la gestion dans Active Directory local vers le cloud. **Il est recommandé d’effectuer un projet pilote impliquant un petit nombre d’utilisateurs avec Système téléphonique avant de démarrer des opérations utilisateur en bloc.** Pour les déploiements de grande taille, les utilisateurs peuvent être traitées par groupes plus petits dans différentes fenêtres de temps. 

> [!NOTE] 
> Ce processus est plus simple pour les utilisateurs qui ont une adresse sip correspondante et UserPrincipalName. Pour les organisations dont les utilisateurs ont des valeurs non correspondantes dans ces deux attributs, une attention supplémentaire doit être prise comme indiqué ci-dessous pour une transition fluide.

> [!NOTE]
> Si vous avez configuré des points de terminaison d’application hybride sur site pour les attendants automatiques ou les files d’attente d’appels, veillez à déplacer ces points de terminaison vers Microsoft 365 avant de désaffecter Skype Entreprise Server. Pour plus d’informations, voir Migrer des points de terminaison d’application hybride avant de désaffecter votre [environnement local.](decommission-move-on-prem-endpoints.md)  


1. Confirmez que l’Skype Entreprise cmdlet PowerShell suivante renvoie un résultat vide. Un résultat vide signifie qu’aucun utilisateur n’est installé en local et a été déplacé vers Microsoft 365 ou désactivé :

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Enregistrez le numéro de téléphone actuel des utilisateurs (LineUri), UserPrincipalName et les informations associées en exécutant l’applet de Skype Entreprise Server PowerShell sur site suivante pour exporter les données utilisateur :

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Avant de poursuivre lSfbUserSettings.csv fichier et de confirmer que toutes les données utilisateur ont bien été exportées. Il est recommandé de conserver une copie de ce fichier.  N’utilisez pas ce fichier dans les étapes suivantes pour traiter les utilisateurs. 

3. Créez un fichier avec un groupe d’utilisateurs à utiliser dans les étapes suivantes. Une fois le premier groupe d’utilisateurs terminé, continuez avec le groupe d’utilisateurs suivant. Dans l’exemple ci-dessous, les groupes d’utilisateurs sont sélectionnés par ordre alphabétique, mais vous pouvez filtrer sur les utilisateurs en fonction de critères qui correspond à la façon dont vous souhaitez traiter les utilisateurs.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Avant de poursuivre lSfbUsers.csv fichier et de confirmer que les données utilisateur ont bien été exportées. Vous aurez besoin de LineUri (numéro de téléphone), UserPrincipalName, SamAccountName et SipAddress à partir de ce fichier dans une étape ultérieure.

4. Supprimez les informations d’attribut Skype Entreprise Server d’Active Directory pour l’ensemble d’utilisateurs que vous êtes prêt à mettre à jour.  Ce processus est en deux étapes, comme illustré ci-dessous.

   > [!Important] 
   > Après le cycle de AAD Sync suivant après l’exécution de cette étape, les utilisateurs avec Système téléphonique qui ont été précédemment déplacés d’une Skype Entreprise Server sur site vers le cloud perdront la possibilité d’effectuer et de recevoir des appels jusqu’à ce que l’étape 8 soit correctement terminée et confirmée à l’étape 9. En outre, assurez-vous que vous avez enregistré les numéros de téléphone et les informations connexes de l’utilisateur à l’étape 2, car ces informations sont requises pour cette étape.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Ensuite, pour le même ensemble d’utilisateurs, désinsértez la valeur de msRTCSIP-DeploymentLocator à l’aide d’Active Directory PowerShell local :

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Exécutez le module Active Directory local suivant pour Windows PowerShell cmdlet pour rajouter une valeur d’adresse sip aux adresses proxy Active Directory sur site. Cela permet d’éviter les problèmes d’interopérabilité qui dépendent de cet attribut. 

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
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Exécutez la commande PowerShell Teams suivante pour affecter des numéros de téléphone et activer les utilisateurs pour Système téléphonique :
     
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

    Teams Commande PowerShell :

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 

12. Après avoir effectué toutes les étapes de la méthode 2, voir Déplacer des points de terminaison [d’application](decommission-move-on-prem-endpoints.md) hybride de l’local vers l’application en ligne et Supprimer votre Skype Entreprise Server sur site pour obtenir des [étapes](decommission-remove-on-prem.md) supplémentaires pour supprimer votre déploiement local Skype Entreprise Server.


## <a name="see-also"></a>Voir aussi

- [Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

