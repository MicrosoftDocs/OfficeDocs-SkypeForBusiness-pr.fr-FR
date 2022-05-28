---
title: Créer une image Salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article explique comment configurer la console Salles Microsoft Teams et ses périphériques.
ms.openlocfilehash: d3c4f534fbd5395c7e0cda8e095b5a6d7a2b8def
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761256"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Créer une image Salles Microsoft Teams

Cet article explique comment créer une image Salles Microsoft Teams pour le déploiement en masse de salles Teams.

> [!NOTE]
> Les étapes suivantes doivent être utilisées uniquement lors de la création d’une [image WIM](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) pour le déploiement en masse. Si vous récupérez des appareils individuels, contactez votre fabricant d’équipement d’origine (OEM) pour obtenir de l’aide.

Vous ne devez effectuer ces étapes que si les comptes Microsoft Teams ou Skype Entreprise et Exchange nécessaires ont déjà été créés et testés, comme décrit dans [Deploy Salles Microsoft Teams](rooms-deploy.md). Vous aurez besoin du matériel et des logiciels décrits dans [Salles Microsoft Teams exigences](requirements.md). Cette rubrique contient les sections suivantes :
  
- [Préparer le support d’installation](console.md#Prep_Media)
- [Installer un certificat d’autorité de certification privée sur la console](console.md#Certs)
- [Installer Windows 10 et l’application console Salles Microsoft Teams](console.md#Reimage)
- [Configuration initiale de la console](console.md#Initial)
- [liste de contrôle de déploiement Salles Microsoft Teams](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Préparer le support d’installation
<a name="Prep_Media"> </a>

L’installation de l’application console Salles Microsoft Teams nécessite un périphérique de stockage USB avec au moins 32 Go de capacité. Il ne doit pas y avoir d’autres fichiers sur l’appareil ; tous les fichiers existants sur le stockage USB seront perdus.
  
> [!NOTE]
> Si vous ne créez pas votre support d’installation Salles Microsoft Teams conformément à ces instructions, vous risquez de provoquer un comportement inattendu.

> [!NOTE]
> Le processus ci-dessous consiste à créer un support d’installation pour imager de nouveaux appareils Salles Microsoft Teams. Par défaut, les appareils existants sont mis à jour automatiquement à partir de Windows Update et du Windows Store.

> [!IMPORTANT]
> La machine Windows 10 utilisée pour créer le support d’installation Salles Microsoft Teams doit se trouver sur la même version ou ultérieure de Windows que le support d’installation cible.
  
1. Téléchargez le [ scriptCreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.
3. Suivez les instructions du script pour créer un Salles Microsoft Teams disque d’installation USB.


> [!TIP]
> Chaque fois que le script CreateSrsMedia.ps1 démarre, la sortie d’écran inclut le nom d’un fichier journal ou d’une transcription pour la session. Si vous rencontrez des problèmes lors de l’exécution du script, veillez à disposer d’une copie de cette transcription disponible lors de la demande de support. 

Le script CreateSrsMedia.ps1 automatise les tâches suivantes :

1. Téléchargez le dernier programme d’installation MSI pour Salles Microsoft Teams.
2. Déterminez la build de Windows que l’utilisateur doit fournir. Les versions les plus récentes peuvent ou non être testées et prises en charge pour une utilisation avec des appareils Salles Microsoft Teams.
3. Téléchargez les composants de prise en charge nécessaires.
4. Assemblez les composants nécessaires sur le support d’installation.

> [!NOTE]
Une version spécifique de Windows 10 est requise, et cette version est disponible uniquement pour les clients de licences en volume.  Vous pouvez obtenir une copie à partir du [Centre de gestion des licences en volume](https://www.microsoft.com/Licensing/servicecenter/).

Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et passez à [installer Windows 10 et l’application console Salles Microsoft Teams](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installer Windows 10 et l’application console Salles Microsoft Teams
<a name="Reimage"> </a>

Vous devez maintenant appliquer le support d’installation que vous avez créé. L’appareil cible s’exécute en tant qu’appliance et l’utilisateur par défaut est défini pour exécuter uniquement l’application Salles Microsoft Teams.

1. Si l’appareil cible est installé dans une station d’accueil (par exemple, un Surface Pro), déconnectez-le du dock.

2. Vérifiez que l’appareil cible n’est pas connecté au réseau.

3. Vérifiez que l’appareil cible est connecté à l’alimentation ac.

4. Branchez votre disque d’installation USB sur l’appareil cible.

5. Démarrez sur le disque d’installation USB. Reportez-vous aux instructions de fabricant. Si votre appareil cible est un Surface Pro, procédez comme suit pour démarrer sur le disque d’installation USB :

    a. Appuyez et maintenez le bouton volume enfoncé (-).

    b. Appuyez et relâchez le bouton d’alimentation.

    c. Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).

8. Le système s’arrête une fois l’installation terminée.
    
Une fois le système arrêté, il est sûr de supprimer le disque d’installation USB. À ce stade, vous pouvez placer l’appareil cible dans son dock (si vous utilisez un produit basé sur un dock), attacher les périphériques nécessaires à votre salle de réunion et vous connecter au réseau. Reportez-vous aux instructions de fabricant.

> [!NOTE]
> Les mises à jour logicielles pour Salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises. Consultez [les prérequis pour Microsoft Store pour Entreprises et Éducation](/microsoft-store/prerequisites-microsoft-store-for-business) pour vérifier que la console de salle sera en mesure d’accéder au magasin et d’effectuer une mise à jour automatique.  

### <a name="selecting-a-language"></a>Sélection d’une langue 

Dans La mise à jour du créateur, vous devez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans les scénarios où la sélection implicite de la langue ne fournit pas à l’utilisateur la langue réelle de l’application souhaitée (par exemple, il souhaite que l’application console soit disponible en Français, mais qu’elle soit disponible en anglais).
  
> [!NOTE]
> Les instructions suivantes fonctionnent uniquement pour les consoles créées à l’aide de la mise à jour du créateur Windows (Windows 10 20H1) ou ultérieure.
  
### <a name="to-apply-your-desired-language"></a>Pour appliquer la langue de votre choix

1. Passez en mode Administrateur.
    
2. Sélectionnez le menu Démarrer.
    
3. Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .
    
4. Sélectionnez **La langue de l’heure&amp;**.
    
5. Sélectionnez **la langue**.
    
6. Sélectionnez **Ajouter une langue**.
    
7. Sélectionnez la langue que vous souhaitez ajouter.
    
8. Installez les fonctionnalités de langage.
    
9. Ne cochez pas Définir comme langue d’affichage Windows.
    
10. Sélectionnez **Installer**.
    
11. Sélectionnez la langue que vous venez d’ajouter à la liste « Langues ».
    
12. Définir comme valeur par défaut : déplacer la flèche vers le haut pour définir la valeur par défaut

13. Pour supprimer une langue :
    
    a. Sélectionnez la langue que vous souhaitez supprimer.
    
    b. Sélectionnez Supprimer.

14. Lancez une invite de commande avec élévation de privilèges.

15. Exécutez la commande suivante : 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. Redémarrez le système.
    
La langue souhaitée est désormais appliquée à la console Salles Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Configuration initiale de la console
<a name="Initial"> </a>

Une fois Windows installée, l’application Salles Microsoft Teams passe à son processus d’installation initial.
  
1. L’écran Compte d’utilisateur apparaît. Entrez l’adresse de connexion du compte Microsoft Exchange Resource (au format user@domain) du compte de salle à utiliser avec la console.
    
2. Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.
   
3. Sélectionnez le mode de réunion pris en charge : Microsoft Teams uniquement, Skype Entreprise uniquement, ou l’une des deux options en mode mixte. Si nécessaire, activez l’authentification moderne.

4. Sélectionnez **Suivant**.
    
5. Si vous utilisez Skype Entreprise et si le domaine SIP Skype Entreprise est différent du domaine Exchange de l’utilisateur, définissez le nom de domaine complet pour le Skype Entreprise Server dans la section Avancé. Si vous n’utilisez pas Skype Entreprise ou si le domaine SIP correspond au domaine Exchange, laissez cette section vide.
6. Sélectionnez **Suivant**.
    
7. Sélectionnez **Terminer**.
    
L’application Salles Microsoft Teams doit se connecter à Microsoft Teams ou Skype Entreprise Server avec les informations d’identification entrées ci-dessus, et doit également commencer à synchroniser son calendrier avec Exchange à l’aide de ces mêmes informations d’identification. Pour plus d’informations sur l’utilisation de salles Teams, reportez-vous à [l’aide Salles Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salles Microsoft Teams s’appuie sur la présence de matériel de console certifié. Même une image correctement créée contenant l’application console Salles Microsoft Teams ne démarre pas après la procédure d’installation initiale, sauf si le matériel de la console est détecté. Pour Surface Pro solutions basées, le Surface Pro doit être connecté à son matériel d’ancrage associé pour passer cette vérification.
  
> [!NOTE]
> Certains utilisateurs non anglophones peuvent avoir besoin d’un clavier physique connecté à la console lors de l’installation initiale si les symboles ne sont pas pris en charge sur le clavier tactile.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installer un certificat d’autorité de certification privée sur la console
<a name="Certs"> </a>
> [!NOTE]
> Ce qui suit s’applique uniquement si vous connectez salles Teams à Skype Entreprise.

Salles Microsoft Teams doit approuver les certificats utilisés par les serveurs auxquels il se connecte. Dans le cas où l’autorité de certification est privée, par exemple un déploiement local avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat à Salles Microsoft Teams de deux manières :
  
- Vous pouvez joindre la console à Active Directory et ajouter automatiquement les certificats requis, étant donné que l’autorité de certification est publiée sur Active Directory (option de déploiement normal).
    
- Vous pouvez installer le certificat manuellement après le processus de création d’image. Avant d’effectuer cette opération, vous devez terminer [la configuration initiale de la console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Pour installer manuellement le certificat 

1. Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Placez la console en mode administrateur (voir [Administration mode et gestion des appareils](rooms-operations.md#AdminMode)).
    
3. Exécutez la commande suivante :
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Joindre un domaine Active Directory (facultatif)
<a name="Certs"> </a>

Vous pouvez joindre Salles Microsoft Teams à votre domaine. Salles Microsoft Teams doivent être placées dans une unité d’organisation distincte de vos stations de travail PC, car de nombreuses stratégies de station de travail ne sont pas compatibles avec Salles Microsoft Teams. Un exemple courant est une stratégie d’application de mot de passe qui empêche Salles Microsoft Teams de démarrer automatiquement. Pour plus d’informations sur la gestion des paramètres d’objet de stratégie de groupe, [reportez-vous à Gérer les Salles Microsoft Teams](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Pour joindre Salles Microsoft Teams à un domaine

1. Connectez-vous à la console à partir du compte d’administrateur (voir [Administration mode et gestion des appareils](rooms-operations.md#AdminMode)).
    
2. Lancez l’invite de commande Powershell avec élévation de privilèges.
    
3. Saisissez la commande suivante dans Powershell :
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, ... ,OU=<Top level OU>,DC=<child domain>,...,DC=<top level domain>"
   ```

Par exemple, si votre domaine complet est redmond.corp.microsoft.com et que vous souhaitez que vos consoles Salles Microsoft Teams se trouve dans une unité d’organisation « Salles Microsoft Teams » enfant d’une unité d’organisation « Resources », la commande est :
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si vous souhaitez renommer l’ordinateur lors de sa jonction à un domaine, utilisez l’indicateur -NewName suivi du nouveau nom de l’ordinateur.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>liste de contrôle de déploiement Salles Microsoft Teams
<a name="Checklist"> </a>

Utilisez la liste de vérification suivante lors de la vérification finale que la console et tous ses périphériques sont entièrement configurés :
  
**Paramètres de l’application**

|Terminé |Vérifier |
|:-----:|:-----|
|☐   |Le nom du compte de salle et le numéro de téléphone (si PSTN est activé) sont correctement affichés   |
|☐   |Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).   |
|☐   |Le mot de passe du compte de l’administrateur est défini et vérifié.   |
|☐   |Toutes les mises à jour du microprogramme ont été appliquées   |
   
**Périphériques audio/vidéo**

|Terminé |Vérifier |
|:-----:|:-----|
|☐   |La version du microprogramme de la caméra est correcte (le cas échéant).   |
|☐   |Caméra fonctionnel et positionné de manière optimale   |
|☐   |Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.   |
|☐   |Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.   |
|☐   |La version du microprogramme du périphérique audio est correcte (le cas échéant).   |
|☐   |Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.   |
|☐   |Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.   |

**Console**

|Terminé |Vérifier |
|:-----:|:-----|
|☐   |Les câbles sont sécurisés et ne sont pas pincés.   |
|☐   |La réception audio via HDMI est fonctionnelle.   |
|☐   |La réception vidéo via HDMI est fonctionnelle.   |
|☐   |La console peut pivoter librement   |



   
## <a name="see-also"></a>Voir aussi
<a name="Checklist"> </a>

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)
