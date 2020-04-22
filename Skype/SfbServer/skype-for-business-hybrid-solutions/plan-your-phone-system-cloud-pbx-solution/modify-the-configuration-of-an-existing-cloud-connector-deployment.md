---
title: Modifier la configuration d’un déploiement Cloud Connector existant
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
description: Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version de Skype entreprise et du déploiement de la version ultérieure de Skype entreprise.
ms.openlocfilehash: 77e9940e10cc356afbade5592bf41a0cdba66b0f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779380"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modifier la configuration d’un déploiement Cloud Connector existant
 
Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version de Skype entreprise et du déploiement de la version ultérieure de Skype entreprise. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modifier la configuration d’un seul site
<a name="BKMK_SIngleSite"> </a>

S’il n’y a qu’une seule Appliance dans le site, lorsque vous souhaitez modifier les paramètres de configuration après le déploiement de l’appliance, vous pouvez modifier le fichier CloudConnector. ini et relancer le déploiement.
  
1. Exécutez l’applet de commande suivante pour désinstaller toutes les machines virtuelles existantes sur le serveur hôte : 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Exécutez l’applet de commande suivante pour annuler l’inscription de l’appliance :
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Mettez à jour le fichier CloudConnector. ini dans le répertoire de l’appliance.
    
4. Exécutez l’applet de commande suivante pour mettre à jour la configuration : (cette étape s’applique uniquement à la version 2 ; pour les versions antérieures, passez à l’étape suivante.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Exécutez l’applet de commande suivante pour réinscrire l’appliance :
    
   ```powershell
   Register-CcAppliance
   ```

6. Exécutez l’applet de commande suivante pour installer Skype entreprise, version Cloud Connector :
    
   ```powershell
   Install-CcAppliance
   ```

S’il y a plusieurs Appliances dans le site, vous devrez suivre ces étapes, modifier le fichier CloudConnector. ini et redéployer les appliances une par une.
  
1. Exécutez l’applet de commande suivante pour désinstaller toutes les machines virtuelles existantes sur l’appliance actuelle : 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Exécutez l’applet de commande suivante pour annuler l’inscription de l’appliance :
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Mettez à jour le fichier CloudConnector. ini dans le répertoire de l’appliance.
    
4. Exécutez l’applet de commande suivante pour mettre à jour la configuration : (cette étape s’applique uniquement à la version 2 ; pour les versions antérieures, passez à l’étape suivante.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Exécutez l’applet de commande suivante pour réinscrire l’appliance :
    
   ```powershell
   Register-CcAppliance
   ```

6. Exécutez l’applet de commande suivante sur toutes les autres Appliances du site pour récupérer la dernière configuration :
    
   ```powershell
   Publish-CcAppliance
   ```

7. Exécutez l’applet de commande suivante pour redéployer Cloud Connector sur l’appliance actuelle :
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modifier la configuration de plusieurs sites
<a name="BKMK_MultipleSites"> </a>

Pour modifier la configuration de plusieurs sites dans un déploiement, suivez les étapes d’un seul site, mettant à jour un site à la fois.
  
## <a name="modify-the-configuration-of-your-office-365-organization-to-enable-automatic-updates"></a>Modifier la configuration de votre organisation Office 365 pour activer les mises à jour automatiques
<a name="BKMK_MultipleSites"> </a>

Pour activer les mises à jour automatiques du système d’exploitation et les mises à jour automatiques bits, vous devez utiliser le compte d’administrateur client Skype entreprise pour la gestion en ligne et utiliser l’environnement PowerShell distant client comme suit.
  
Si vous avez désactivé les mises à jour automatiques du système d’exploitation ou les mises à jour automatiques bits, votre ordinateur hôte et votre ordinateur virtuel risquent de manquer d’importantes mises à jour Windows, et Cloud Connector ne sera pas mis à niveau automatiquement vers la nouvelle version. Il est vivement recommandé d’activer les mises à jour automatiques.
  
1. La propriété EnableAutoUpdate du site doit être définie sur true (valeur par défaut). Exécutez l’applet de commande suivante pour vous assurer que la valeur de EnableAutoUpdate est true :
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Créer une fenêtre de mise à jour automatique pour le client.
    
    La fenêtre de temps peut être quotidienne, hebdomadaire et mensuelle. Toutes les fenêtres temporelles ont besoin d’une heure de début et d’une durée.
    
   - Pour une fenêtre de temps quotidien, seule l’heure de début et la durée sont nécessaires. 
    
   - Pour une fenêtre de temps hebdomadaire, les jours de la semaine sont nécessaires, ce qui peut être un seul jour ou plusieurs jours.
    
   - Pour une fenêtre de temps mensuelle, il peut y avoir deux types. Le premier type consiste à spécifier le jour du mois, qui peut être un seul jour. Le deuxième type consiste à spécifier les semaines du mois, ainsi que les jours de la semaine, qui peuvent être un ou plusieurs éléments.
    
   - Chaque client peut avoir 20 fenêtres de temps définies. La fenêtre de temps par défaut est créée pour un nouveau client comme fenêtre temporelle par défaut pour la mise à jour du système d’exploitation et la mise à jour bits. Exécutez les cmdlets suivantes pour définir la période quotidienne, hebdomadaire ou mensuelle :
    
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

   - Affectez les fenêtres heure de mise à jour au site. 
    
     Les fenêtres heure de mise à jour bits et heure de mise à jour du système d’exploitation sont configurées séparément. Elles peuvent toutes deux être affectées à une ou plusieurs fenêtres temporelles. Chaque fenêtre de temps peut être affectée à différents sites et à différentes fins (mise à jour bits et mise à jour du système d’exploitation). Exécutez l’applet de commande suivante pour définir la fenêtre de temps pour le site : 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Mettre à jour les informations d’identification d’administrateur client dédié
<a name="BKMK_MultipleSites"> </a>

Les modifications administratives dans l’organisation Office 365 pour Cloud Connector sont effectuées à partir d’un compte disposant des autorisations nécessaires. Dans les versions de Cloud Connector antérieures à 2,0, ce compte est un compte d’administrateur client global dédié. Dans le Cloud Connector versions 2,0 et versions ultérieures, ce compte peut être un compte Office 365 avec des droits d’administrateur de Skype entreprise.
  
Si les informations d’identification de votre compte d’administrateur changent dans Office 365, vous devez également mettre à jour les informations d’identification mises en cache localement dans Cloud Connector en exécutant la commande PowerShell d’administration suivante sur chaque appliance Cloud Connector que vous avez déployée :
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Mettre à jour le mot de passe du serveur hôte
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Cette section s’applique à Cloud Connector version 2,0 et versions ultérieures. 
  
Toutes les informations d’identification Cloud Connector sont stockées dans le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. Xml». Lorsque le mot de passe sur le serveur hôte est modifié, vous devez mettre à jour les informations d’identification stockées localement.
  
Pour mettre à jour les informations d’identification stockées localement sur le matériel de Cloud Connector, utilisez les cmdlets [Get-applet cccredential](get-cccredential.md) et [Set-applet cccredential](set-cccredential.md) et procédez comme suit :
  
1. Exécutez les commandes suivantes pour récupérer les mots de passe dont vous aurez besoin plus tard : 
    
   - Get-applet cccredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-applet cccredential-AccountType VMAdmin-DisplayPassword
    
   - Get-applet cccredential-AccountType CceService-DisplayPassword
    
2. Modifiez le mot de passe de votre compte sur le serveur hôte.
    
3. Redémarrez le serveur hôte.
    
4. Supprimez le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. Xml».
    
5. Lancez une console PowerShell en tant qu’administrateur, puis exécutez la commande « Register-applet ccappliance-local » pour entrer de nouveau les mots de passe à la suite de la description. Veillez à entrer le même mot de passe que celui que vous avez entré auparavant pour le déploiement de Cloud Connector.
    
Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :
  
1. Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :
    
1. Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
2. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.
    
2. Exécutez Set-applet cccredential-AccountType VmAdmin comme suit :
    
1. Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
2. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Mettre à jour le mot de passe du compte CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Cette section s’applique à Cloud Connector version 2.0.1 et versions ultérieures. 
  
Le service Cloud Connector exécute le service de gestion de Cloud Connector. Le compte CceService est créé pendant le déploiement de Cloud Connector Edition et stocké dans les fichiers suivants : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml» et «%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. Xml».
  
Pour vous assurer que toutes les appliances peuvent accéder au partage de l’annuaire de sites, le mot de passe du compte CceService doit être le même sur toutes les appliances déployées dans le site. Gardez les éléments suivants à l’esprit :
  
- Par défaut, le compte CceService est configuré comme « le mot de passe n’expire jamais ». Lorsque vous mettez à jour le mot de passe, Microsoft vous recommande de conserver cette configuration.
    
- Vous devez mettre à jour le mot de passe pendant les périodes d’utilisation non-pics et en dehors des fenêtres de temps de mise à jour automatique pour les mises à jour de bits ou Windows. Lorsque vous mettez à jour le mot de passe, l’appliance doit être vidée et redémarrée, ce qui prend un peu de temps. Le redémarrage de l’appliance interrompt les opérations de mise à jour automatique. 
    
- Lorsque vous modifiez le mot de passe du compte CceService, vous devez spécifier toutes les informations d’identification et les mettre à jour dans le fichier stocké localement. 
    
Pour chaque appliance qui appartient au même site RTC, vous devez spécifier les éléments suivants : 
  
1. Exécutez les commandes suivantes pour récupérer les noms de compte et les mots de passe que vous utiliserez plus tard :
    
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

2. Exécutez la cmdlet Enter-applet ccupdate pour décharger l’appliance et la déplacer en mode de maintenance manuelle.
    
3. Mettez à jour le mot de passe du compte CceService sur le serveur hôte.
    
4. Redémarrez le serveur hôte.
    
5. Exécutez la cmdlet Restore-CcCredentials pour entrer de nouveau les mots de passe à la suite de la description. 
    
    Assurez-vous d’entrer le mot de passe que vous avez entré auparavant pour le déploiement de Cloud Connector, à l’exception du compte CceService. Pour le compte CceService, entrez votre nouveau mot de passe. Assurez-vous que le nouveau mot de passe du compte CceService est le même pour toutes les appliances dans le site RTC.
    
6. Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l’étape 1 sont différents, vous devez effectuer les étapes suivantes :
    
7. Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :
    
   - Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
   - Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.
    
8. Exécutez Set-applet cccredential-AccountType VmAdmin comme suit :
    
   - Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.
    
   - Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1. 
    
9. Exécutez la cmdlet Exit-applet ccupdate pour déplacer l’appliance en mode de maintenance manuelle.
    
10. Après avoir effectué ces étapes sur toutes les appliances du même site RTC, supprimez les fichiers suivants dans le répertoire racine du site :
    
    - CcLockFile
    
    - Nom\<de domaine complet du pool Sip externe Site_ Edge\>
    
    - Nom\<de domaine complet du pool Sip externe Tenant_ Edge\>
    
    - Nom\<de domaine complet du pool Sip externe TenantConfigLock_ Edge\>
    
## <a name="add-a-new-sip-domain"></a>Ajouter un nouveau domaine SIP
<a name="BKMK_UpdatePassword"> </a>

Pour ajouter un nouveau domaine SIP (ou plusieurs domaines SIP) à votre déploiement Cloud Connector existant, procédez comme suit :
  
1. Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la configuration de votre domaine dans Office 365, consultez la rubrique [Ajouter un domaine à office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Mettez à jour le fichier de configuration de Cloud Connector avec le ou les nouveaux domaines SIP.
    
3. Demandez un nouveau certificat externe de serveur Edge avec des noms SAN supplémentaires pour SIP. domain pour chaque domaine SIP défini dans la configuration de Cloud Connector. 
    
4. Définissez le chemin d’accès pour le nouveau certificat externe de serveur Edge comme suit :
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Suivez les instructions pour [modifier la configuration d’un seul site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [modifier la configuration de plusieurs sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modifier le domaine SIP principal
<a name="BKMK_UpdatePassword"> </a>

Si vous devez modifier le domaine SIP principal dans votre déploiement de Cloud Connector, procédez comme suit :
  
1. Assurez-vous que vous avez effectué les étapes de mise à jour de votre domaine dans Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la configuration de votre domaine dans Office 365, consultez la rubrique [Ajouter un domaine à office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Mettez à jour le fichier de configuration de Cloud Connector avec le nouveau domaine SIP.
    
3. Demandez un nouveau certificat externe de serveur Edge avec des noms SAN supplémentaires pour SIP. domain pour chaque domaine SIP défini dans la configuration de Cloud Connector. 
    
4. Définissez le chemin d’accès pour le nouveau certificat externe de serveur Edge comme suit :
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Supprimez l’inscription du client pour chaque appliance dans un site en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Supprimez l’inscription de site pour chaque site en exécutant l’applet de commande suivante dans Skype entreprise Online PowerShell :
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Désinstallez chaque appliance en exécutant l’applet de commande suivante dans la session PowerShell d’administrateur sur Cloud Connector :
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Enregistrez chaque appliance en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installez chaque appliance, une par une, en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur Cloud Connector :
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Remplacer le certificat de serveur Edge externe par un nouveau certificat
<a name="BKMK_UpdatePassword"> </a>

Lorsque vous devez remplacer le certificat de serveur Edge externe sur vos appareils Cloud Connector, vous devez obtenir un nouveau certificat de serveur Edge, préparer le fichier PFX contenant la clé privée et la chaîne de certificats complète, puis effectuer les opérations suivantes sur chaque appliance :
  
1. Placez l’appliance en mode maintenance à l’aide de la cmdlet Enter-applet ccupdate.
    
2. Exécutez la commande suivante : 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Si le mot de passe du nouveau certificat est le même que l’ancien, l’importation réussit. Si le mot de passe est différent, vous recevrez un message d’erreur indiquant que le mot de passe est incorrect, et vous devrez réinitialiser le mot de passe en exécutant la cmdlet Register-applet ccappliance avec le paramètre-local, puis en répétant l’étape 2. 
    
4. Désactivez l’appliance en mode maintenance à l’aide de la cmdlet Exit-applet ccupdate.
    

