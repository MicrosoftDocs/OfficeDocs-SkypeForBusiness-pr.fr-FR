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
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Résoudre les problèmes de votre déploiement de Cloud connecteur Edition.
ms.openlocfilehash: 1fb4f65c0fefd335865c5babb0e69090ab824908
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Identification et résolution des problèmes de votre déploiement Cloud Connector
 
Résoudre les problèmes de votre déploiement de Cloud connecteur Edition.
  
Cette rubrique vous décrit les solutions aux problèmes courants liés au déploiement de la version Cloud Connector. Si vous rencontrez des problèmes liés aux appels vers ou sur la Réseau Téléphonique Commuté (RTC), vous pouvez tenter de les résoudre en suivant les solutions décrites dans cette rubrique.
  
Connecteur de nuage fournit des mécanismes intégrés pour résoudre automatiquement les problèmes. Un processus de détection automatique recherche les problèmes potentiels avec les appliances de connecteur du nuage et, si possible, prend des actions correctives pour résoudre les problèmes sans l’intervention de l’administrateur. Le processus de détection fonctionne comme suit :
  
- **Séquence de détection :** Le service de gestion du connecteur nuage exécute un processus toutes les 60 secondes pour détecter si un appareil est vers le bas. Dans le nuage lien version 2.0 et ultérieure, le processus de détection utilise le Skype pour commutateur Corpnet d’entreprise pour établir les connexions PowerShell pour les machines de nuage connecteur ; pour les versions antérieures à 2.0, le processus de détection utilise le commutateur de gestion connecteur de nuage.
    
    > [!NOTE]
    > Pour la récupération automatique réussisse, la connectivité réseau entre l’hôte et les machines virtuelles doit être sur le commutateur de réseau hôte. Veillez à vérifier la connectivité réseau pour vous assurer que la détection automatique et de récupération peut réussir. 
  
- **Analyse :** Les services suivants sont analysés dans le nuage, connecteur version 2.0 et versions ultérieure :
    
  - Machines virtuelles n’êtes pas connectés au connecteur de nuage d’entreprise ou les commutateurs virtuels Internet
    
  - Les Machines virtuelles sont dans un état enregistré ou arrêté
    
  - Les services de serveur d’administration centrale : RÉPLICA, maître
    
  - Services de serveur de médiation : RÉPLICA, RTCSRV et MEDSVC
    
  - Edge Server services : RÉPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Règles sont désactivées pour CS RTCSRV sur le serveur de transport Edge, RTCMEDSRV CS sur le serveur de médiation de pare-feu de trafic entrant
    
    Dans le nuage lien version 1.4.2, seulement les services suivants sont analysés :
    
  - Services de serveur de médiation : RTCSRV et MEDSVC
    
  - Bord du service serveur : RTCSRV
    
- **Processus de récupération :** Si les services supervisés sont arrêtés, une solution matérielle-logicielle est sélectionnée vers le bas et les services sont arrêtés et marqués manuelles jusqu'à ce que tous les problèmes peuvent être résolus. Cela empêchera les appels du routage vers une solution matérielle-logicielle qui peut entraîner des échecs d’appel.
    
    Le service de gestion du connecteur nuage va réessayer la récupération automatique comme suit.
    
  - L’intervalle de nouvelle tentative initiale est toutes les dix secondes avec un intervalle maximum d’une heure.
    
  - Pour les tentatives de trois premières récupération, l’intervalle de temps est de 10 secondes. À partir de la quatrième tentative, l’intervalle de temps augmente par deux fois l’intervalle heure précédente. Par exemple, la quatrième tentative va se produire dans les 20 secondes, le cinquième de 40 secondes et ainsi de suite. 
    
  - Lorsque l’intervalle maximal d’une heure est atteinte, les tentatives va continuer une fois par heure.
    
  - Lorsque la restauration est réussie, le nombre de l’intervalle et réessayez est défini à leurs valeurs initiales.
    
  - Si le service Gestion des services sont redémarré, le nombre de l’intervalle et réessayez est réinitialisé à leurs valeurs initiales.
    
## <a name="troubleshooting"></a>Identification et résolution des problèmes

Voici des solutions aux problèmes fréquemment rencontrés :
  
- **Problème : le déploiement échoue ou ne répond plus lors de l’exécution des scripts de déploiement. Après la connexion à chaque machine virtuelle, l’adresse IP est manquante ou incorrecte pour la carte d’interface réseau (NIC) de gestion/interne/externe.**
    
    **Résolution :** Ce problème ne peut pas être résolu automatiquement. Les NIC ne peuvent pas être ajoutées aux machines virtuelles tant qu’elles sont en cours d’exécution. Veuillez éteindre et retirer ces machines virtuelles dans le gestionnaire hyper-v, puis exécuter l’applet de commande suivante :
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **Problème : Une fois que le serveur Active Directory et la forêt sont installés, le serveur CMS et/ou le serveur de médiation ne pas joindre le domaine correctement.**
    
    **Résolution :** Pour résoudre ce problème, procédez comme suit :
    
  - Connectez-vous au serveur Active Directory et vérifiez que le domaine a été correctement créé.
    
  - Connectez-vous au serveur CMS/de médiation et vérifiez qu’une adresse IP valide est affectée à la NIC du réseau interne, et qu'une adresse IP statique et le DNS sont configurés comme adresse IP du serveur AD.
    
  - Ouvrez une session sur le serveur CMS/médiation et ouvrez une invite de commande. Vérifiez que vous pouvez tester l’adresse IP et nom de domaine complet du serveur Active Directory. Si vous ne le pouvez pas, il peut y avoir un conflit d’adresse IP. Veuillez essayer d’attribuer une nouvelle adresse IP pour Active Directory et de mettre à jour DNS sur le serveur CMS/médiation en conséquence.
    
- **Problème : Vous recevez le message d’erreur suivant, « Remove-VMSwitch : Échec lors de la suppression des switch Ethernet virtuel. La commutation virtuelle « Gestion de connecteur nuage report » Impossible de supprimer car il est utilisé par les ordinateurs virtuels ou affectée à des pools d’enfants. »**
    
    **Résolution :** Le « nuage connecteur gestion Switch » n’a pas été supprimé après le déploiement. Si vous appuyez sur cette erreur, veuillez accédez à Gestionnaire Hyper-v et vérifiez qu’il y a pas encore une machine virtuelle toujours connectée à celui-ci. S’il existe des machines virtuelles toujours connectés, déconnectez-les et supprimez le commutateur de gestion. Si le commutateur de gestion ne peut pas toujours être supprimé, redémarrez le serveur hôte et réessayez.
    
- **Problème : Vous recevez le message d’erreur suivant, « échec du démarrage du Service RTCMRAUTH. Vérifiez que le service n’est pas désactivé. »**
    
    > [!NOTE]
    > Ce problème s’applique uniquement aux versions de connecteur de nuage antérieures à la version 1.4.2. 
  
    L’échec du démarrage peut aussi être dû au fait que le serveur frontal a basculé (en utilisant la bascule ordinateur). Si c’est le cas, veuillez appeler la restauration (en utilisant la restauration ordinateur).
    
    **Résolution :** Ce problème se produit sur un serveur Edge quand le certificat de l’AC racine ou le certificat de l’AC intermédiaire n’est pas approuvé par le serveur Edge, même si le certificat extérieur peut être importé mais que la chaîne de certificats est brisée. Dans ces conditions, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.
    
    Veuillez importer manuellement dans le serveur Edge le certificat de l’AC racine et tous les certificats d’AC intermédiaires de votre certificat externe, puis redémarrer le serveur Edge. Une fois que les services RTCMRAUTH et RTCSRV ont démarré sur le serveur Edge, retournez sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez l’applet de commande suivante pour basculer vers le nouveau déploiement :
    
  ```
  Switch-CcVersion
  ```

- 
    
    **Problème : le serveur hôte a redémarré à l’application des mises à jour de Windows, et les appels qu’il gérait échouent.**
    
    **Résolution :** Si vous avez déployé un environnement haute disponibilité, Microsoft fournit une applet de commande pour vous aider à déplacer un ordinateur hôte (instance de déploiement) dans ou en dehors de la topologie actuelle lorsque vous vérifiez et installez manuellement les mises à jour de Windows. Pour cela, veuillez suivre les étapes suivantes :
    
1. Sur le serveur hôte, démarrez une console PowerShell en tant qu’administrateur, puis exécutez :
    
  ```
  Enter-CcUpdate
  ```

2. Vérifiez si des mises à jour sont disponibles et installez-les.
    
3. Dans la console PowerShell, exécutez l’applet de commande suivante :
    
  ```
  Exit-CcUpdate
  ```

- 
    
    **Problème : Quand un appel est placé en utilisant un numéro RTC depuis un client Skype Entreprise, l';appel ne peut pas être transformé en conférence en invitant un autre numéro RTC.**
    
    **Résolution :** Pour résoudre ce problème, reportez-vous à la section [hybride en ligne de configurer les paramètres de serveur de médiation](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problème : un avertissement à propos de Windows Update s’affiche quand vous installez le serveur Active Directory - « La mise à jour automatique de Windows n’est pas activée. Pour vous assurer que le rôle ou la fonctionnalité que vous venez d’installer est automatiquement mis à jour, activez Windows Update. »**
    
    **Résolution :** Lancement d’une session PowerShell distant des clients à l’aide de Skype d’informations d’identification d’administration Business locataire, puis exécuter l’applet de commande suivante pour vérifier la configuration _EnableAutoUpdate_ de votre site :
    
  ```
  Get-CsHybridPSTNSite
  ```

    Si _EnableAutoUpdate_ est définie sur **True**, vous pouvez ignorer ce message d’avertissement parce que le service CCEManagement gère le téléchargement et l’installation des mises à jour de Windows pour les ordinateurs virtuels et le serveur hôte. Si _EnableAutoUpdate_ est définie sur **False**, exécutez après l’applet de commande pour le définir sur **True**.
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Une autre solution consiste à vérifier et installer les mises à jour manuellement. Consultez la rubrique suivante.
    
- **Problème : Vous recevez un message d’erreur : Impossible d’enregistrer l’appliance car votre entrée/configuration actuelle \<SiteName\> ou \<ApplianceName\> ou \<FQDN de serveur de médiation\> ou \<adresse IP du serveur de médiation \> est en conflit avec l’ou les matériels jour existants. Supprimer la solution matérielle-logicielle de conflit ou mettre à jour vos informations/configuration de l’entrée, puis enregistrer de nouveau. ' Registre-CcAppliance pour enregistrer la solution matérielle-logicielle en cours en ligne lorsqu’il est exécuté.**
    
    **Résolution :** Valeurs pour le \<ApplianceName\>, \<FQDN de serveur de médiation\> et \<adresse IP du serveur de médiation\> doit être unique et uniquement utilisées pour l’enregistrement d’une solution matérielle-logicielle. Par défaut, \<ApplianceName\> s’agit du nom d’hôte. \<FQDN du serveur de médiation\> et \<adresse IP du serveur de médiation\> défini dans le fichier de configuration ini.
    
    Par exemple, utiliser (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) pour inscrire sur SiteName=MySite, mais s'il existe un appareil inscrit (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), un conflit se produira.
    
    Tout d’abord, vérifiez votre fichier CloudConnector.ini dans la rubrique répertoire ApplianceRoot. Vous obtiendrez \<SiteName\>, \<FQDN de serveur de médiation\> et \<adresse IP du serveur de médiation\> les valeurs dans le fichier. \<ApplianceName\> est le nom de votre serveur hôte.
    
    Ensuite, lancez locataire PowerShell distant à l’aide de votre Skype pour les informations d’identification d’entreprise locataire admin, puis exécutez l’applet de commande suivante pour vérifier les ou les matériels jour enregistrés.
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    Après avoir identifié les conflits, vous pouvez soit mettre à jour votre fichier CloudConnector.ini avec les informations correspondant à l’appliance inscrite, soit annuler l’inscription de « l’appliance » existant pour résoudre les conflits.
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

- 
    
    **Problème : L’applet de commande Get-CcRunningVersion retourne une valeur vide s’il existe une solution matérielle-logicielle déployée en cours d’exécution sur l’hôte.**
    
    **Résolution :** Cela peut arriver quand vous passez de la version 1.3.4 ou 1.3.8 à la version 1.4.1. Après l’installation de la 1.4.1 avec le .msi, vous devez exécuter `Register-CcAppliance` avant d’exécuter une quelconque autre applet de commande. `Register-CcAppliance` fera migrer le module du fichier .ini de %UserProfile%\CloudConnector vers %ProgramData%\CloudConnector. Si vous l’avez manqué, un nouveau module .ini sera créé dans le dossier %ProgramData%\CloudConnector et remplacera les informations de la version exécutée ou de sauvegarde pour la version 1.3.4 ou la 1.3.8.
    
    Comparez les modules des fichier .ini dans les dossiers %UserProfile%\CloudConnector et %ProgramData%\CloudConnector. S’il existe des différences, supprimez le fichier module.ini dans %ProgramData%\CloudConnector et relancez `Register-CcAppliance`. Vous pouvez également modifier le fichier manuellement à l’exécution correcte et la version de sauvegarde.
    
- **Problème : Après avoir exécuté l’applet de commande du commutateur-CcVersion pour passer à une ancienne version qui est différente de la version de script en cours, il est sans prise en charge de haute disponibilité pour cette ancienne version.**
    
    **Résolution :** Par exemple, vous avez mis à niveau 1.4.1 à 1.4.2. La version de script en cours, qui peut être déterminée en exécutant `Get-CcVersion`et la version en cours d’exécution, qui peut être déterminée en exécutant `Get-CcRunningVersion` sont les deux 1.4.2. À ce stade, si vous exécutez `Switch-CcVersion` pour faire rebasculer la version exécutée vers la version 1.4.1, la haute disponibilité pour cette ancienne version ne sera pas prise en charge.
    
    Pour que la haute disponibilité soit entièrement prise en charge, veuillez rebasculer vers la version 1.4.2 afin que la version exécutée et celle du script soient les mêmes. Si vous rencontrez des problèmes avec votre déploiement 1.4.2, veuillez désinstaller et réinstaller dès que possible.
    
- **Problème : Les certificats de l’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**
    
    **Résolution :** Les certificats de l’autorité de certification de Skype Entreprise sont valides cinq ans. Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides deux ans.
    
    > [!NOTE]
    > Dans le nuage lien version 2.0 et ultérieure, l’applet de commande de renouvellement-CcServerCertificate a été modifiée et mise à jour-CcServerCertificate et l’applet de commande de renouvellement-CcCACertificate a été modifiée et mise à jour-CcCACertificate. 
  
    Si les certificats internes, émis le magasin Central de gestion, serveur de médiation, et serveur de transport Edge sont bientôt expirer ou compromis, exécutent le renouvellement-CcServerCertificate ou l’applet de commande Update-CcServerCertificate pour renouveler vos certificats.
    
    Si les certificats d’autorité de certification sont bientôt expirer, exécutez la cmdlet de renouvellement-CcCACertificate ou CcCACertificate de la mise à jour pour renouveler vos certificats.
    
    **Si les certificats d’autorité de certification sont compromises et il n'existe qu’une seule solution matérielle-logicielle sur le site,** effectuez les opérations suivantes :
    
1. Exécutez l’applet de commande Enter-CcUpdate afin d’épuiser les services et de mettre l’appliance en mode maintenance.
    
2. Exécutez les applets de commande suivantes afin de réinitialiser et de créer les nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :
    
    Pour les versions de connecteur de nuage avant 2.0 :
    
  ```
  Reset-CcCACertificate 
Renew-CcServerCertificate 
Remove-CcLegacyServerCertificate 

  ```

    Ou pour connecteur de nuage version 2.0 et versions ultérieur :
    
  ```
  Reset-CcCACertificate 
Update-CcServerCertificate 
Remove-CcLegacyServerCertificate 

  ```

3. Exécutez l’applet de commande Exit-CcUpdate afin de démarrer les services et de quitter le mode maintenance.
    
4. Exécutez l’applet de commande Export-CcRootCertificate sur le fichier local dans l’appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.
    
    **Si les certificats d’autorité de certification sont compromises et il y a plusieurs applications sur le site,** effectuer les étapes séquentielles suivantes sur chaque solution matérielle-logicielle sur le site.
    
    Microsoft recommande d’effectuer ces opérations pendant les périodes creuses de.
    
  - Sur la première solution matérielle-logicielle, exécutez l’applet de commande Remove-CcCertificationAuthorityFile pour le nettoyage de l’autorité de certification sauvegarder des fichiers dans le \<SiteRoot\> répertoire.
    
  - Exécutez l’applet de commande entrée-CcUpdate pour décharger des services et de placer chaque solution matérielle-logicielle en mode maintenance.
    
  - Exécutez les applets de commande suivantes afin de réinitialiser et de créer les nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :
    
    Pour les versions de connecteur de nuage avant 2.0 :
    
  ```
  Reset-CcCACertificate
Renew-CcServerCertificate
Remove-CcLegacyServerCertificate 

  ```

    Ou pour connecteur de nuage version 2.0 et versions ultérieur :
    
  ```
  Reset-CcCACertificate
Update-CcServerCertificate
Remove-CcLegacyServerCertificate 

  ```

  - Sur la première application, exécutez l’applet de commande suivante pour sauvegarder les fichiers de l’autorité de certification à la \<SiteRoot\> dossier. Plus tard, sur toutes les autres applications sur le même site, l’applet de commande Reset-CcCACertificate utilisent automatiquement les fichiers de sauvegarde d’autorité de certification et appareils utiliseront le même certificat racine.
    
  ```
  Backup-CcCertificationAuthority
  ```

  - Exécutez l’applet de commande Exit-CcUpdate pour démarrer les services et quitter le mode maintenance. 
    
  - Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de commande de CcRootCertificate de l’exportation à partir de n’importe quel matériel sur le site et puis installez le certificat exporté sur vos passerelles RTPC. 
    
- **Problème : Vous recevez le message d’erreur suivant dans le journal du Service de gestion de connecteur Cloud, « C:\Program Files\Skype pour Business Cloud connecteur Edition\ManagementService\CceManagementService.log » : erreur de CceService : 0 : exception inattendue lors de la rapports d’état en ligne : System.Management.Automation.CmdletInvocationException : Échec de l’ouverture de session de l’utilisateur \<administration des clients Global\>. Créez un nouvel objet d’informations d’identification, en veillant à ce que vous avez utilisé le nom d’utilisateur et le mot de passe. ---\>**
    
    **Résolution :** Les informations d’identification administrateur de Office 365 locataire global ont été modifiées depuis l’application Connecteur de nuage a été enregistrée. Pour mettre à jour les informations d’identification stockées localement sur le matériel de connecteur de nuage, exécutez la suivante à partir de PowerShell d’administrateur sur l’application hôte :
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- 
    
    **Problème : Après avoir modifié le mot de passe pour le compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : spécifié de clé non valide pour une utilisation dans état. » dans %ProgramFiles%\Skype pour le nuage de Business Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de l’applet de commande Get-CcCredential.**
    
    **Résolution :** Toutes les informations d’identification de connecteur de nuage sont stockées dans le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ». Lorsque le mot de passe sur le serveur hôte change, vous devez mettre à jour les informations d’identification stockées localement.
    
    **Si vous exécutez le connecteur nuage version 1.4.2,** régénérer tous les mots de passe de connecteur de nuage en suivant ces étapes :
    
1. redémarrez le serveur hôte.
    
2. Supprimez le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».
    
3. Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Registre-CcAppliance-Local » entrer à nouveau les mots de passe suit la description. Entrez les mêmes mots de passe saisis avant le déploiement de connecteur de nuage.
    
    **Si vous exécutez le connecteur nuage version 2.0 ou ultérieure,** régénérer tous les mots de passe de connecteur de nuage en suivant ces étapes :
    
1. redémarrez le serveur hôte.
    
2. Supprimez le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».
    
3. Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Registre-CcAppliance-Local » entrer à nouveau les mots de passe suit la description. 
    
    Si le fichier du mot de passe en mémoire a été généré avec la version 1.4.2 de Cloud Connector, utilisez le mot de passe VMAdmin pour le mot de passe CceService lorsque vous y serez invité. Saisissez le même mot de passe que vous avez saisi pour le déploiement de Cloud Connector pour tous les autres comptes.
    
    Si le fichier du mot de passe en mémoire a été généré avec la version 1.4.2 de Cloud Connector et que les mots de passe DomainAdmin et VMAdmin sont différents, suivez les étapes suivantes :
    
1. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
1. Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService.
    
2. Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe DomainAdmin que vous avez utilisé auparavant.
    
    Si le fichier de mise en cache du mot de passe a été généré avec connecteur de nuage version 2.0 ou une version ultérieure, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe en tant que CceService. Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les opérations suivantes :
    
1. Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :
    
1. Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService
    
2. Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe DomainAdmin que vous avez utilisé auparavant.
    
2. Exécutez Set-CcCredential -AccountType VmAdmin comme suit :
    
1. Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService
    
2. Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe VmAdmin que vous avez utilisé auparavant.  
    
- 
    
    **Problème : Avec le nuage lien version 2.1 et version ultérieure, lors de l’exécution du Registre-CcAppliance ou autres applets de commande sur la solution matérielle-logicielle, vous recevez un message d’erreur tel que : « pour chaque objet : la propriété « Commune » est introuvable sur cet objet. Vérifiez que la propriété existe. À C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char : 14 »**
    
    **Résolution :** Cloud connecteur 2.1 et ultérieur requiert.NET Framework 4.6.1 ou version ultérieure. Veuillez mettre à jour de.NET Framework sur la solution matérielle-logicielle version 4.6.1 ou version ultérieure et réexécutez le cmdlet(s).
    
- **Problème : Vous recevez le message d’erreur suivant « Dismount-WindowsImage : Dismount-WindowsImage a échoué. Code d’erreur = 0xc1550115 » lors de l’installation ou la mise à niveau d’édition de connecteur de nuage.**
    
    **Résolution :** Lancez une console PowerShell en tant qu’administrateur, exécutez « DISM-Cleanup-Wim' ». Il nettoie toutes les images d’état. Réexécutez Install-CcAppliance ou attendez que les bits de la mise à niveau automatique.
    
- **Problème : Déploiement de l’application connecteur du Cloud dans un environnement haute disponibilité échoue**
    
    **Résolution :** Les étapes à que suivre varient selon la raison de l’échec du déploiement :
    
  - Si la première appliance de nuage connecteur échoue et que vous ne peut pas déterminer la cause de l’échec, vous devez installer la solution matérielle-logicielle de nouveau jusqu'à ce que le déploiement a réussi et puis installer les autres appliances.
    
  - En cas d’échec de la première application de connecteur de nuage avec un problème mineur, tel qu’un problème de certificat externe, vous pourrez peut-être résoudre le problème sans installer de nouveau l’application. Vous pouvez ensuite utiliser client distant PowerShell pour marquer le déploiement comme étant réussie comme suit. (Vous pouvez également utiliser les étapes suivantes si le premier déploiement a réussi, mais, pour une raison quelconque, connecteur de nuage ne signale pas le déploiement comme étant réussi.)
    
  - Pour obtenir l’identité (GUID) de la première application de connecteur de nuage, exécutez l’applet de commande Get-CsHybridPSTNAppliance.
    
  - Pour marquer l’application déployée a réussi, exécutez le jeu-CsCceApplianceDeploymentStatus comme suit :
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- 
    
    **Problème : Vous devez vérifier et installer les mises à jour de Windows manuellement sur le serveur hôte ou les machines virtuelles.**
    
    **Résolution ** Nous vous conseillons de profiter des avantages des mises à jour automatiques du système d’exploitation fournies par la version Cloud Connector de Skype Entreprise. Une fois qu’un appareil est inscrit pour une gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifieront et installeront automatiquement les mises à jour de Windows en fonction des paramètres d’heure de mise à jour du système d’exploitation.
    
    Si vous devez vérifier et installer les mises à jour de Windows manuellement, suivez les étapes de cette rubrique qui s’appliquent à votre type de déploiement. Vous devriez mettre à jour le serveur hôte en même temps que les machines virtuelles qui sont exécutées dessus pour réduire le temps d’arrêt nécessaire aux mises à jour.
    
    Si vous préférez, vous pouvez utiliser un serveur WSUS (services de mises à jour de serveur Windows) pour qu’il fournisse les mises à jour aux serveurs Cloud Connector. Assurez-vous simplement de configurer Windows Update de sorte qu’il n’effectue **pas** d’installation automatique.
    
    Pour en savoir plus sur la mise à jour de votre déploiement Cloud Collector manuellement, consultez la rubrique suivante.
    
- 
    
    **Problème : Connecteur de nuage mises à jour vers une nouvelle version, les cmdlets de connecteur de nuage ne sont pas mis à jour.** Cela se produit parfois si une fenêtre PowerShell est laissée ouverte lors de la mise à jour automatique se produit.
    
    **Résolution :** Pour charger les applets de commande mises à jour, vous pouvez effectuer une des étapes suivantes :
    
  - Fermez PowerShell sur l’appliance de connecteur du nuage et puis rouvrez PowerShell.
    
  - Ou bien, vous pouvez exécuter le Module d’importation CloudConnector-Force. 
    
## <a name="install-windows-updates-manually"></a>Installer manuellement les mises à jour Windows

Si vous ne voulez pas utiliser les mises à jour automatiques dans votre environnement, suivez ces étapes pour vérifier et appliquer manuellement les mises à jour de Windows. Vérifier et installer manuellement les mises à jour de Windows nécessite de redémarrer le serveur. Lorsqu’un serveur est redémarré, les utilisateurs ne sera pas en mesure d’utiliser le connecteur du nuage pour placer ou recevoir des appels. Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler quand elles ont lieu, puis redémarrer les machines au besoin au moment de votre choix pour éviter une perturbation des services.
  
Pour vérifier et installer manuellement les mises à jours, connectez-vous à chaque serveur hôte et ouvrez le **Panneau de contrôle**. Sélectionnez **système et sécurité \>mise à jour de Windows**, puis gérer les mises à jour et redémarrage du serveur en fonction de votre environnement.
  
- S’il n’existe qu’un seul appareil sur le site, connectez-vous à chaque machine virtuelle et ouvrez le **Panneau de contrôle**. Sélectionnez **système et sécurité \>mise à jour de Windows**, puis configurer les mises à jour et redémarrage du serveur comme il convient.
    
- S’il existe plusieurs appareils sur le site, l’instance en cours de mise à jour et de redémarrage n’est plus accessible par les utilisateurs. Les utilisateurs se connecteront à d’autres instances du déploiement jusqu’à ce que toutes les machines virtuelles et que tous les services Skype Entreprise démarrent sur les machines virtuelles après la fin des mises à jour. Pour éviter de potentielles perturbations du service, vous pouvez supprimer les instances de la haute disponibilité pendant que vous appliquez les mises à jour, puis les restaurer une fois celles-ce achevées. Pour ce faire :
    
1. Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.
    
2. Supprimez l’instance de la haute disponibilité à l’aide de l’applet de commande suivante :
    
  ```
  Enter-CcUpdate
  ```

3. 
    
    Suivez la procédure applicable à une instance unique pour installer manuellement les mises à jour et redémarrer la machine virtuelle.
    
4. Définissez à nouveau l’instance en haute disponibilité grâce à l’applet de commande suivante :
    
  ```
  Exit-CcUpdate
  ```

Pour des déploiements sur plusieurs sites, suivez les étapes pour un site unique pour chaque site du déploiement, en appliquant les mises à jour un site à la fois.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Conseils lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte de connecteur de nuage

Si vous avez besoin installer un logiciel antivirus sur l’ordinateur hôte de connecteur de nuage, vous devez ajouter les exclusions suivantes :
  
- Répertoire de la solution matérielle-logicielle local sur chaque ordinateur.
    
- Annuaire de sites à distance sur chaque ordinateur.
    
- Répertoire du Site local sur l’ordinateur héberge le dossier racine du site partagé.
    
- %ProgramFiles%\Skype pour connecteur de Cloud Business Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Le processus Microsoft.Rtc.CCE.ManagementService.exe.
    

