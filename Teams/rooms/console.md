---
title: Configurer une console des salles Microsoft Teams
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
description: Cet article décrit comment configurer et configurer la console Salles Microsoft Teams et ses périphériques.
ms.openlocfilehash: 0acd5449c97f1a42f1a1c015b74df8f7cdaf3e4c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011558"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurer une console des salles Microsoft Teams

Cet article décrit comment configurer la console Salles Microsoft Teams et ses périphériques.
  
Vous ne devez effectuer ces étapes que si les comptes Microsoft Teams ou Skype Entreprise et Exchange nécessaires ont déjà été créés et testés comme décrit dans Déployer des salles [Microsoft Teams.](rooms-deploy.md) Vous aurez besoin du matériel et du logiciel décrits dans la configuration [requise pour les salles Microsoft Teams.](requirements.md) Cette rubrique contient les sections suivantes :
  
- [Préparer le support d’installation](console.md#Prep_Media)
- [Installer un certificat d’autorisation d’certification privé sur la console](console.md#Certs)
- [Installer Windows 10 et l’application Salles Microsoft Teams](console.md#Reimage)
- [Mise en place initiale de la console](console.md#Initial)
- [Liste de contrôle du déploiement de salles Microsoft Teams](console.md#Checklist)

> [!NOTE]
> Salles Microsoft Teams ne fonctionne que dans un environnement Microsoft Teams ou Skype Entreprise correctement configuré où les comptes d’appareil sont correctement configurés, comme décrit dans Déployer les salles [Microsoft Teams.](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>Préparer le support d’installation
<a name="Prep_Media"> </a>

L’installation de l’application Salles Microsoft Teams nécessite un dispositif de stockage USB dont la capacité est d’au moins 32 Go. Aucun autre fichier ne doit être sur l’appareil. Tous les fichiers existants sur le stockage USB seront perdus.
  
> [!NOTE]
> L’échec de la création du support d’installation de salles Microsoft Teams en fonction de ces instructions peut entraîner un comportement inattendu.

> [!NOTE]
> Le processus ci-dessous a pour objectif de créer un support d’installation pour image de nouveaux appareils Microsoft Teams Rooms. Par défaut, les appareils existants sont mis à jour automatiquement à partir de Windows Update et du Windows Store.

> [!IMPORTANT]
> L’ordinateur Windows 10 utilisé pour créer le support d’installation de Salles Microsoft Teams doit être dans la même version ou ultérieure de Windows que le support d’installation cible.
  
1. Téléchargez le [scriptCreateSrsMedia.ps1'application.](https://go.microsoft.com/fwlink/?linkid=867842)
2. Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.
3. Suivez les instructions du script pour créer un disque de configuration USB de Microsoft Teams Rooms.


> [!TIP]
> Chaque fois que CreateSrsMedia.ps1 script principal démarre, la sortie à l’écran inclut le nom d’un fichier journal ou d’une transcription de la session. Si vous avez des problèmes lors de l’exécution du script, assurez-vous qu’une copie de cette transcription est disponible lorsque vous demandez de l’aide. 

Le CreateSrsMedia.ps1 script automatise les tâches suivantes :

1. Téléchargez le dernier programme d’installation MSI pour les salles Microsoft Teams.
2. Déterminez la build de Windows que l’utilisateur doit fournir. Il est possible que les versions les plus récentes ne soient pas testées et qu’elles soient prise en charge pour une utilisation avec les appareils Microsoft Teams Rooms.
3. Téléchargez les composants de prise en charge nécessaires.
4. Assemblez les composants nécessaires sur le support d’installation.

Une version spécifique de Windows 10 est requise, et cette version est uniquement disponible pour les clients de licence en volume.  Vous pouvez en obtenir une copie à partir du [Centre de gestion des licences en volume.](https://www.microsoft.com/Licensing/servicecenter/)

Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur et continuez à installer Windows 10 et l’application de [console Salles Microsoft Teams.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installer Windows 10 et l’application Salles Microsoft Teams
<a name="Reimage"> </a>

Vous devez à présent appliquer le support de configuration que vous avez créé. Le périphérique cible s’exécute sous la mesure d’une appliance et l’utilisateur par défaut est réglé pour exécuter uniquement l’application de console Salles Microsoft Teams.

1. Si l’appareil cible est installé dans une station d’accueil (par exemple, une Surface Pro), déconnectez-le de la station d’accueil.

2. Assurez-vous que l’appareil cible n’est pas connecté au réseau.

3. Assurez-vous que l’appareil cible est connecté à la puissance CA.

4. Branchez votre disque de configuration USB sur le périphérique cible.

5. Démarrez sur le disque de configuration USB. Reportez-vous aux instructions de fabricant. Si votre appareil cible est une Surface Pro, utilisez les étapes suivantes pour démarrer sur le disque de configuration USB :

    a. Appuyez sur le bouton de baisse du volume (-) et maintenez-le enfoncé.

    b. Appuyez sur le bouton d’alimentation et relâchez-le.

    c. Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).

8. Le système se ferme une fois l’installation terminée.
    
Une fois le système arrêté, vous risquez de supprimer le disque d’installation USB en toute sécurité. À ce stade, vous pouvez placer l’appareil cible dans sa station d’accueil (si vous utilisez un produit basé sur une station d’accueil), connecter les périphériques nécessaires à votre salle de réunion et vous connecter au réseau. Reportez-vous aux instructions de fabricant.

> [!NOTE]
> Les mises à jour logicielles des salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises. Consultez [les conditions préalables pour que Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business) pour Entreprises et Éducation vérifie que la console de salle sera en mesure d’accéder au Store et de se mettre à jour.  

### <a name="selecting-a-language"></a>Sélection d’une langue 

Dans la Mise à jour de l’application de créateur, vous devrez utiliser le script ApplyCurrentRegionAndLanguage.ps1 dans des scénarios où la sélection de langue implicite ne fournit pas à l’utilisateur la langue réelle de l’application qu’il souhaite (par exemple, il souhaite que l’application de console soit fournie en français, mais qu’elle soit en anglais).
  
> [!NOTE]
> Les instructions suivantes fonctionnent uniquement pour les consoles créées à l’aide de la Mise à jour du Créateur de Windows. Les systèmes hérités/sur le marché qui n’ont pas été configurés à l’aide du média avec le nouveau système de mise en service ne pourront pas utiliser ces instructions, mais ne doivent pas non plus être en raison du problème initial nécessitant cette intervention manuelle (l’édition anniversaire vous permet de sélectionner la langue de votre application explicitement dans le cadre de la configuration).
  
### <a name="to-apply-your-desired-language"></a>Pour appliquer la langue de votre choix

1. Passez en mode Administrateur.
    
2. Sélectionnez le menu Démarrer.
    
3. Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .
    
4. Sélectionnez **la langue &amp; de l’heure.**
    
5. Sélectionnez **la langue de la &amp; région.**
    
6. Sélectionnez **Ajouter une langue**.
    
7. Sélectionnez la langue que vous souhaitez ajouter.
    
8. Sélectionnez la langue que vous vient d’ajouter à la liste « Langues ».
    
9. Sélectionnez **Définir par défaut**.
    
10. Pour supprimer une langue :
    
    a. Sélectionnez la langue que vous souhaitez supprimer.
    
    b. Sélectionnez **Supprimer**.
    
11. Lancez une invite de commande avec élévation de privilèges.
    
12. Exécutez la commande suivante : 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Redémarrez le système.
    
La langue souhaitée est désormais appliquée à la console Salles Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Mise en place initiale de la console
<a name="Initial"> </a>

Une fois Windows installé, l’application de console Salles Microsoft Teams se lancera dans le processus de configuration initial au moment de la prochaine mise en place ou si l’option /redémarrage a été choisie.
  
1. L’écran Compte d’utilisateur apparaît. Entrez l’adresse de sign-in Skype (au format user@domain) du compte de salle à utiliser avec la console.
    
2. Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.
    
3. Sous « Configurer le domaine », définissez le nom de domaine (FQDN) pour le serveur Skype Entreprise. Si le domaine SIP Skype Entreprise est différent du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.
    
4. Cliquez sur **Suivant**.
    
5. Sélectionnez les appareils indiqués dans l’écran Fonctionnalités, puis cliquez **sur Suivant.** Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés. Les appareils à sélectionner sont les suivants :
    
   - Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.
    
   - Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences.  
    
   - Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.
    
     Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.
    
6. Cliquez sur **Terminer**.
    
L’application Salles Microsoft Teams doit commencer immédiatement à se connexion à Skype Entreprise Server avec les informations d’identification entrées ci-dessus, et doit également commencer à synchroniser son calendrier avec Exchange à l’aide des mêmes informations d’identification. Pour plus d’informations sur l’utilisation de l’application de console, consultez l’aide de [Salles Microsoft Teams.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Salles Microsoft Teams s’appuie sur la présence de matériel de console certifié. Même une image correctement créée contenant l’application de console Salles Microsoft Teams ne démarre pas au-delà de la procédure de configuration initiale, sauf si le matériel de la console est détecté. Pour les solutions Surface Pro, le Surface Pro doit être connecté à son matériel de la station d’accueil pour réussir cette vérification.
  
> [!NOTE]
> Certains utilisateurs non anglophones auront besoin d’un clavier physique connecté à la console lors de la configuration initiale si les symboles ne sont pas pris en charge sur le clavier tactile.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installer un certificat d’autorisation d’certification privé sur la console
<a name="Certs"> </a>

La console Salles Microsoft Teams doit faire confiance aux certificats utilisés par les serveurs avec qui elle se connecte. Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10. Dans le cas où l’autorité de certification est privée, par exemple un déploiement sur site avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat à la console Salles Microsoft Teams de deux façons :
  
- Vous pouvez rejoindre la console d’Active Directory et cela ajoutera automatiquement les certificats requis à la publication de l’autorité de certification dans Active Directory (option de déploiement normal).
    
- Vous pouvez installer le certificat manuellement après le processus de création d’image. Avant cela, vous devez effectuer la mise en place initiale [de la console.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>Pour installer manuellement le certificat 

1. Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Placez la console en mode d’administration (voir [Mode d’administration et gestion des appareils).](rooms-operations.md#AdminMode)
    
3. Exécutez la commande suivante :
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Joindre un domaine Active Directory (facultatif)
<a name="Certs"> </a>

Vous pouvez joindre des consoles salles Microsoft Teams à votre domaine. Les consoles Salles Microsoft Teams doivent être placées dans une station d’exploitation distincte de vos stations de travail PC, car de nombreuses stratégies de station de travail ne sont pas compatibles avec les salles Microsoft Teams. Les stratégies d’application de mot de passe qui empêchent microsoft Teams Rooms de démarrer automatiquement en sont un exemple courant. Pour plus d’informations sur la gestion des paramètres des GPO, voir [Gérer des salles Microsoft Teams.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Pour joindre salles Microsoft Teams à un domaine

1. Connectez-vous à la console à partir du compte d’administrateur (voir [mode Administrateur et gestion des appareils).](rooms-operations.md#AdminMode)
    
2. Lancez l’invite de commande Powershell avec élévation de privilèges.
    
3. Saisissez la commande suivante dans Powershell :
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Par exemple, si votre domaine complet est redmond.corp.microsoft.com et que vous souhaitez que vos consoles Salles Microsoft Teams se trouveront dans une ou « Salles Microsoft Teams » enfant d’une ou plusieurs « Ressources », la commande sera :
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si vous voulez renommer l’ordinateur lorsque vous rejoignez celui-ci en domaine, utilisez l’indicateur -NewName suivi du nouveau nom de l’ordinateur.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Liste de contrôle du déploiement de salles Microsoft Teams
<a name="Checklist"> </a>

Utilisez la liste de vérification suivante lors d’une vérification finale que la console et tous ses périphériques sont entièrement configurés :
  
**Paramètres de l’application**

|Terminé |Cochez |
|:-----:|:-----|
|☐   |Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.   |
|☐   |Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).   |
|☐   |Le mot de passe du compte de l’administrateur est défini et vérifié.   |
|☐   |Toutes les mises à jour du microprogramme ont été appliquées   |
   
**Périphériques audio/vidéo**

|Terminé |Cochez |
|:-----:|:-----|
|☐   |La version du microprogramme de la caméra est correcte (le cas échéant).   |
|☐   |Appareil photo fonctionnel et positionné de manière optimale   |
|☐   |Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.   |
|☐   |Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.   |
|☐   |La version du microprogramme du périphérique audio est correcte (le cas échéant).   |
|☐   |Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.   |
|☐   |Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.   |

**Dock**

|Terminé |Cochez |
|:-----:|:-----|
|☐   |Les câbles sont sécurisés et ne sont pas pincés.   |
|☐   |La réception audio via HDMI est fonctionnelle.   |
|☐   |La réception vidéo via HDMI est fonctionnelle.   |
|☐   |Le dock peut pivoter librement.   |
|☐   |La luminosité de l’affichage est acceptable pour l’environnement.   |


   
## <a name="see-also"></a>Voir aussi
<a name="Checklist"> </a>

[Planifier les Salles Microsoft Teams](rooms-plan.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)
