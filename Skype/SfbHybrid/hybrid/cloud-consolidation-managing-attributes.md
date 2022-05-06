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
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249016"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Décider de la façon de gérer les attributs après la mise hors service

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Par défaut, tous les utilisateurs qui ont été activés pour Skype Entreprise Server puis déplacés vers le cloud ont toujours des attributs msRTCSIP configurés dans votre Active Directory local. 

Ces attributs, en particulier l’adresse sip (msRTCSIP-PrimaryUserAddress) et le numéro de téléphone (msRTCSIP-Line), continuent à se synchroniser dans Azure AD. Si des modifications sont requises pour l’un des attributs msRTCSIP, ces modifications doivent être apportées dans le Active Directory local, puis synchronisées pour Azure AD. Toutefois, une fois le déploiement Skype Entreprise Server supprimé, les outils de Skype Entreprise Server ne seront pas disponibles pour gérer ces attributs.

Deux options sont disponibles pour gérer cette situation :

1. Laissez les utilisateurs activés pour Skype Entreprise comptes de serveur tels qu’ils sont et gérez les attributs msRTCSIP à l’aide des outils Active Directory. Cette méthode garantit l’absence de perte de service pour les utilisateurs migrés et vous permet de supprimer le déploiement Skype Entreprise Server en éliminant (par exemple, la réinitialisation) les serveurs, sans mise hors service complète. Toutefois, les utilisateurs nouvellement sous licence ne disposeront pas de ces attributs dans votre Active Directory local et devront être gérés en ligne.

2.  Effacez tous les attributs msRTCSIP des utilisateurs migrés dans votre Active Directory local et gérez ces attributs à l’aide d’outils en ligne. Cette méthode permet une approche de gestion cohérente pour les utilisateurs existants et nouveaux. Toutefois, cela peut entraîner une perte temporaire de service pendant le processus de désaffectation local.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Méthode 1 : gérer les adresses sip et les numéros de téléphone des utilisateurs dans Active Directory

Les administrateurs peuvent gérer les utilisateurs qui ont été déplacés d’un Skype Entreprise Server local vers le cloud, même après la désaffectation du déploiement local. 

Si vous souhaitez apporter des modifications à l’adresse sip d’un utilisateur ou au numéro de téléphone d’un utilisateur (et que l’adresse de la sip ou le numéro de téléphone a déjà une valeur dans le Active Directory local), vous devez effectuer la modification dans le Active Directory local et laisser la ou les valeurs circuler jusqu’à Azure AD. Cette méthode ne nécessite PAS de Skype Entreprise Server locale. Au lieu de cela, vous pouvez modifier ces attributs directement dans le Active Directory local, à l’aide du composant logiciel enfichable MMC Utilisateurs et ordinateurs Active Directory (comme indiqué ci-dessous) ou à l’aide de PowerShell. Si vous utilisez le composant logiciel enfichable MMC, ouvrez la page des propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs et recherchez les attributs appropriés à modifier :

- Pour modifier l’adresse sip d’un utilisateur, modifiez le `msRTCSIP-PrimaryUserAddress`.

    > [!NOTE]
    > Si l’attribut `ProxyAddresses` contient une adresse sip, mettez également à jour cette valeur comme meilleure pratique. Bien que l’adresse de sip soit `ProxyAddresses` ignorée par O365 si `msRTCSIP-PrimaryUserAddress` elle est remplie, elle peut être utilisée par d’autres composants locaux.

- Pour modifier le numéro de téléphone d’un utilisateur, modifiez `msRTCSIP-Line` *s’il a déjà une valeur*.

  ![Outil utilisateurs et ordinateurs Active Directory.](../media/disable-hybrid-1.png)


- Si l’utilisateur n’avait pas à l’origine de valeur locale `msRTCSIP-Line` avant le déplacement, vous pouvez modifier le numéro de téléphone à l’aide du `-PhoneNumber` paramètre dans [l’applet de commande Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) dans le module PowerShell Teams.

Ces étapes ne sont pas nécessaires pour les nouveaux utilisateurs créés après la désactivation de l’hybride, et ces utilisateurs peuvent être gérés directement dans le cloud. Si vous êtes à l’aise avec la combinaison de ces méthodes et que vous laissez les attributs msRTCSIP en place dans votre Active Directory local, vous pouvez re-imager les serveurs Skype Entreprise locaux. Toutefois, si vous préférez effacer tous les attributs msRTCSIP et effectuer une désinstallation traditionnelle de Skype Entreprise Server, utilisez la méthode 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Méthode 2 : effacer les attributs Skype Entreprise pour tous les utilisateurs locaux dans Active Directory

Cette option nécessite plus d’efforts et une planification appropriée, car les utilisateurs qui ont été déplacés d’un Skype Entreprise Server local vers le cloud doivent être réapprovisionnements. Ces utilisateurs peuvent être classés en deux catégories différentes : les utilisateurs sans Système téléphonique et les utilisateurs avec Système téléphonique. Les utilisateurs avec Système téléphonique subiront une perte temporaire de service téléphonique dans le cadre de la transition du numéro de téléphone de la gestion de Active Directory local vers le cloud. **Il est recommandé d’effectuer un pilote impliquant un petit nombre d’utilisateurs avec Système téléphonique avant de démarrer des opérations utilisateur en bloc.** Pour les déploiements de grande taille, les utilisateurs peuvent être traités dans des groupes plus petits dans différentes fenêtres de temps. 

> [!NOTE] 
> Ce processus est plus simple pour les utilisateurs qui ont une adresse sip correspondante et UserPrincipalName. Pour les organisations qui ont des utilisateurs avec des valeurs non correspondantes entre ces deux attributs, vous devez faire attention, comme indiqué ci-dessous, pour une transition sans heurts.

> [!NOTE]
> Si vous avez configuré des points de terminaison d’application hybrides locaux pour les standards automatiques ou les files d’attente d’appels, veillez à déplacer ces points de terminaison vers Microsoft 365 avant de désactiver Skype Entreprise Server. Pour plus d’informations, consultez [Migrer des points de terminaison d’application hybride avant de désactiver votre environnement local](decommission-move-on-prem-endpoints.md).  


1. Vérifiez que l’applet de commande PowerShell Skype Entreprise locale suivante retourne un résultat vide. Un résultat vide signifie qu’aucun utilisateur n’est hébergé localement et qu’il a été déplacé vers Microsoft 365 ou qu’il a été désactivé :

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Enregistrez le numéro de téléphone actuel des utilisateurs (LineUri), UserPrincipalName et les informations associées en exécutant l’applet de commande PowerShell locale suivante Skype Entreprise Server pour exporter les données utilisateur :

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Avant d’ouvrir SfbUserSettings.csv fichier et de confirmer que toutes les données utilisateur ont été exportées avec succès. Il est recommandé de conserver une copie de ce fichier.  N’utilisez pas ce fichier dans les étapes suivantes pour traiter les utilisateurs. 

3. Créez un fichier avec un groupe d’utilisateurs à utiliser dans les étapes suivantes. Une fois le premier groupe d’utilisateurs terminé, passez au groupe d’utilisateurs suivant. Dans l’exemple ci-dessous, les groupes d’utilisateurs sont sélectionnés par ordre alphabétique. Vous pouvez filtrer les utilisateurs en fonction de critères qui correspondent à la façon dont vous souhaitez traiter les utilisateurs.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Avant d’ouvrir SfbUsers.csv fichier et de confirmer que les données utilisateur ont été exportées avec succès. Vous aurez besoin de LineUri (numéro de téléphone), UserPrincipalName, SamAccountName et SipAddress à partir de ce fichier dans une étape ultérieure.

4. Supprimez les informations d’attribut liées à Skype Entreprise Server d’Active Directory pour l’ensemble d’utilisateurs que vous êtes prêt à mettre à jour.  Ce processus comporte deux étapes, comme indiqué ci-dessous.

   > [!Important] 
   > Après la prochaine AAD Sync cycle après l’exécution de cette étape, les utilisateurs ayant Système téléphonique qui ont été déplacés d’un Skype Entreprise Server local vers le cloud perdront la possibilité d’effectuer et de recevoir des appels jusqu’à ce que l’étape 8 soit terminée et confirmée à l’étape 9. En outre, assurez-vous que vous avez enregistré les numéros de téléphone de l’utilisateur et les informations connexes conformément à l’étape 2, car ces informations sont requises pour cette étape.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Ensuite, pour le même ensemble d’utilisateurs, effacez la valeur de msRTCSIP-DeploymentLocator à l’aide de Active Directory local PowerShell :

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Pour rajouter une valeur d’adresse sip aux Active Directory local proxyAddresses, exécutez le module Active Directory local suivant pour Windows PowerShell cmdlet. Cette action empêche les problèmes d’interopérabilité qui reposent sur cet attribut. 

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

7. Attendez que l’approvisionnement des utilisateurs se termine. Vous pouvez surveiller la progression de l’approvisionnement des utilisateurs en exécutant la commande PowerShell Teams suivante. La commande PowerShell Teams suivante retourne un résultat vide dès que le processus est terminé.

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. Pour affecter des numéros de téléphone et activer les utilisateurs pour Système téléphonique, exécutez la commande PowerShell Teams suivante :


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
   >  Si vous avez toujours Skype Entreprise points de terminaison (clients Skype ou téléphones tiers), vous pouvez également définir -HostedVoiceMail sur $true. Si votre organisation utilise uniquement Teams points de terminaison pour les utilisateurs avec voix activée, ce paramètre n’est pas applicable à vos utilisateurs. 

9. Vérifiez que les utilisateurs disposant de Système téléphonique fonctionnalités ont été provisionnées correctement. La commande PowerShell Teams suivante retourne un résultat vide dès que le processus est terminé.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. Répétez les étapes 3 à 9 jusqu’à ce que tous les utilisateurs soient traités.

11. Vérifiez que tous les utilisateurs ont été traités correctement en exécutant les deux commandes PowerShell suivantes.

    Commande PowerShell locale Skype Entreprise Server :

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    commande PowerShell Teams :

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. Une fois que vous avez effectué toutes les étapes de la méthode 2, consultez [Déplacer des points de terminaison d’application hybride d’un site local vers un site en ligne](decommission-move-on-prem-endpoints.md) et [supprimez votre Skype Entreprise Server](decommission-remove-on-prem.md) local pour obtenir des étapes supplémentaires pour supprimer votre Skype Entreprise Server déploiement local.


## <a name="see-also"></a>Voir aussi

- [Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

