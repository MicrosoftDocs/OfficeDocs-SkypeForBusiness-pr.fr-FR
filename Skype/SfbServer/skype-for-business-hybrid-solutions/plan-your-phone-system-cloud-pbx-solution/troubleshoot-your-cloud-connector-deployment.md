---
title: Identification et résolution des problèmes de votre déploiement Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Résoudre les problèmes de votre déploiement en nuage connecteur Edition.
ms.openlocfilehash: 5dbb046680824f2af72688844914db0096e2ded1
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295470"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Identification et résolution des problèmes de votre déploiement Cloud Connector
 
Résoudre les problèmes de votre déploiement en nuage connecteur Edition.
  
Cette rubrique vous décrit les solutions aux problèmes courants liés au déploiement de la version Cloud Connector. Si vous rencontrez des problèmes liés aux appels vers ou sur la Réseau Téléphonique Commuté (RTC), vous pouvez tenter de les résoudre en suivant les solutions décrites dans cette rubrique.
  
Connecteur de cloud fournit des mécanismes intégrés pour la résolution des problèmes automatiquement. Un processus de détection automatique recherche les problèmes potentiels avec les appareils nuage connecteur et, prend la mesure du possible, les actions correctives pour résoudre les problèmes sans l’intervention de l’administrateur. Le processus de détection fonctionne comme suit :
  
- **Séquence de détection :** Le service de gestion du nuage connecteur s’exécute un processus toutes les 60 secondes pour détecter si un appareil est inactif. Dans le nuage connecteur version 2.0 et versions ultérieure, le processus de détection utilise le Skype pour Business Corpnet commutateur pour établir des connexions de PowerShell pour les ordinateurs dans le nuage connecteur ; pour les versions antérieures à 2.0, le processus de détection utilise le commutateur de gestion dans le nuage connecteur.
    
    > [!NOTE]
    > Pour la récupération automatique aboutisse, la connectivité réseau entre l’hôte et les machines virtuelles doit être sur le commutateur réseau hôte. Veillez à vérifier la connectivité réseau pour vous assurer que la détection automatique et de récupération soient prises en compte. 
  
- **Surveillance :** Les services suivants sont analysés dans le nuage connecteur version 2.0 et versions ultérieure :
    
  - Machines virtuelles n’êtes pas connectés au nuage connecteur d’entreprise ou commutateurs virtuels Internet
    
  - Machines virtuelles sont dans un état arrêté ou enregistré
    
  - Services de serveur d’administration centrale : RÉPLICA, forme de base
    
  - Services de serveur de médiation : RÉPLICA, RTCSRV et MEDSVC
    
  - Services de serveur Edge : RÉPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Trafic entrant pare-feu règles sont désactivés pour RTCSRV CS sur le serveur de périphérie, CS RTCMEDSRV sur le serveur de médiation
    
    Dans le nuage connecteur version 1.4.2, uniquement les services suivants sont analysés :
    
  - Services de serveur de médiation : RTCSRV et MEDSVC
    
  - Service du serveur Edge : RTCSRV
    
- **Processus de récupération :** Si tous les services surveillés sont arrêtés, un matériel est marqué vers le bas et services sont arrêtés et marqués manuelles jusqu'à ce que tous les problèmes peuvent être résolus. Cela empêche les appels du routage vers une application qui peut entraîner des échecs d’appel.
    
    Le service de gestion du nuage connecteur système recommencer la récupération automatique comme suit
    
  - L’intervalle de nouvelle tentative initiale est toutes les dix secondes avec un intervalle maximal d’une heure.
    
  - Pour les tentatives de trois premiers récupération, l’intervalle de temps est de 10 secondes. L’intervalle de temps à partir de la quatrième tentative, augmente par deux fois la précédente intervalle de temps. Par exemple, la quatrième tentative sera se produisent dans les 20 secondes, la cinquième de 40 secondes et ainsi de suite. 
    
  - Lorsque l’intervalle maximal d’une heure est atteint, tentatives continue une fois par heure.
    
  - Lors de la récupération se déroule correctement, le nombre de l’intervalle et réessayez est défini à leurs valeurs initiales.
    
  - Si le service de gestion est redémarré, le nombre de l’intervalle et réessayez est réinitialisé à leurs valeurs initiales.
    
## <a name="troubleshooting"></a>Résolution des problèmes

Voici des solutions aux problèmes couramment rencontrés :
  
- **Problème : le déploiement échoue ou cesse de répondre pendant l’exécution des scripts de déploiement. Après s’être connectée sur chaque machine virtuelle, l’adresse IP est manquante ou incorrecte pour la NIC Externe/Interne/Gestion.**
    
    **Résolution :** Ce problème ne peut pas être résolu automatiquement. Les NIC ne peuvent pas être ajoutées aux machines virtuelles tant qu’elles sont en cours d’exécution. Veuillez éteindre et retirer ces machines virtuelles dans le gestionnaire hyper-v, puis exécuter l’applet de commande suivante :
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **Problème : après l'installation du serveur et de la forêt Active Directory, le serveur CMS et/ou le serveur de médiation n'ont pas correctement rejoint le domaine.**
    
    **Résolution :** Pour résoudre ce problème, suivez les étapes suivantes :
    
  - Connectez-vous au serveur Active Directory et vérifiez que le domaine a été correctement créé.
    
  - Connectez-vous au serveur CMS/de médiation et vérifiez qu’une adresse IP valide est affectée à la NIC du réseau interne, et qu'une adresse IP statique et le DNS sont configurés comme adresse IP du serveur AD.
    
  - Ouvrez une session sur le serveur CMS/médiation et ouvrez une invite de commandes. Assurez-vous que vous pouvez tester l’adresse IP et le nom de domaine complet du serveur Active Directory. Si vous ne pouvez pas, il peut être un conflit d’adresse IP. Veuillez essayer d’attribuer une nouvelle adresse IP pour Active Directory et mettre à jour DNS sur le serveur CMS/médiation en conséquence.
    
- **Problème : Vous recevez le message d’erreur suivant, « Remove-VMSwitch : Échec lors de la suppression du commutateur Ethernet virtuel. Le commutateur virtuel « Nuage connecteur gestion report » ne peut pas être supprimé car il est utilisé par les ordinateurs virtuels ou affecté aux pools enfants. »**
    
    **Résolution :** Le « nuage connecteur gestion commutateur » n’a pas été supprimé après le déploiement. Si vous avez atteint cette erreur, veuillez accédez à Gestionnaire Hyper-v et vérifiez qu’il y a pas encore un ordinateur virtuel toujours connecté. S’il existe des machines virtuelles encore connectés, déconnectez-les et supprimer le commutateur de gestion. Si le commutateur gestion toujours ne peut pas être supprimé, redémarrez le serveur hôte et réessayez.
    
- **Problème : Vous recevez le message d’erreur suivant, « Service RTCMRAUTH Échec de démarrage. Vérifiez que le service n’est pas désactivé. »**
    
    > [!NOTE]
    > Ce problème s’applique uniquement aux versions de nuage connecteur antérieures à 1.4.2. 
  
    L’échec du démarrage peut aussi être dû au fait que le serveur frontal a basculé (en utilisant la bascule ordinateur). Si c’est le cas, veuillez appeler la restauration (en utilisant la restauration ordinateur).
    
    **Résolution :** Ce problème se produit sur un serveur Edge quand le certificat de l’AC racine ou le certificat de l’AC intermédiaire n’est pas approuvé par le serveur Edge, même si le certificat extérieur peut être importé mais que la chaîne de certificats est brisée. Dans ces conditions, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.
    
    Veuillez importer manuellement dans le serveur Edge le certificat de l’AC racine et tous les certificats d’AC intermédiaires de votre certificat externe, puis redémarrer le serveur Edge. Une fois que les services RTCMRAUTH et RTCSRV ont démarré sur le serveur Edge, retournez sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez l’applet de commande suivante pour basculer vers le nouveau déploiement :
    
  ```
  Switch-CcVersion
  ```

- 
    
    **Problème : le serveur hôte a redémarré à l’application des mises à jour de Windows, et les appels qu’il gérait échouent.**
    
    **Résolution :** Si vous avez déployé un environnement de haute disponibilité, Microsoft propose une applet de commande qui permettent de déplacer un ordinateur hôte (instance de déploiement) vers ou depuis la topologie actuelle lorsque vous vérifiez et installez manuellement les mises à jour de Windows. Pour cela, veuillez suivre les étapes suivantes :
    
1. Sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez :
    
   ```
   Enter-CcUpdate
   ```

2. Vérifiez la présence de mise à jour, et installez toutes celles qui sont disponibles.
    
3. Dans la console PowerShell, exécutez l’applet de commande suivante :
    
   ```
   Exit-CcUpdate
   ```

- 
    
    **Problème : Quand un appel est placé en utilisant un numéro RTC depuis un client Skype Entreprise, l';appel ne peut pas être transformé en conférence en invitant un autre numéro RTC.**
    
    **Résolution :** Pour résoudre ce problème, voir [hybride en ligne de configurer les paramètres de serveur de médiation](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problème : un avertissement à propos de Windows Update s’affiche quand vous installez le serveur Active Directory - « La mise à jour automatique de Windows n’est pas activée. Pour vous assurer que le rôle ou la fonctionnalité que vous venez d’installer est automatiquement mis à jour, activez Windows Update. »**
    
    **Résolution :** Lancer une session PowerShell distante de client à l’aide de Skype pour les informations d’identification d’administration de Business client, puis exécutez l’applet de commande suivante pour vérifier la configuration _EnableAutoUpdate_ de votre site :
    
  ```
  Get-CsHybridPSTNSite
  ```

    Si _EnableAutoUpdate_ est définie sur **True**, vous pouvez ignorer ce message d’avertissement, car le service CCEManagement gère le téléchargement et l’installation de mises à jour de Windows pour les ordinateurs virtuels et le serveur hôte. Si _EnableAutoUpdate_ est défini sur **False**, exécutez après l’applet de commande pour lui attribuer **la valeur True**.
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Une autre solution consiste à vérifier et installer les mises à jour manuellement. Consultez la rubrique suivante.
    
- **Problème : Vous recevez un message d’erreur : Impossible d’enregistrer l’appliance car votre entrée/configuration actuelle \<SiteName\> ou \<ApplianceName\> ou \<FQDN du serveur de médiation\> ou \<adresse IP de serveur de médiation \> est en conflit avec l’ou les matériels jour existants. Supprimer l’appliance conflit ou mettre à jour vos informations de configuration d’entrée, puis enregistrer à nouveau. « CcAppliance-enregistrer pour enregistrer la solution en cours en ligne lorsqu’il est exécuté.**
    
    **Résolution :** Valeurs de la \<ApplianceName\>, \<FQDN du serveur de médiation\> et \<adresse IP de serveur de médiation\> doit être unique et uniquement utilisé pour l’inscription d’une application. Par défaut, \<ApplianceName\> provient du nom d’hôte. \<FQDN du serveur de médiation\> et \<adresse IP de serveur de médiation\> définies dans le fichier de configuration ini.
    
    Par exemple, utiliser (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) pour inscrire sur SiteName=MySite, mais s'il existe un appareil inscrit (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), un conflit se produira.
    
    Tout d’abord, vérifiez votre fichier CloudConnector.ini dans la rubrique répertoire ApplianceRoot. Vous obtiendrez \<SiteName\>, \<FQDN du serveur de médiation\> et \<adresse IP de serveur de médiation\> valeurs dans le fichier. \<ApplianceName\> est le nom du serveur hôte.
    
    Deuxièmement, lancer client PowerShell à distance à l’aide de votre Skype pour les informations d’identification d’entreprise client d’administration, puis exécutez l’applet de commande suivante pour vérifier les ou les matériels jour inscrits.
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    Après avoir identifié les conflits, vous pouvez soit mettre à jour votre fichier CloudConnector.ini avec les informations correspondant à l’appliance inscrite, soit annuler l’inscription de « l’appliance » existant pour résoudre les conflits.
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problème : L’applet de commande Get-CcRunningVersion renvoie une valeur vide s’il existe une solution déployée en cours d’exécution sur l’hôte.**
    
  **Résolution :** Cela peut arriver quand vous passez de la version 1.3.4 ou 1.3.8 à la version 1.4.1. Après l’installation de la 1.4.1 avec le .msi, vous devez exécuter `Register-CcAppliance` avant d’exécuter une quelconque autre applet de commande. `Register-CcAppliance` fera migrer le module du fichier .ini de %UserProfile%\CloudConnector vers %ProgramData%\CloudConnector. Si vous l’avez manqué, un nouveau module .ini sera créé dans le dossier %ProgramData%\CloudConnector et remplacera les informations de la version exécutée ou de sauvegarde pour la version 1.3.4 ou la 1.3.8.
    
  Comparez les modules des fichier .ini dans les dossiers %UserProfile%\CloudConnector et %ProgramData%\CloudConnector. S’il existe des différences, supprimez le fichier module.ini %ProgramData%\CloudConnector et relancez `Register-CcAppliance`. Vous pouvez également modifier le fichier manuellement à la version de sauvegarde et le fonctionnement correct.
    
- **Problème : Après avoir exécuté l’applet de commande commutateur-CcVersion pour basculer vers une ancienne version qui est différente de la version actuelle de script, il n’est aucune prise en charge de haute disponibilité pour cette version ancienne.**
    
    **Résolution :** Par exemple, vous avez mis à niveau 1.4.1 à 1.4.2. La version actuelle de script, qui peut être déterminée en exécutant `Get-CcVersion`et la version en cours d’exécution, qui peut être déterminée en exécutant `Get-CcRunningVersion` sont les deux 1.4.2. À ce stade, si vous exécutez `Switch-CcVersion` pour faire rebasculer la version exécutée vers la version 1.4.1, la haute disponibilité pour cette ancienne version ne sera pas prise en charge.
    
    Pour que la haute disponibilité soit entièrement prise en charge, veuillez rebasculer vers la version 1.4.2 afin que la version exécutée et celle du script soient les mêmes. Si vous rencontrez des problèmes avec votre déploiement 1.4.2, veuillez désinstaller et réinstaller dès que possible.
    
- **Problème : Les certificats de l’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**
    
    **Résolution :** Les certificats de l’autorité de certification de Skype Entreprise sont valides cinq ans. Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides deux ans.
    
    > [!NOTE]
    > Dans le nuage connecteur version 2.0 et versions ultérieure, l’applet de commande renouveler-CcServerCertificate a été modifié pour la mise à jour-CcServerCertificate et l’applet de commande renouveler-CcCACertificate a été modifié pour la mise à jour-CcCACertificate. 
  
    Si les certificats internes émis vers le magasin Central de gestion, le serveur de médiation et le serveur de périphérie sont bientôt expirer ou compromis, exécutez le renouvellement-CcServerCertificate ou l’applet de commande Update-CcServerCertificate pour renouveler vos certificats.
    
    Si les certificats d’autorité de certification sont bientôt expirer, exécutez la cmdlet renouveler-CcCACertificate ou CcCACertificate de la mise à jour pour renouveler vos certificats.
    
    **Si les certificats d’autorité de certification sont compromises et s’il n'existe qu’une seule application dans le site,** effectuez les opérations suivantes :
    
1. Exécutez l’applet de commande Enter-CcUpdate afin d’épuiser les services et de mettre l’appliance en mode maintenance.
    
2. Exécutez les applets de commande suivantes afin de réinitialiser et de créer les nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :
    
    Pour les versions de nuage connecteur avant 2.0 :
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Ou pour le nuage connecteur version 2.0 et versions ultérieure :
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. Exécutez l’applet de commande Exit-CcUpdate afin de démarrer les services et de quitter le mode maintenance.
    
4. Exécutez l’applet de commande Export-CcRootCertificate sur le fichier local dans l’appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.
    
    **Si les certificats d’autorité de certification sont compromises et qu’il existe plusieurs applications dans le site,** procédez comme suit séquentiel sur chaque appliance dans le site.
    
    Microsoft recommande que vous suivez ces étapes pendant les heures non pics d’utilisation.
    
   - Sur la première application, exécutez l’applet de commande Remove-CcCertificationAuthorityFile pour le nettoyage de l’autorité de certification sauvegarder des fichiers dans le \<SiteRoot\> directory.
    
   - Exécutez l’applet de commande entrée-CcUpdate pour décharger les services et placer chaque application en mode maintenance.
    
   - Exécutez les applets de commande suivantes afin de réinitialiser et de créer les nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :
    
     Pour les versions de nuage connecteur avant 2.0 :
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Ou pour le nuage connecteur version 2.0 et versions ultérieure :
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

   - Sur la première application, exécutez la cmdlet suivante pour sauvegarder les fichiers de l’autorité de certification pour le \<SiteRoot\> dossier. Ultérieurement, sur tous les autres matériels dans le même site, l’applet de commande Reset-CcCACertificate consomme automatiquement les fichiers de sauvegarde d’autorité de certification et équipements utiliseront le même certificat racine.
    
     ```
     Backup-CcCertificationAuthority
     ```

   - Exécutez l’applet de commande Exit-CcUpdate pour démarrer les services et quitter le mode maintenance. 
    
   - Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de commande Export-CcRootCertificate à partir de n’importe quel matériel dans le site, puis installez le certificat exporté dans vos passerelles PSTN. 
    
- **Problème : Vous recevez le message d’erreur suivant dans le journal du Service de gestion de connecteur dans le nuage, « C:\Program Files\Skype pour Business nuage connecteur Edition\ManagementService\CceManagementService.log » : erreur CceService : 0 : exception inattendue lorsque rapports d’état en ligne : System.Management.Automation.CmdletInvocationException : Échec de l’ouverture de session de l’utilisateur \<administrateur client Global\>. Créez un nouvel objet d’informations d’identification, en veillant à ce que vous avez utilisé le nom d’utilisateur et le mot de passe. ---\>**
    
    **Résolution :** Informations d’identification d’administration Office 365 client globale ont été modifiées depuis l’appliance nuage connecteur a été enregistré. Pour mettre à jour les informations d’identification stockées localement sur le matériel de nuage connecteur, exécutez ce qui suit à partir de PowerShell administrateur sur l’application hôte :
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problème : Une fois que vous modifiez le mot de passe pour le compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : clé non valide pour une utilisation dans spécifié état. » dans %ProgramFiles%\Skype Business Cloud Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de l’applet de commande Get-CcCredential.**
    
    **Résolution :** Toutes les informations d’identification sur le nuage connecteur sont stockées dans le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ». Lorsque le mot de passe sur le serveur hôte change, vous devrez mettre à jour les informations d’identification stockées localement.
    
    **Si vous exécutez la version 1.4.2 de Cloud Connector,** renouvelez tous les mots de passe Cloud Connector en suivant les étapes suivantes :
    
  1. redémarrez le serveur hôte.
    
  2. Supprimez le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».
    
  3. Lancer une console PowerShell en tant qu’administrateur et exécutez « Register-CcAppliance-Local » à entrer les mots de passe suivant la description. Entrez les mots de passe même que vous avez entré avant le déploiement dans le nuage connecteur.
    
     **Si vous exécutez nuage connecteur 2.0 ou version ultérieure,** régénérez tous les mots de passe dans le nuage connecteur en suivant ces étapes :
    
  4. redémarrez le serveur hôte.
    
  5. Supprimez le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».
    
  6. Lancer une console PowerShell en tant qu’administrateur et exécutez « Register-CcAppliance-Local » à entrer les mots de passe suivant la description. 
    
     Si le fichier du mot de passe en mémoire a été généré avec la version 1.4.2 de Cloud Connector, utilisez le mot de passe VMAdmin pour le mot de passe CceService lorsque vous y serez invité. Saisissez le même mot de passe que vous avez saisi pour le déploiement de Cloud Connector pour tous les autres comptes.
    
     Si le fichier du mot de passe en mémoire a été généré avec la version 1.4.2 de Cloud Connector et que les mots de passe DomainAdmin et VMAdmin sont différents, suivez les étapes suivantes :
    
  7. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
  8. Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService.
    
  9. Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe DomainAdmin que vous avez utilisé auparavant.
    
     Si le fichier de mot de passe mis en cache a été généré avec le nuage connecteur version 2.0 ou version ultérieure, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe en tant que CceService. Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les étapes suivantes :
    
  10. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
       1. Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService
    
       2. Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe DomainAdmin que vous avez utilisé auparavant.
    
  11. Exécutez Set-CcCredential -AccountType VmAdmin comme suit :
    
       1. Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService
    
       2. Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe VmAdmin que vous avez utilisé auparavant.  
    
- **Problème : Avec le nuage connecteur version 2.1 et version ultérieure, lors de l’exécution Register-CcAppliance ou autres applets de commande sur le matériel, vous recevez un message d’erreur tel : » pour chaque objet : la propriété « Commune » est introuvable sur cet objet. Vérifiez que la propriété existe. À C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 caractère : 14 »**
    
    **Résolution :** Nuage connecteur 2.1 et version ultérieure requiert .NET Framework 4.6.1 ou version ultérieure. Veuillez mettre à jour .NET Framework sur l’application vers la version 4.6.1 ou version ultérieure et réexécutez le cmdlet(s).

- **Problème : Nuage connecteur Edition 2.1, lorsque vous exécutez Install-CcAppliance, vous recevez un message d’erreur tel que : « Impossible d’installer la nouvelle instance avec l’erreur : Impossible de définir « État » car seules les chaînes peuvent être utilisés en tant que valeurs pour définir les propriétés XmlNode »**

   **Résolution :** Dans Cloudconnector.ini, sous la section [courantes], ajoutez la configuration de « État » comme indiqué ci-dessous : CountryCode = US State = WA ville = Redmond

   Il n’est pas obligatoire pour la ligne « État » à la valeur, mais la ligne « État » ne peut pas être supprimée à partir du fichier Cloudconnector.ini.

- **Problème : Vous recevez le message d’erreur « Dismount-WindowsImage : Dismount-WindowsImage a échoué. Code d’erreur = 0xc1550115 » lors de l’installation ou mise à niveau dans le nuage connecteur Edition.**
    
    **Résolution :** Lancer une console PowerShell en tant qu’administrateur, exécutez « DISM-Cleanup-Wim' ». Cela nettoie toutes les images défectueux. Réexécutez Install-CcAppliance ou attendez que les fichiers binaires mettre à niveau automatiquement.
    
- **Problème : Déploiement de l’application dans un environnement de haute disponibilité dans le nuage connecteur échoue**
    
    **Résolution :** Les étapes à que suivre dépendent de la raison pour laquelle le déploiement a échoué :
    
  - Si la première application de nuage connecteur échoue et vous ne pouvez pas déterminer la cause de l’échec, vous devez installer l’application à nouveau jusqu'à ce que le déploiement a réussi et puis installer les autres applications.
    
  - En cas d’échec de l’application connecteur sur le nuage avec un problème mineur, par exemple un problème de certificat externe, vous pourrez peut-être résoudre le problème sans installer de nouveau l’application. Vous pouvez ensuite utiliser des clients PowerShell à distance pour marquer le déploiement comme étant réussi comme suit. (Vous pouvez également utiliser les étapes suivantes si le premier déploiement a réussi, mais, pour une raison quelconque, nuage connecteur ne parvient pas à signaler le déploiement comme étant réussi.)
    
  - Pour obtenir l’identité (GUID) de l’application dans le nuage connecteur, exécutez l’applet de commande Get-CsHybridPSTNAppliance.
    
  - Pour marquer le matériel comme correctement déployé, exécutez la Set-CsCceApplianceDeploymentStatus comme suit :
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problème : Vous devez vérifier et installer les mises à jour de Windows manuellement sur le serveur hôte ou les machines virtuelles.**
    
   **Résolution ** Nous vous conseillons de profiter des avantages des mises à jour automatiques du système d’exploitation fournies par la version Cloud Connector de Skype Entreprise. Une fois qu’un appareil est inscrit pour une gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifieront et installeront automatiquement les mises à jour de Windows en fonction des paramètres d’heure de mise à jour du système d’exploitation.
    
   Si vous devez vérifier et installer les mises à jour de Windows manuellement, suivez les étapes de cette rubrique qui s’appliquent à votre type de déploiement. Vous devriez mettre à jour le serveur hôte en même temps que les machines virtuelles qui sont exécutées dessus pour réduire le temps d’arrêt nécessaire aux mises à jour.
    
   Si vous préférez, vous pouvez utiliser un serveur WSUS (services de mises à jour de serveur Windows) pour qu’il fournisse les mises à jour aux serveurs Cloud Connector. Assurez-vous simplement de configurer Windows Update de sorte qu’il n’effectue **pas** d’installation automatique.
    
   Pour en savoir plus sur la mise à jour de votre déploiement Cloud Collector manuellement, consultez la rubrique suivante.
    
- **Problème : Lorsque le nuage connecteur mises à jour vers une nouvelle version, cmdlets de connecteur de nuage ne sont pas mis à jour.** Cela se produit parfois si une fenêtre PowerShell reste ouverte lors de la mise à jour automatique se produit.
    
  **Résolution :** Pour charger les applets de commande mis à jour, vous pouvez effectuer une des opérations suivantes :
    
   - Fermez PowerShell sur le matériel de nuage connecteur, puis rouvrez PowerShell.
    
     - Vous pouvez également exécuter Import-Module CloudConnector-Force. 
 
-   **Problème : « le terme 'Stop-CsWindowsService' n’est pas reconnu comme nom de l’applet de commande, fonction, fichier de script ou programme exécutable. » erreur lorsque vous essayez d’exécuter l’applet de commande entrée-CcUpdate.**

    **Résolution :** Supprimez le fichier de HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache $.
PowerShell crée ce fichier comme un cache des applets de commande de modules qu’il trouve afin qu’il ne doit pas recommencer l’analyse chaque fois que tous les modules que choses vraiment lente. Probablement, il a été une corruption de fichiers qui fournie résultats trompeuses PowerShell lors de la lecture depuis la mémoire cache.

-   **Problème : « Import-Module CloudConnector » génère l’erreur « Import-Module : le module spécifié est « CloudConnector » n’a pas été chargé, car aucun fichier de module valide a été trouvé dans n’importe quel répertoire module »**

    **Résolution **
    - Valider que fait le module CloudConnector existe sous c:\Program Files\WindowsPowerShell\Modules
    
    - Une fois la validation de ce module CloudConnector existe sous cet emplacement, la variable d’environnement PSModulePath stocker le chemin d’accès vers les emplacements des modules peut être modifiée :
    
     a. Modification temporaire : Démarrer Powershell en tant qu’administrateur et exécutez la commande suivante : $env : PSModulePath = $env : PSModulePath + « ; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Changement persistent, démarrer le PowerShell en tant qu’administrateur et exécutez les commandes suivantes, un par un : $CurrentValue = [Environment] :: GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules », « Machine »)

    
## <a name="install-windows-updates-manually"></a>Installer manuellement les mises à jour Windows

Si vous ne voulez pas utiliser les mises à jour automatiques dans votre environnement, suivez ces étapes pour vérifier et appliquer manuellement les mises à jour de Windows. Vérifier et installer manuellement les mises à jour de Windows nécessite de redémarrer le serveur. Lorsque le redémarrage d’un serveur hôte, les utilisateurs ne sera pas en mesure d’utiliser le connecteur sur le nuage pour passer ou recevoir des appels. Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler quand elles ont lieu, puis redémarrer les machines au besoin au moment de votre choix pour éviter une perturbation des services.
  
Pour vérifier et installer manuellement les mises à jours, connectez-vous à chaque serveur hôte et ouvrez le **Panneau de contrôle**. Sélectionnez **système et sécurité \>mise à jour Windows**, puis gérer les mises à jour et redémarre le serveur en fonction de votre environnement.
  
- S’il n’existe qu’un seul appareil sur le site, connectez-vous à chaque machine virtuelle et ouvrez le **Panneau de contrôle**. Sélectionnez **système et sécurité \>mise à jour Windows**, puis configurez les mises à jour et redémarre le serveur comme il convient.
    
- S’il existe plusieurs appareils sur le site, l’instance en cours de mise à jour et de redémarrage n’est plus accessible par les utilisateurs. Les utilisateurs se connecteront à d’autres instances du déploiement jusqu’à ce que toutes les machines virtuelles et que tous les services Skype Entreprise démarrent sur les machines virtuelles après la fin des mises à jour. Pour éviter de potentielles perturbations du service, vous pouvez supprimer les instances de la haute disponibilité pendant que vous appliquez les mises à jour, puis les restaurer une fois celles-ce achevées. Pour ce faire :
    
1. Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.
    
2. Supprimez l’instance de la haute disponibilité grâce à l’applet de commande suivante :
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    Suivez les étapes pour une instance unique afin d’appliquer manuellement les mises à jour et redémarrer la machine virtuelle.
    
4. Définissez à nouveau l’instance en haute disponibilité grâce à l’applet de commande suivante :
    
   ```
   Exit-CcUpdate
   ```

Pour des déploiements sur plusieurs sites, suivez les étapes pour un site unique pour chaque site du déploiement, en appliquant les mises à jour un site à la fois.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Conseils lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte de nuage connecteur

Si vous avez besoin installer un logiciel antivirus sur l’ordinateur hôte de connecteur dans le nuage, vous devez ajouter les exclusions suivantes :
  
- Répertoire de matériel local sur chaque ordinateur.
    
- Annuaire de sites à distance sur chaque ordinateur.
    
- Répertoire du Site local sur l’ordinateur héberge le dossier racine du site partagé.
    
- %ProgramFiles%\Skype pour l’édition de connecteur Business Cloud
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Le processus Microsoft.Rtc.CCE.ManagementService.exe.
