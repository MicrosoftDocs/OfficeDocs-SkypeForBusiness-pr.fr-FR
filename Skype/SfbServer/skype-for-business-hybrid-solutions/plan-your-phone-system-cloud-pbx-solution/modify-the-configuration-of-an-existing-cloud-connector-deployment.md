---
title: Modifier la configuration d'un déploiement Cloud Connector existant
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version actuelle de Skype entreprise Cloud Connector, ou d’une version ultérieure.
ms.openlocfilehash: 7e46d614a5aaf3c34d9401e2ec53ba72e8adba71
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287047"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modify the configuration of an existing Cloud Connector deployment
 
Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’une version actuelle de Skype entreprise Cloud Connector, ou d’une version ultérieure. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modifier la configuration d'un seul site
<a name="BKMK_SIngleSite"> </a>

Si le site ne comporte qu'une seule appliance, lorsque vous souhaitez modifier les paramètres de configuration une fois l'appliance déployée, vous pouvez modifier le fichier CloudConnector.ini et recommencer le déploiement.
  
1. Exécutez l'applet de commande suivante pour désinstaller tous les ordinateurs virtuels existants sur le serveur hôte : 
    
   ```
   Uninstall-CcAppliance
   ```

2. Exécutez l’applet de commande suivante pour annuler l’inscription de l'appliance :
    
   ```
   Unregister-CcAppliance
   ```

3. Mettez le fichier CloudConnector.ini à jour dans l'annuaire d'appliances.
    
4. Exécutez l’applet de commande suivante pour mettre à jour la configuration: (cette étape s’applique uniquement à la version 2; pour les versions précédentes, passez à l’étape suivante.)
    
   ```
   Import-CcConfiguration 
   ```

5. Exécutez l’applet de commande suivante pour inscrire de nouveau l'appliance :
    
   ```
   Register-CcAppliance
   ```

6. Exécutez l’applet de commande suivante pour installer Skype Entreprise, version Cloud Connector :
    
   ```
   Install-CcAppliance
   ```

Si le site comporte plusieurs appliances, vous devez suivre ces étapes, modifier le fichier CloudConnector.ini et redéployer les appliances une par une.
  
1. Exécutez l’applet de commande suivante pour désinstaller toutes les machines virtuelles existantes sur le matériel actuel: 
    
   ```
   Uninstall-CcAppliance
   ```

2. Exécutez l’applet de commande suivante pour annuler l’inscription de l'appliance :
    
   ```
   Unregister-CcAppliance
   ```

3. Mettez le fichier CloudConnector.ini à jour dans l'annuaire d'appliances.
    
4. Exécutez l’applet de commande suivante pour mettre à jour la configuration: (cette étape s’applique uniquement à la version 2; pour les versions précédentes, passez à l’étape suivante.)
    
   ```
   Import-CcConfiguration 
   ```

5. Exécutez l’applet de commande suivante pour inscrire de nouveau l'appliance :
    
   ```
   Register-CcAppliance
   ```

6. Exécutez l’applet de commande suivante sur toutes les autres appliances du site pour récupérer la dernière configuration :
    
   ```
   Publish-CcAppliance
   ```

7. Exécutez l’applet de commande suivante pour redéployer le Cloud Connector sur le matériel actuel:
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modifier la configuration de plusieurs sites
<a name="BKMK_MultipleSites"> </a>

Pour modifier la configuration de plusieurs sites dans un déploiement, suivez les étapes d’un seul site pour mettre à jour un site à la fois.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Modification de la configuration de votre client Office 365 pour activer les mises à jour automatiques
<a name="BKMK_MultipleSites"> </a>

Pour activer les mises à jour automatiques du système d’exploitation et les mises à jour automatiques bits, vous devez utiliser le compte d’administrateur de clients Skype entreprise pour une gestion en ligne et utiliser PowerShell distant client comme suit.
  
Si vous avez désactivé les mises à jour automatiques du système d’exploitation ou les mises à jour automatiques bits, il est possible que votre hôte et votre ordinateur virtuel manquent de nouvelles mises à jour Windows, et que Cloud Connector ne sera pas automatiquement mis à niveau vers la nouvelle version. Il est vivement recommandé de d’activer les mises à jour automatiques.
  
1. La propriété EnableAutoUpdate du site doit être définie sur true (valeur par défaut). Exécutez l’applet de commande suivante pour vous assurer que EnableAutoUpdate est définie sur True :
    
   ```
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Créez une fenêtre temporelle de mise à jour automatique pour le client.
    
    Cette fenêtre temporelle peut être quotidienne, hebdomadaire et mensuelle. Toutes les fenêtres temporelles doivent comporter une heure de début et une durée.
    
   - Pour une fenêtre temporelle quotidienne, seules l'heure de début et la durée sont nécessaires. 
    
   - Pour une fenêtre temporelle hebdomadaire, les jours de la semaine sont nécessaires, et il peut d'agir d'un seul jour ou de plusieurs jours.
    
   - Les fenêtres temporelles mensuelles peuvent être de deux types. Le premier consiste à spécifier le jour du mois, et il peut s'agir d'un seul jour. Le second consiste à spécifier les semaines du mois, ainsi que les jours de la semaine, et il peut s'agir d'une seule semaine ou d'un seul jour ou de plusieurs.
    
   - Chaque client peut disposer de 20 fenêtres temporelles définies. La fenêtre temporelle par défaut est créée pour un nouveau client comme fenêtre temporelle par défaut pour la mise à jour du système d’exploitation et de Bits. Exécutez l’applet ou les applets de commande suivantes pour définir une fenêtre temporelle quotidienne, hebdomadaire ou mensuelle :
    
   ```
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Attribuez des heures de mise à jour à votre site. 
    
     Les fenêtres temporelles de mises à jour d'OS et de Bits sont configurées séparément. OS et Bits peuvent recevoir une seule fenêtre temporelle ou plusieurs. Chaque fenêtre temporelle peut être affectée à différents sites et pour différents objectifs (mise à jour de Bits et d'OS). Exécutez l’applet de commande suivante pour définir la fenêtre délai pour le site: 
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Mettre à jour les informations d’identification d’administrateur de clients dédiées
<a name="BKMK_MultipleSites"> </a>

Les modifications d’administration apportées au client 365 pour le Cloud Connector sont effectuées à partir d’un compte disposant des autorisations nécessaires. Dans les versions Cloud Connector antérieures à 2,0, ce compte est un compte d’administrateur de clients global dédié. Dans Cloud Connector versions 2,0 et ultérieures, ce compte peut être un compte Office 365 avec des droits d’administrateur Skype entreprise.
  
Si les informations d’identification de votre compte d’administrateur sont modifiées dans Office 365, vous devez également mettre à jour les informations d’identification mises en cache localement dans Cloud Connector en exécutant la commande PowerShell d’administration suivante sur chacun des appareils Cloud Connector:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Mettre à jour le mot de passe du serveur hôte
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Cette section s’applique à la version 2,0 et les versions ultérieures du connecteur Cloud. 
  
Les informations d’identification de tous les connecteurs Cloud sont stockées dans le fichier suivant: «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Lorsque le mot de passe du serveur hôte change, vous devrez mettre à jour les informations d’identification stockées localement.
  
Pour mettre à jour les informations d’identification stockées localement sur le périphérique Cloud Connector, utilisez les applets de connexion [Get-CcCredential](get-cccredential.md) et [Set-CcCredential](set-cccredential.md) , et procédez comme suit:
  
1. Pour récupérer les mots de passe dont vous aurez besoin plus tard, exécutez les commandes suivantes: 
    
   - Get-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType CceService-DisplayPassword
    
2. Modifiez le mot de passe de votre compte sur le serveur hôte.
    
3. Redémarrez le serveur hôte.
    
4. Supprimez le fichier suivant: «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
5. Lancez une console PowerShell en tant qu’administrateur, puis exécutez «Register-CcAppliance-local» pour entrer de nouveau le mot de passe suivi de la description. Assurez-vous d’entrer le mot de passe que vous avez entré auparavant pour le déploiement Cloud Connector.
    
Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si le mot de passe DomainAdmin, VMAdmin et CceService renvoyé à l’étape 1 est différent, vous devez effectuer les étapes suivantes:
  
1. Exécutez Set-CcCredential-AccountType DomainAdmin comme suit:
    
1. Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.
    
2. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.
    
2. Exécutez Set-CcCredential-AccountType VmAdmin comme suit:
    
1. Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.
    
2. Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Mettez à jour le mot de passe du compte CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Cette section s’applique à Cloud Connector version 2.0.1 et versions ultérieures. 
  
Le service Cloud Connector exécute le service de gestion de connecteurs Cloud. Le compte CceService est créé lors du déploiement de l’édition Cloud Connector et est stocké dans les fichiers suivants: «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "et"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. Xml».
  
Pour vous assurer que tous les appareils peuvent accéder au partage de l’annuaire de sites, le mot de passe du compte CceService doit être le même sur tous les appareils déployés dans le site. Tenez compte des points suivants :
  
- Par défaut, le compte CceService est configuré comme «le mot de passe n’expire jamais». Lorsque vous mettez à jour le mot de passe, Microsoft vous recommande de le protéger.
    
- Vous devez mettre à jour le mot de passe pendant les périodes d’utilisation sans pointe et en dehors des mises à jour automatiques de Windows pour les bits ou les mises à jour Windows. Lorsque vous mettez à jour le mot de passe, l’application doit être vidée et redémarrée, ce qui prend du temps. Le redémarrage de l’application interrompt les opérations de mise à jour automatique. 
    
- Lorsque vous modifiez le mot de passe du compte CceService, vous devez spécifier toutes les informations d’identification et les mettre à jour dans le fichier stocké localement. 
    
Pour chaque appareil qui appartient au même site RTC, vous devez spécifier les éléments suivants: 
  
1. Pour récupérer les noms de compte et mots de passe que vous utiliserez plus tard, exécutez les commandes suivantes:
    
   ```
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

2. Exécutez l’applet de conduite Enter-CcUpdate pour décharger l’appareil et le déplacer vers le mode de maintenance manuelle.
    
3. Mettez à jour le mot de passe du compte CceService sur le serveur hôte.
    
4. Redémarrez le serveur hôte.
    
5. Exécutez l’applet de commande Restore-CcCredentials pour entrer de nouveau le mot de passe suivant la description. 
    
    Assurez-vous d’entrer le mot de passe que vous avez entré précédemment pour le déploiement du Cloud Connector, sauf pour le compte CceService. Pour le compte CceService, entrez votre nouveau mot de passe. Vérifiez que le nouveau mot de passe du compte CceService est le même pour tous les appareils du site PSTN.
    
6. Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si le mot de passe DomainAdmin, VMAdmin et CceService renvoyé à l’étape 1 est différent, vous devez effectuer les étapes suivantes:
    
7. Exécutez Set-CcCredential-AccountType DomainAdmin comme suit:
    
   - Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.
    
   - Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin renvoyé à l’étape 1.
    
8. Exécutez Set-CcCredential-AccountType VmAdmin comme suit:
    
   - Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.
    
   - Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin renvoyé à l’étape 1. 
    
9. Exécutez l’applet de connexion Exit-CcUpdate pour éloigner l’application du mode de maintenance manuelle.
    
10. Après avoir effectué ces étapes sur tous les appareils du même site RTC, supprimez les fichiers suivants dans le répertoire racine du site:
    
    - CcLockFile
    
    - FQDN\<du pool SIP externe Site_ Edge\>
    
    - FQDN\<du pool SIP externe Tenant_ Edge\>
    
    - FQDN\<du pool SIP externe TenantConfigLock_ Edge\>
    
## <a name="add-a-new-sip-domain"></a>Ajouter un nouveau domaine SIP
<a name="BKMK_UpdatePassword"> </a>

Pour ajouter un nouveau domaine SIP (ou plusieurs domaines SIP) à votre déploiement Cloud Cloud actuel, procédez comme suit:
  
1. Vérifiez que vous avez terminé les étapes de mise à jour de votre domaine dans Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la configuration de votre domaine dans Office 365, voir [Ajouter un domaine à office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Mettez à jour le fichier de configuration du connecteur Cloud avec le nouveau domaine ou domaines SIP.
    
3. Demandez un nouveau certificat externe avec des noms de réseau SIP supplémentaires pour SIP. domain pour chaque domaine SIP défini dans votre configuration Cloud Connector. 
    
4. Définissez le chemin pour le nouveau certificat externe du périmètre comme suit:
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Suivez les instructions pour [modifier la configuration d’un site unique](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou pour [modifier la configuration de plusieurs sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modifier le domaine SIP principal
<a name="BKMK_UpdatePassword"> </a>

Si vous devez modifier le domaine SIP principal dans votre déploiement Cloud Connector, procédez comme suit:
  
1. Vérifiez que vous avez terminé les étapes de mise à jour de votre domaine dans Office 365 et que vous avez la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la configuration de votre domaine dans Office 365, voir [Ajouter un domaine à office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Mettez à jour le fichier de configuration du connecteur Cloud avec le nouveau domaine SIP.
    
3. Demandez un nouveau certificat externe avec des noms de réseau SIP supplémentaires pour SIP. domain pour chaque domaine SIP défini dans votre configuration Cloud Connector. 
    
4. Définissez le chemin pour le nouveau certificat externe du périmètre comme suit:
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Supprimez l’inscription de locataire pour chaque application dans un site en exécutant l’applet de commande suivante dans PowerShell PowerShell sur le Cloud Connector:
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    Supprimez l’inscription de site pour chaque site en exécutant l’applet de commande suivante dans Skype entreprise Online PowerShell:
    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Désinstallez chaque application en exécutant l’applet de commande suivante dans PowerShell PowerShell dans Cloud Connector:
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     Enregistrez chaque application en exécutant l’applet de commande suivante dans PowerShell PowerShell dans Cloud Connector:
    
   ```
   Register-ccAppliance
   ```

9. 
    
     Installez chaque application, une par une, en exécutant l’applet de commande suivante dans PowerShell PowerShell sur le Cloud Connector:
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Remplacer le certificat de bord externe par un nouveau certificat
<a name="BKMK_UpdatePassword"> </a>

Lorsque vous avez besoin de remplacer le certificat de frontière externe sur vos appareils Cloud Connector, vous devez obtenir un nouveau certificat de bord, préparer le fichier PFX contenant la clé privée et la chaîne de certificats complète, puis effectuer les opérations suivantes sur chaque application:
  
1. Placez l’application en mode de maintenance à l’aide de l’applet de passe Enter-CcUpdate.
    
2. Exécutez la commande suivante : 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Si le mot de passe du nouveau certificat est identique à l’ancien, l’importation est réussie. Si le mot de passe est différent, vous recevez un message d’erreur indiquant que le mot de passe est incorrect, et vous devez réinitialiser le mot de passe en exécutant l’applet de passe Register-CcAppliance à l’aide du paramètre-local, puis répéter l’étape 2. 
    
4. Emportez l’application en mode de maintenance à l’aide de l’applet de connexion Exit-CcUpdate.
    

