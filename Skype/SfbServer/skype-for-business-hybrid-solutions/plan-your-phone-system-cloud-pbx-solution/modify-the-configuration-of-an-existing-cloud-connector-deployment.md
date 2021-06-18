---
title: Modifier la configuration d’un déploiement de Cloud Connector existant
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Suivez les étapes de cette rubrique pour modifier la configuration d’un déploiement existant de Skype Entreprise, version Cloud Connector 1.4.1 ou ultérieure.
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109170"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modifier la configuration d’un déploiement de Cloud Connector existant

> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Suivez les étapes de cette rubrique pour modifier la configuration d’un déploiement existant de Skype Entreprise, version Cloud Connector 1.4.1 ou ultérieure. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modifier la configuration d’un site unique
<a name="BKMK_SIngleSite"> </a>

S’il n’existe qu’une seule appliance dans le site, lorsque vous souhaitez modifier les paramètres de configuration après le déploiement de l’appliance, vous pouvez modifier le fichier CloudConnector.ini et recommencer le déploiement.
  
1. Exécutez l’cmdlet suivante pour désinstaller toutes les machines virtuelles existantes sur le serveur hôte : 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Exécutez l’cmdlet suivante pour désinsser l’appliance :
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Mettez à jour CloudConnector.ini fichier dans l’annuaire d’équipements.
    
4. Exécutez l’cmdlet suivante pour mettre à jour la configuration : (Cette étape s’applique uniquement à la version 2 ; pour les versions précédentes, passez à l’étape suivante.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Exécutez l’cmdlet suivante pour inscrire à nouveau l’appliance :
    
   ```powershell
   Register-CcAppliance
   ```

6. Exécutez l’cmdlet suivante pour installer Skype Entreprise, version Cloud Connector :
    
   ```powershell
   Install-CcAppliance
   ```

S’il existe plusieurs appliances dans le site, vous devez suivre ces étapes, modifier le fichier CloudConnector.ini et redéployer les appliances une par une.
  
1. Exécutez l’cmdlet suivante pour désinstaller toutes les machines virtuelles existantes sur l’appliance actuelle : 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Exécutez l’cmdlet suivante pour désinsser l’appliance :
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Mettez à jour CloudConnector.ini fichier dans l’annuaire d’équipements.
    
4. Exécutez l’cmdlet suivante pour mettre à jour la configuration : (Cette étape s’applique uniquement à la version 2 ; pour les versions précédentes, passez à l’étape suivante.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Exécutez l’cmdlet suivante pour inscrire à nouveau l’appliance :
    
   ```powershell
   Register-CcAppliance
   ```

6. Exécutez l’cmdlet suivante sur toutes les autres appliances du site pour récupérer la dernière configuration :
    
   ```powershell
   Publish-CcAppliance
   ```

7. Exécutez l’cmdlet suivante pour redéployer Cloud Connector sur l’appliance actuelle :
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modifier la configuration de plusieurs sites
<a name="BKMK_MultipleSites"> </a>

Pour modifier la configuration de plusieurs sites dans un déploiement, suivez les étapes pour un site unique, en mettant à jour un site à la fois.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Modifier la configuration de votre organisation Microsoft 365 ou Office 365 pour activer les mises à jour automatiques
<a name="BKMK_MultipleSites"> </a>

Pour activer les mises à jour automatiques du système d’exploitation et les mises à jour automatiques des bits, vous devez utiliser le compte d’administrateur client Skype Entreprise pour la gestion en ligne et utiliser powerShell à distance client comme suit.
  
Si vous avez désactivé les mises à jour automatiques du système d’exploitation ou les mises à jour automatiques bits, votre ordinateur hôte et votre ordinateur virtuel risquent de manquer des mises à jour Windows importantes et Cloud Connector ne sera pas mis à niveau automatiquement vers la nouvelle version. Il est vivement recommandé d’activer les mises à jour automatiques.
  
1. La propriété EnableAutoUpdate du site doit être définie sur true (valeur par défaut). Exécutez l’cmdlet suivante pour vous assurer que EnableAutoUpdate est définie sur true :
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Créez une fenêtre de temps de mise à jour automatique pour le client.
    
    La fenêtre horaire peut être quotidienne, hebdomadaire et mensuelle. Toutes les fenêtres de temps ont besoin d’une heure de début et d’une durée.
    
   - Pour une fenêtre de temps quotidienne, seules l’heure de début et la durée sont nécessaires. 
    
   - Pour une période hebdomadaire, les jours de la semaine sont nécessaires, qui peuvent être un seul jour ou plusieurs jours.
    
   - Pour une période mensuelle, il peut y avoir deux types. Le premier type consiste à spécifier le jour du mois, qui peut être un seul jour. Le deuxième type consiste à spécifier les semaines du mois, ainsi que les jours de la semaine, qui peuvent être un ou plusieurs éléments.
    
   - Chaque client peut avoir 20 fenêtres de temps définies. La fenêtre de temps par défaut est créée pour un nouveau client comme fenêtre de temps par défaut pour la mise à jour du système d’exploitation et la mise à jour des bits. Exécutez la ou les cmdlet suivantes pour définir la période quotidienne, hebdomadaire ou mensuelle :
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Attribuez des fenêtres d’heure de mise à jour au site. 
    
     Les fenêtres d’heure de mise à jour des bits et de mise à jour du système d’exploitation sont configurées séparément. Ces deux fenêtres peuvent être affectées à une ou plusieurs fenêtres de temps. Chaque fenêtre de temps peut être affectée à différents sites et à un objectif différent (mise à jour bits et mise à jour du système d’exploitation). Exécutez l’cmdlet suivante pour définir la fenêtre d’heure du site : 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Mettre à jour les informations d’identification de l’administrateur client dédié
<a name="BKMK_MultipleSites"> </a>

Les modifications administratives apportées dans l’organisation Microsoft 365 ou Office 365 pour Cloud Connector sont apportées à partir d’un compte avec les autorisations nécessaires. Dans les versions de Cloud Connector antérieures à la version 2.0, ce compte est un compte d’administrateur client global dédié. Dans les versions 2.0 et ultérieures de Cloud Connector, ce compte peut être un compte Microsoft 365 ou Office 365 avec des droits d’administrateur Skype Entreprise.
  
Si les informations d’identification de votre compte d’administrateur changent dans Microsoft 365 ou Office 365, vous devez également mettre à jour les informations d’identification mises en cache localement dans Cloud Connector en exécutant la commande Administrateur PowerShell suivante sur chaque appliance Cloud Connector que vous avez déployée :
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Mettre à jour le mot de passe du serveur hôte
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Cette section s’applique aux versions 2.0 et ultérieures de Cloud Connector. 
  
Toutes les informations d’identification Cloud Connector sont stockées dans le fichier suivant : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml ». Lorsque le mot de passe du serveur hôte change, vous devez mettre à jour les informations d’identification stockées localement.
  
Pour mettre à jour les informations d’identification stockées localement sur l’appliance Cloud Connector, utilisez les cmdlets [Get-CcCredential](get-cccredential.md) et [Set-CcCredential](set-cccredential.md) et suivez les étapes suivantes :
  
1. Exécutez les commandes suivantes pour récupérer les mots de passe dont vous aurez besoin ultérieurement : 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Modifiez le mot de passe de votre compte sur le serveur hôte.
    
3. Redémarrez le serveur hôte.
    
4. Supprimez le fichier suivant : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml ».
    
5. Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance -Local » pour entrer à nouveau les mots de passe suivant la description. Veillez à entrer le mot de passe que vous avez entré auparavant pour le déploiement Cloud Connector.
    
Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :
  
1. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
1. Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
2. Lorsque vous y invitez les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.
    
2. Exécutez Set-CcCredential -AccountType VmAdmin comme suit :
    
1. Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
2. Lorsque vous y invitez les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Mettre à jour le mot de passe du compte CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Cette section s’applique aux versions 2.0.1 et ultérieures de Cloud Connector. 
  
Le service Cloud Connector exécute le service de gestion Cloud Connector. Le compte CceService est créé lors du déploiement de Cloud Connector Edition et stocké dans les fichiers suivants : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml » et « %SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml ».
  
Pour vous assurer que toutes les appliances peuvent accéder au partage d’annuaire de sites, le mot de passe du compte CceService doit être le même sur toutes les appliances déployées sur le site. Gardez les éléments suivants à l’esprit :
  
- Par défaut, le compte CceService est configuré comme « Le mot de passe n’expire jamais ». Lorsque vous mettez à jour le mot de passe, Microsoft recommande de conserver cette configuration.
    
- Vous devez mettre à jour le mot de passe pendant les périodes d’utilisation en dehors des périodes de pointe et en dehors des fenêtres d’heure de mise à jour automatique pour les bits ou les mises à jour Windows. Lorsque vous mettez à jour le mot de passe, l’appliance doit être drainée et redémarré, ce qui prend un certain temps. Le redémarrage de l’appliance interrompra les opérations de mise à jour automatique. 
    
- Lorsque vous modifiez le mot de passe du compte CceService, vous devez spécifier toutes les informations d’identification et les mettre à jour dans le fichier stocké localement. 
    
Pour chaque appliance qui appartient au même site PSTN, vous devez spécifier les spécifications suivantes : 
  
1. Exécutez les commandes suivantes pour récupérer les noms de compte et les mots de passe que vous utiliserez ultérieurement :
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. Exécutez lEnter-CcUpdate cmdlet pour vider l’appliance et la déplacer en mode de maintenance manuelle.
    
3. Mettez à jour le mot de passe du compte CceService sur le serveur hôte.
    
4. Redémarrez le serveur hôte.
    
5. Exécutez lRestore-CcCredentials cmdlet pour entrer à nouveau les mots de passe suivant la description. 
    
    Veillez à entrer le mot de passe que vous avez entré auparavant pour le déploiement Cloud Connector, à l’exception du compte CceService. Pour le compte CceService, entrez votre nouveau mot de passe. Assurez-vous que le nouveau mot de passe du compte CceService est identique pour toutes les appliances du site PSTN.
    
6. Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :
    
7. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
   - Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
   - Lorsque vous y invitez les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.
    
8. Exécutez Set-CcCredential -AccountType VmAdmin comme suit :
    
   - Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
   - Lorsque vous y invitez les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1. 
    
9. Exécutez lExit-CcUpdate cmdlet pour sortir l’appliance du mode de maintenance manuelle.
    
10. Une fois ces étapes terminées sur toutes les appliances du même site PSTN, supprimez les fichiers suivants dans l’annuaire racine du site :
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Ajouter un nouveau domaine SIP
<a name="BKMK_UpdatePassword"> </a>

Pour ajouter un nouveau domaine SIP (ou plusieurs domaines SIP) à votre déploiement Cloud Connector existant, vous pouvez :
  
1. Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la façon de configurer votre domaine dans Microsoft 365 ou Office 365, voir Ajouter un domaine à [Microsoft 365 ou Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Mettez à jour le fichier de configuration Cloud Connector avec le ou les nouveaux domaines SIP.
    
3. Demandez un nouveau certificat externe Edge avec des noms SAN supplémentaires pour sip.domain pour chaque domaine SIP défini dans votre configuration Cloud Connector. 
    
4. Définissez le chemin d’accès du nouveau certificat externe Edge comme suit :
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Suivez les instructions pour [modifier la configuration d’un site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) unique ou modifier la configuration de plusieurs [sites.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>Modifier le domaine SIP principal
<a name="BKMK_UpdatePassword"> </a>

Si vous devez modifier le domaine SIP principal dans votre déploiement Cloud Connector, faites les choses suivantes :
  
1. Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Microsoft 365 ou Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la façon de configurer votre domaine dans Microsoft 365 ou Office 365, voir Ajouter un domaine à [Microsoft 365 ou Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Mettez à jour le fichier de configuration Cloud Connector avec le nouveau domaine SIP.
    
3. Demandez un nouveau certificat externe Edge avec des noms SAN supplémentaires pour sip.domain pour chaque domaine SIP défini dans votre configuration Cloud Connector. 
    
4. Définissez le chemin d’accès du nouveau certificat externe Edge comme suit :
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Supprimez l’inscription du client pour chaque appliance d’un site en exécutant l’cmdlet suivante dans l’administrateur PowerShell sur Cloud Connector :
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Supprimez l’inscription de site pour chaque site en exécutant l’cmdlet suivante dans Skype Entreprise Online PowerShell :
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Désinstallez chaque appliance en exécutant l’cmdlet suivante dans l’administrateur PowerShell sur Cloud Connector :
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Inscrivez chaque appliance en exécutant l’cmdlet suivante dans l’administrateur PowerShell sur Cloud Connector :
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installez chaque appliance, une par une, en exécutant l’cmdlet suivante dans l’administrateur PowerShell sur Cloud Connector :
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Remplacer le certificat Edge externe par un nouveau certificat
<a name="BKMK_UpdatePassword"> </a>

Lorsque vous devez remplacer le certificat Edge externe sur vos appliances Cloud Connector, vous devez obtenir un nouveau certificat Edge, préparer le fichier PFX contenant la clé privée et la chaîne de certificats complète, puis faire les opérations suivantes sur chaque appliance :
  
1. Placez l’appliance en mode maintenance à l’aide Enter-CcUpdate cmdlet.
    
2. Exécutez la commande suivante : 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Si le mot de passe du nouveau certificat est identique à l’ancien, l’importation réussit. Si le mot de passe est différent, vous recevrez une erreur vous faisant part d’une erreur, et vous devrez réinitialiser le mot de passe en exécutant la cmdlet Register-CcAppliance avec le paramètre -Local, puis en répétant l’étape 2. 
    
4. Sortir l’appliance du mode maintenance à l’aide de la cmdlet Exit -CcUpdate.
