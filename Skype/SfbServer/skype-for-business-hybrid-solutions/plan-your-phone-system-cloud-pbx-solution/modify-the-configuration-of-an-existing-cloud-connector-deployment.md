---
title: Modifier la configuration d'un déploiement Cloud Connector existant
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’un Skype existant pour le nuage connecteur Édition 1.4.1 ou déploiement ultérieur.
ms.openlocfilehash: be3c7cbbc1395000dbb84bab0c9be0a866fb4403
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375371"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modifier la configuration d'un déploiement Cloud Connector existant
 
Suivez les étapes décrites dans cette rubrique pour modifier la configuration d’un Skype existant pour le nuage connecteur Édition 1.4.1 ou déploiement ultérieur. 
  
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
    
4. Exécutez la cmdlet suivante pour mettre à jour la configuration : (cette étape n’est applicable que pour la version 2 ; pour les versions antérieures, passez à l’étape suivante).
    
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
  
1. Exécutez l’applet de commande suivante pour désinstaller tous les ordinateurs virtuels existants dans l’application en cours : 
    
   ```
   Uninstall-CcAppliance
   ```

2. Exécutez l’applet de commande suivante pour annuler l’inscription de l'appliance :
    
   ```
   Unregister-CcAppliance
   ```

3. Mettez le fichier CloudConnector.ini à jour dans l'annuaire d'appliances.
    
4. Exécutez la cmdlet suivante pour mettre à jour la configuration : (cette étape n’est applicable que pour la version 2 ; pour les versions antérieures, passez à l’étape suivante).
    
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

7. Exécutez l’applet de commande suivante pour redéployer nuage connecteur sur le matériel en cours :
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modifier la configuration de plusieurs sites
<a name="BKMK_MultipleSites"> </a>

Pour modifier la configuration pour plusieurs sites dans un déploiement, suivez les étapes d’un seul site, mise à jour d’un site à la fois.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Modifier la configuration de votre client Office 365 pour activer les mises à jour automatiques
<a name="BKMK_MultipleSites"> </a>

Pour activer les mises à jour automatiques du système d’exploitation et les mises à jour automatiques de Bits, vous devez utiliser le Skype pour le compte d’administrateur client Business pour la gestion en ligne et l’utilisation de PowerShell à distance des clients comme suit.
  
Si vous avez désactivé les mises à jour automatiques du système d’exploitation ou des mises à jour automatiques des fichiers binaires, votre hôte et la machine virtuelle peuvent manquer des mises à jour importantes et nuage connecteur ne seront pas modifiés automatiquement vers la nouvelle version. Il est vivement recommandé de d’activer les mises à jour automatiques.
  
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

   - Affecter des périodes de mise à jour sur le site. 
    
     Les fenêtres temporelles de mises à jour d'OS et de Bits sont configurées séparément. OS et Bits peuvent recevoir une seule fenêtre temporelle ou plusieurs. Chaque fenêtre temporelle peut être affectée à différents sites et pour différents objectifs (mise à jour de Bits et d'OS). Exécutez l’applet de commande suivante pour définir la fenêtre de temps pour le site : 
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Mettre à jour les informations d'identification d'administrateur client dédié 
<a name="BKMK_MultipleSites"> </a>

Modifications d’administration dans le client Office 365 pour le connecteur sur le nuage sont effectuées à partir d’un compte disposant des autorisations requises. Dans les versions antérieures nuage connecteur 2.0, ce compte est un compte d’administrateur client globale dédié. Dans le nuage connecteur 2.0 et versions ultérieures, ce compte peut être un compte Office 365 avec Skype pour des droits d’administrateur d’entreprise.
  
Si vos informations d’identification du compte d’administration changent dans Office 365, vous devez également mettre à jour les informations d’identification mises en cache localement dans le nuage connecteur en exécutant la commande administrateur PowerShell suivante sur chaque appliance nuage connecteur que vous avez déployé :
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Mettre à jour le mot de passe pour le serveur hôte 
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Cette section est applicable à la version en nuage connecteur 2.0 et versions ultérieures. 
  
Toutes les informations d’identification sur le nuage connecteur sont stockées dans le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ». Lorsque le mot de passe sur le serveur hôte change, vous devrez mettre à jour les informations d’identification stockées localement.
  
Pour mettre à jour les informations d’identification stockées localement sur le matériel de nuage connecteur, utilisez les applets de commande [Get-CcCredential](get-cccredential.md) et [Set-CcCredential](set-cccredential.md) et procédez comme suit :
  
1. Exécutez les commandes suivantes pour récupérer les mots de passe dont vous aurez besoin plus tard :  
    
   - Get-CcCredential - AccountType DomainAdmin - DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential - AccountType CceService - DisplayPassword
    
2. Modifiez le mot de passe de votre compte sur le serveur hôte.
    
3. Redémarrez le serveur hôte.
    
4. Supprimez le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».
    
5. Lancer une console PowerShell en tant qu’administrateur et exécutez « Register-CcAppliance-Local » à entrer les mots de passe suivant la description. Assurez-vous que vous entrez le même mot de que passe avant le déploiement dans le nuage connecteur.
    
Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l'étape 1 sont différents, suivez les étapes suivantes :
  
1. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
1. Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService.
    
2. Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe DomainAdmin renvoyé à l'étape 1.
    
2. Exécutez Set-CcCredential -AccountType VmAdmin comme suit :
    
1. Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService.
    
2. Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe VmAdmin renvoyé à l'étape 1.  
    
## <a name="update-the-password-for-the-cceservice-account"></a>Mettre à jour le mot de passe pour le compte CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Cette section est applicable à la version en nuage connecteur 2.0.1 et versions ultérieures. 
  
Le service de nuage connecteur s’exécute le service de gestion du connecteur sur le nuage. Le compte CceService est créé au cours du déploiement en nuage connecteur Edition et stocké dans les fichiers suivants : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml » et « % SystemDrive%\Programdata\Cloudconnector\credentials... CceService.xml ».
  
Pour vous assurer que tous les appareils peuvent accéder au partage de répertoire de site, le mot de passe pour le compte CceService doit être identiques sur tous les appareils déployés au sein du site. Tenez compte des points suivants :
  
- Par défaut, le compte CceService est configuré comme « Le mot de passe n’expire jamais ». Lorsque vous mettez à jour le mot de passe, Microsoft recommande de cette configuration.
    
- Vous devez mettre à jour le mot de passe pendant les périodes d’utilisation de pointe et en dehors des périodes de mise à jour automatique pour les mises à jour de Windows ou de bits. Lorsque vous mettez à jour le mot de passe, l’appliance doit être drainés et redémarré, qui prend un certain temps. Redémarrage de l’appliance interrompt les opérations de mise à jour automatique. 
    
- Lorsque vous modifiez le mot de passe du compte CceService, vous devez spécifier les informations d’identification et les mettre à jour dans le fichier stocké localement. 
    
Pour chaque application qui appartient au même site PSTN, vous devez spécifier les éléments suivants : 
  
1. Exécutez les commandes suivantes pour récupérer les noms de compte et les mots de passe que vous utiliserez plus tard :
    
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

2. Exécutez l’applet de commande entrée-CcUpdate pour décharger le matériel et la déplacer en mode maintenance manuelle.
    
3. Mettre à jour le mot de passe du compte CceService sur le serveur hôte.
    
4. redémarrez le serveur hôte.
    
5. Exécutez l’applet de commande Restore-CcCredentials pour entrer de nouveau les mots de passe suivant la description. 
    
    Assurez-vous que vous entrez le même mot de que passe avant le déploiement de nuage connecteur à l’exception du compte CceService. Pour le compte CceService, entrez votre nouveau mot de passe. Assurez-vous que le nouveau mot de passe pour le compte CceService est la même pour tous les matériels dans le site PSTN.
    
6. Par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService. Si les mots de passe DomainAdmin, VMAdmin et CceService renvoyés à l'étape 1 sont différents, suivez les étapes suivantes :
    
7. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
   - Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService.
    
   - Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe DomainAdmin renvoyé à l'étape 1.
    
8. Exécutez Set-CcCredential -AccountType VmAdmin comme suit :
    
   - Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService.
    
   - Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe VmAdmin renvoyé à l'étape 1.  
    
9. Exécutez l’applet de commande Exit-CcUpdate pour déplacer le matériel en mode maintenance manuelle.
    
10. Après avoir terminé ces étapes sur tous les appareils dans le même site PSTN, supprimez les fichiers suivants dans le répertoire racine du site :
    
    - CcLockFile
    
    - Site_\<nom complet du Pool de Sip externe Edge\>
    
    - Tenant_\<nom complet du Pool de Sip externe Edge\>
    
    - TenantConfigLock_\<nom complet du Pool de Sip externe Edge\>
    
## <a name="add-a-new-sip-domain"></a>Ajouter un nouveau domaine SIP 
<a name="BKMK_UpdatePassword"> </a>

Pour ajouter un domaine SIP (ou plusieurs domaines SIP) à votre déploiement en nuage connecteur existant, procédez comme suit :
  
1. Assurez-vous que vous avez effectué les étapes pour mettre à jour votre domaine dans Office 365 et ont la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la façon de configurer votre domaine dans Office 365, voir [Ajouter un domaine à Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Mettre à jour le fichier de configuration du connecteur sur le nuage avec le nouveau domaine SIP ou des domaines.
    
3. Demander un nouveau certificat externe Edge avec des noms SAN supplémentaires pour domaine.SIP pour chaque domaine SIP défini dans votre configuration de connecteur dans le nuage. 
    
4. Définissez le chemin d'accès pour le nouveau certificat Microsoft Edge externe comme suit :
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    suivez les instructions pour [Modifier la configuration d'un seul site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [Modifier la configuration de plusieurs sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modifier le domaine SIP principal
<a name="BKMK_UpdatePassword"> </a>

Si vous devez modifier le domaine SIP principal de votre déploiement en nuage connecteur, procédez comme suit :
  
1. Assurez-vous que vous avez effectué les étapes pour mettre à jour votre domaine dans Office 365 et ont la possibilité d’ajouter des enregistrements DNS. Pour plus d’informations sur la façon de configurer votre domaine dans Office 365, voir [Ajouter un domaine à Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Mettre à jour le fichier de configuration du connecteur sur le nuage avec le nouveau domaine SIP.
    
3. Demander un nouveau certificat externe Edge avec des noms SAN supplémentaires pour domaine.SIP pour chaque domaine SIP défini dans votre configuration de connecteur dans le nuage. 
    
4. Définissez le chemin d'accès pour le nouveau certificat Microsoft Edge externe comme suit :
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Supprimer l’inscription du client pour chaque application dans un site en exécutant l’applet de commande suivante dans l’administrateur PowerShell sur le nuage connecteur :
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    Supprimez l'inscription du site pour chaque site en exécutant l'applet de commande suivante dans la session PowerShell de Skype Entreprise Online :


    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Désinstaller chaque appliance en exécutant la cmdlet suivante dans administrateur PowerShell sur le nuage connecteur :
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     Enregistrer chaque appliance en exécutant la cmdlet suivante dans administrateur PowerShell sur le nuage connecteur :
    
   ```
   Register-ccAppliance
   ```

9. 
    
     Installer chaque matériel, un par un, en exécutant la cmdlet suivante dans administrateur PowerShell sur le nuage connecteur :
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Remplacer le certificat de serveur Edge externe avec un nouveau certificat
<a name="BKMK_UpdatePassword"> </a>

Lorsque vous devez remplacer le certificat de serveur Edge externe sur vos applications dans le nuage connecteur, vous devez obtenir un nouveau certificat de serveur Edge, préparer le fichier PFX contenant la chaîne de certificats complète et la clé privée, puis procédez comme suit sur chaque appliance :
  
1. Placer l’application en mode maintenance à l’aide de l’applet de commande entrée-CcUpdate.
    
2. Exécutez la commande suivante : 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Si le mot de passe du nouveau certificat est identique à l’ancien, l’importation sera réussie. Si le mot de passe est différent, vous obtenez une erreur que le mot de passe est incorrect, et vous devez réinitialiser le mot de passe en exécutant l’applet de commande Register-CcAppliance avec le paramètre - Local, et puis répéter l’étape 2. 
    
4. Prendre l’appliance en mode maintenance à l’aide de l’applet de commande Exit - CcUpdate.
    

