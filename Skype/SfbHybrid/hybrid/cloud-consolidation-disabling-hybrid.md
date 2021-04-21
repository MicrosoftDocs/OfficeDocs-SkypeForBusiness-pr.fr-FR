---
title: Désactiver le mode hybride pour terminer la migration vers le cloud
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
description: Cet article comprend des étapes détaillées pour la désactivation de l'hybride dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: 08d305fa2650cffbadb0ec3122458f4a57e052a4
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899105"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a>Désactiver votre configuration hybride pour terminer la migration vers le cloud

Cet article explique comment désactiver votre configuration hybride avant de désaffecter votre environnement Skype Entreprise local. Il s'agit de l'étape 2 des étapes suivantes pour désaffecter votre environnement local :

- Étape 1. [Déplacez tous les utilisateurs requis de l'local vers le site en ligne.](decommission-move-on-prem-users.md)

- **Étape 2. Désactivez votre configuration hybride.** (Cet article)

- Étape 3. [Déplacez les points de terminaison de l'application hybride de l'local vers le mode en ligne.](decommission-move-on-prem-endpoints.md)

- Étape 4. [Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)


## <a name="overview"></a>Vue d’ensemble

Après avoir mis à niveau tous les utilisateurs de Skype Entreprise en local vers Teams uniquement dans Microsoft 365, vous pouvez désaffecter le déploiement Skype Entreprise local. Avant de désaffecter le déploiement Skype Entreprise local et de supprimer du matériel, vous devez séparer logiquement le déploiement local de Microsoft 365 en désactivant l'hybride. La désactivation hybride se compose des trois étapes suivantes :

1. Mettre à jour les enregistrements DNS pour qu'ils pointent vers Microsoft 365.

2. Désactivez l'espace d'adressare sip partagé (également appelé « domaine fractioné ») dans l'organisation Microsoft 365.

3. Désactivez la possibilité de communiquer en local avec Microsoft 365.

Ces étapes séparent logiquement votre déploiement local de Skype Entreprise Server de Microsoft 365 et doivent être réalisées ensemble. Les détails de chaque étape sont fournis dans cet article. Une fois l'installation terminée, vous pouvez désaffecter votre déploiement Skype Entreprise local à l'aide de l'une des deux méthodes référencés ci-dessous.

> [!Important] 
> Une fois cette séparation logique terminée, les attributs msRTCSIP de votre active Directory local ont toujours des valeurs et continueront à se synchroniser via Azure AD Connect dans Azure AD. La façon dont vous désaffectez l'environnement local varie selon que vous avez l'intention de laisser ces attributs en place ou de les effacer d'abord de votre environnement Active Directory local. Sachez que l'effacement des attributs msRTCSIP locaux une fois que vous avez migré à partir de l'local peut entraîner une perte de service pour les utilisateurs ! Les détails et les compromis des deux approches de désaffectation sont décrits plus loin.

## <a name="detailed-steps"></a>Étapes détaillées

1. *Mettez à jour le DNS pour qu'il pointe vers Microsoft 365.* Le DNS externe de l'organisation pour l'organisation sur site doit être mis à jour afin que les enregistrements Skype Entreprise pointent vers Microsoft 365 au lieu du déploiement local. Notamment :

    |Type d’enregistrement|Nom|Durée de vie|Value (Valeur)|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|

    En outre, les enregistrements CNAME pour la meet ou dialin (le cas présent) peuvent être supprimés. Enfin, tous les enregistrements DNS pour Skype Entreprise dans votre réseau interne doivent être supprimés.

    > [!Note] 
    > Dans de rares cas, la modification du DNS de pointage local vers Microsoft 365 pour votre organisation peut entraîner l'arrêt de la fédération avec d'autres organisations jusqu'à ce que cette autre organisation met à jour sa configuration de fédération :
    >
    > - Toutes les organisations fédérées qui utilisent l'ancien modèle de fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour que leur organisation supprime le nom de domaine réservé au proxy. Ce modèle de fédération hérité n'est pas basé sur des enregistrements DNS SRV, de sorte qu'une telle configuration ne sera plus à jour une fois que votre organisation sera installée dans le cloud.
    > 
    > - Toute organisation fédérée qui n'a pas de fournisseur d'hébergement activé pour sipfed.online.lync. <span> com devra mettre à jour sa configuration pour l'activer. Cette situation n'est possible que si l'organisation fédérée est purement sur site et n'a jamais été fédérée avec un client hybride ou en ligne. Dans ce cas, la fédération avec ces organisations ne fonctionne pas tant qu'elles n'ont pas activé leur fournisseur d'hébergement.
    >
    > Si vous pensez que l'un de vos partenaires fédérés peut utiliser la fédération directe ou n'avoir été fédéré avec aucune organisation en ligne ou hybride, nous vous suggérons de leur envoyer une communication à ce sujet lorsque vous vous préparez à terminer votre migration vers le cloud.


2.  *Désactivez l'espace d'adressare sip partagé dans l'organisation Microsoft 365.* La commande ci-dessous doit être effectuée à partir d'une fenêtre PowerShell Skype Entreprise Online.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *Désactivez la possibilité de communiquer en local avec Microsoft 365.* La commande ci-dessous doit être effectuée à partir d'une fenêtre PowerShell sur site :

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Gestion des attributs après le déplacement d'utilisateurs de l'local vers le cloud

Par défaut, tous les utilisateurs qui étaient précédemment activés pour Skype Entreprise Server et qui sont ensuite déplacés vers le cloud ont toujours des attributs msRTCSIP configurés dans votre annuaire Active Directory local. Ces attributs, en particulier l'adresse sip (msRTCSIP-PrimaryUserAddress) et potentiellement le numéro de téléphone (msRTCSIP-Line), continuent de se synchroniser avec Azure AD. Si des modifications sont requises pour l'un des attributs msRTCSIP, ces modifications doivent être apportées dans l'annuaire Active Directory local, puis synchronisées avec Azure AD. Toutefois, une fois le déploiement de Skype Entreprise Server supprimé, les outils Skype Entreprise Server ne seront pas disponibles pour gérer ces attributs.

Deux options sont disponibles pour gérer cette situation :

1. Laissez les utilisateurs activés pour les comptes de serveur Skype Entreprise tels qu'ils sont et gérez les attributs msRTCSIP à l'aide des outils Active Directory. Cela garantit l'absence de perte de service pour les utilisateurs migrés et vous permet de supprimer facilement le déploiement de Skype Entreprise Server en éliminant (par exemple, la suppression) des serveurs, sans désaffectation complète. Toutefois, les utilisateurs nouvellement titulaires d'une licence n'auront pas ces attributs dans votre annuaire Active Directory local et devront être gérés en ligne.

2.  Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools. Cette méthode permet une approche de gestion cohérente pour les utilisateurs existants et nouveaux, mais elle peut potentiellement entraîner une perte temporaire de service pendant le processus de mise hors service local.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Méthode 1 : gérer les adresses SIP et les numéros de téléphone des utilisateurs dans Active Directory

Les administrateurs peuvent gérer les utilisateurs qui ont été précédemment déplacés d'un serveur Skype Entreprise local vers le cloud, même après la désaffectation du déploiement local. Si vous souhaitez apporter des modifications à l'adresse SIP d'un utilisateur ou au numéro de téléphone d'un utilisateur (et que l'adresse sip ou le numéro de téléphone a déjà une valeur dans l'annuaire Active Directory local), vous devez le faire dans l'annuaire Active Directory local et laisser les valeurs s'écouler jusqu'à Azure AD. Cela ne nécessite PAS Skype Entreprise Server local. Au lieu de cela, vous pouvez modifier ces attributs directement dans Active Directory local, à l'aide du logiciel en ligne MMC Utilisateurs et ordinateurs Active Directory (comme illustré ci-dessous) ou à l'aide de PowerShell. Si vous utilisez le logiciel en snap-in MMC, ouvrez la page des propriétés de l'utilisateur, cliquez sur l'onglet Éditeur d'attributs et recherchez les attributs appropriés à modifier :

- Pour modifier l'adresse SIP d'un utilisateur, modifiez le `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Si `ProxyAddresses` l'attribut contient une adresse SIP, mettez également à jour cette valeur en tant que meilleure pratique. Bien que l'adresse sip dans soit ignorée par O365 si elle est remplie, elle peut être utilisée par d'autres `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` composants locaux.

- Pour modifier le numéro de téléphone d'un utilisateur, modifiez `msRTCSIP-Line` *s'il a déjà une valeur.*

  ![Outil utilisateurs et ordinateurs Active Directory](../media/disable-hybrid-1.png)
  
-  Si l'utilisateur n'avait à l'origine pas de valeur pour l'environnement local avant le déplacement, vous pouvez modifier le numéro de téléphone à l'aide du paramètre - dans `msRTCSIP-Line` l'cmdlet `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) du module PowerShell de Skype Entreprise Online.

Ces étapes ne sont pas nécessaires pour les nouveaux utilisateurs créés après la désactivation de l'hybride, et ces utilisateurs peuvent être gérés directement dans le cloud. Si vous êtes à l'aise avec la combinaison de ces méthodes et si vous souhaitez laisser les attributs msRTCSIP en place dans votre environnement Active Directory local, vous pouvez simplement ré-imager les serveurs Skype Entreprise locaux. Toutefois, si vous préférez effacer tous les attributs msRTCSIP et faire une désinstallation traditionnelle de Skype Entreprise Server, utilisez la méthode 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Méthode 2 : effacer les attributs Skype Entreprise pour tous les utilisateurs locaux dans Active Directory

Cette option nécessite des efforts supplémentaires et une planification appropriée, car les utilisateurs qui ont été précédemment déplacés d'un serveur Skype Entreprise local vers le cloud doivent être réapprovisionnement. Ces utilisateurs peuvent être classés dans deux catégories différentes : les utilisateurs sans système téléphonique et les utilisateurs avec système téléphonique. Les utilisateurs avec le système téléphonique seront temporairement perdus du service téléphonique dans le cadre de la transition du numéro de téléphone de la gestion dans Active Directory local vers le cloud. **Il est recommandé d'effectuer un projet pilote impliquant un petit nombre d'utilisateurs avec le système téléphonique avant de démarrer des opérations utilisateur en bloc.** Pour les déploiements de grande taille, les utilisateurs peuvent être traitées par groupes plus petits dans différentes fenêtres de temps. 

> [!NOTE] 
> Ce processus est plus simple pour les utilisateurs qui ont une adresse sip correspondante et UserPrincipalName. Pour les organisations dont les utilisateurs ont des valeurs non correspondantes dans ces deux attributs, une attention supplémentaire doit être prise comme indiqué ci-dessous pour une transition fluide.

> [!NOTE]
> Si vous avez configuré des points de terminaison d'application hybride sur site pour les attendants automatiques ou les files d'attente d'appels, veillez à déplacer ces points de terminaison vers Microsoft 365 avant de désaffecter Skype Entreprise Server.


1. Confirmez que l'cmdlet PowerShell Skype Entreprise local suivante renvoie un résultat vide. Un résultat vide signifie qu'aucun utilisateur n'est installé sur site et a été déplacé vers Microsoft 365 ou a été désactivé :

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Enregistrez le numéro de téléphone actuel des utilisateurs (LineUri), UserPrincipalName et les informations connexes en exécutant l'applet de la cmdlet PowerShell Skype Entreprise Server sur site suivante pour exporter les données utilisateur :

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Avant de poursuivre lSfbUserSettings.csv fichier et de confirmer que toutes les données utilisateur ont bien été exportées. Il est recommandé de conserver une copie de ce fichier.  N’utilisez pas ce fichier dans les étapes suivantes pour traiter les utilisateurs. 

3. Créez un fichier avec un groupe d’utilisateurs à utiliser dans les étapes suivantes. Une fois le premier groupe d’utilisateurs terminé, continuez avec le groupe d’utilisateurs suivant. Dans l’exemple ci-dessous, les groupes d’utilisateurs sont sélectionnés par ordre alphabétique, mais vous pouvez filtrer les utilisateurs en fonction de critères qui correspond à la façon dont vous souhaitez traiter les utilisateurs.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Avant de poursuivre lSfbUsers.csv fichier et de confirmer que les données utilisateur ont bien été exportées. Vous aurez besoin de LineUri (numéro de téléphone), UserPrincipalName, SamAccountName et SipAddress à partir de ce fichier dans une étape ultérieure.

4. Supprimez les informations d’attribut relatives à Skype Entreprise Server d’Active Directory pour l’ensemble d’utilisateurs que vous êtes prêt à mettre à jour.  Ce processus est en deux étapes, comme illustré ci-dessous.

   > [!Important] 
   > Après le cycle de synchronisation AAD suivant après l’exécution de cette étape, les utilisateurs avec le système téléphonique qui ont été précédemment déplacés d’un serveur Skype Entreprise local vers le cloud perdent la possibilité de prendre et de recevoir des appels jusqu’à ce que l’étape 8 soit terminée et confirmée à l’étape 9. En outre, assurez-vous que vous avez enregistré les numéros de téléphone et les informations connexes de l’utilisateur à l’étape 2, car ces informations sont requises pour cette étape.

 
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

7. Attendez la fin de la mise en service de l’utilisateur. Vous pouvez surveiller la progression de l’approvisionnement des utilisateurs en exécutant la commande PowerShell Skype Entreprise Online suivante. La commande PowerShell Skype Entreprise Online suivante renvoie un résultat vide dès que le processus est terminé.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Exécutez la commande PowerShell Skype Entreprise Online suivante pour attribuer des numéros de téléphone et activer les utilisateurs pour le système téléphonique :
     
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
   >  Si vous avez encore des points de terminaison Skype Entreprise (clients Skype ou téléphones tiers), vous devez également définir -HostedVoiceMail sur $true. Si votre organisation utilise uniquement des points de terminaison Teams pour les utilisateurs à reconnaissance vocale, ce paramètre n'est pas applicable à vos utilisateurs. 

9. Confirmez que les utilisateurs ayant la fonctionnalité système téléphonique ont été correctement mis en service. La commande PowerShell Skype Entreprise Online suivante renvoie un résultat vide dès que le processus est terminé.

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

10. Répétez les étapes 3 à 9 jusqu'à ce que tous les utilisateurs soient traitées.

11. Confirmez que tous les utilisateurs ont été correctement traitées en exécutant les deux commandes PowerShell suivantes.

    Commande PowerShell skype entreprise server sur site :

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Commande PowerShell Skype Entreprise Online :

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. Une fois que vous avez effectué toutes les [étapes](decommission-move-on-prem-endpoints.md) de la méthode 2, voir Déplacer des points de terminaison d'application hybride de l'local vers le serveur en ligne et Supprimer votre serveur Skype Entreprise local pour obtenir des [étapes](decommission-remove-on-prem.md) supplémentaires pour supprimer votre déploiement local de Skype Entreprise Server.


## <a name="see-also"></a>Voir aussi

- [Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)

- [Mise hors service de votre environnement Skype pour entreprises sur site](decommission-on-prem-overview.md)

