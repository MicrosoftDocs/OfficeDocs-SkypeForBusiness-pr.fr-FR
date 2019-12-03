---
title: Configurer une console de salle Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Cet article décrit la configuration de la console salles de Microsoft teams et de ses périphériques.
ms.openlocfilehash: fd09d7e9d70a5912469d4ed2d79a4dc8f465eeb6
ms.sourcegitcommit: 486eaa85042670edec2231efaf7dae8fa329e852
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2019
ms.locfileid: "39665437"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurer une console de salle Microsoft teams

Cet article décrit la configuration de la console salles de Microsoft teams et de ses périphériques.
  
Vous devez effectuer cette procédure uniquement si les comptes Microsoft teams ou Skype entreprise et Exchange requis ont déjà été créés et testés comme décrit dans la rubrique [déploiement de salles de Microsoft teams](room-systems-v2.md). Vous aurez besoin du matériel et du logiciel décrits dans la [Configuration requise dans Microsoft teams](requirements.md). Cette rubrique contient les sections suivantes :
  
- [Préparer le support d’installation](console.md#Prep_Media)
- [Installer un certificat d’autorité de certification privée sur la console](console.md#Certs)
- [Installation de Windows 10 et de l’application de console Microsoft teams](console.md#Reimage)
- [Configuration initiale de la console](console.md#Initial)
- [Liste de vérification de déploiement de Microsoft teams](console.md#Checklist)

> [!NOTE]
> Les salles de Microsoft teams fonctionneront uniquement dans un environnement Microsoft teams ou Skype entreprise correctement configuré pour lequel les comptes de périphériques sont correctement configurés comme décrit dans la rubrique [déploiement de salles Microsoft teams](room-systems-v2.md).
  
## <a name="prepare-the-installation-media"></a>Préparer le support d’installation
<a name="Prep_Media"> </a>

L’installation de l’application Microsoft teams salle console nécessite un périphérique de stockage USB doté d’au moins 32 Go de capacité. Il n’y a pas d’autres fichiers sur l’appareil ; tout fichier existant sur le stockage USB sera perdu.
  
> [!NOTE]
> L’impossibilité de créer votre support d’installation de Microsoft Teams (en vertu de ces instructions) peut entraîner un comportement inattendu.

> [!NOTE]
> Le processus ci-dessous consiste à créer un support d’installation pour l’image des nouveaux appareils Microsoft Teams. Par défaut, les appareils existants sont automatiquement mis à jour à partir de Windows Update et du Windows Store.

> [!IMPORTANT]
> Sur un ordinateur Windows 10, le média d’installation de Microsoft teams se trouve sur la même version ou une version ultérieure.
  
1. Téléchargez le [script CreateSrsMedia. ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Exécutez le script CreateSrsMedia.ps1 à partir d'une invite avec élévation de privilèges sur un ordinateur Windows 10.
3. Suivez les instructions du script pour créer un disque de configuration USB Microsoft Teams.


> [!TIP]
> Chaque fois que le script CreateSrsMedia. ps1 démarre, la sortie écran inclut le nom d’un fichier journal ou d’une transcription de la session. Si vous rencontrez des problèmes lors de l’exécution du script, assurez-vous qu’une copie de cette transcription est disponible lors de la demande d’assistance. 

Le script CreateSrsMedia. ps1 automatise les tâches suivantes :

1. Téléchargez la dernière version du programme d’installation MSI pour les salles de Microsoft Teams.
2. Déterminez la version de Windows que l’utilisateur doit fournir. Les versions les plus récentes sont susceptibles de ne pas être testées et prises en charge pour une utilisation avec des appareils Microsoft Teams.
3. Téléchargez les composants d’assistance nécessaires.
4. Assemblez les composants nécessaires sur le support d’installation.

Une version spécifique de Windows 10 est requise, et cette version n’est disponible que pour les clients du programme de licence en volume.  Vous pouvez obtenir une copie via le [Centre](https://www.microsoft.com/Licensing/servicecenter/)de gestion des licences en volume.

Lorsque vous avez terminé, supprimez le disque USB de votre ordinateur, puis procédez à [l’installation de Windows 10 et de l’application console de Microsoft teams](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Installation de Windows 10 et de l’application de console Microsoft teams
<a name="Reimage"> </a>

Vous devez maintenant appliquer le média de configuration que vous avez créé. L’appareil cible sera exécuté en tant que matériel et l’utilisateur par défaut sera configuré pour exécuter l’application console Microsoft teams uniquement.

1. Si l’appareil cible doit être installé dans un dock (par exemple, surface Pro), débranchez-le du Dock.

2. Assurez-vous que l’appareil cible n’est pas connecté au réseau.

3. Assurez-vous que l’appareil cible est connecté à une alimentation ca.

4. Branchez le disque de configuration USB dans l’appareil cible.

5. Démarrez sur le disque de configuration USB. Reportez-vous aux instructions de fabricant. S’il s’agit d’un appareil cible, utilisez les étapes suivantes pour démarrer l’installation sur le disque de configuration USB :

    a. Appuyez de façon prolongée sur le bouton du volume (-).

    b. Appuyez et relâchez le bouton d’alimentation.

    c. Une fois l’installation Windows démarrée, relâchez le bouton de diminution du volume (-).

8. Le système s’arrêtera une fois l’installation terminée.
    
Une fois le système arrêté, il est sûr de supprimer le disque de configuration USB. À ce stade, vous pouvez placer l’appareil cible dans sa station d’accueil (si vous utilisez un produit d’une station d’accueil), joindre les périphériques nécessaires à votre salle de réunion et vous connecter au réseau. Reportez-vous aux instructions de fabricant.

> [!NOTE]
> Les mises à jour logicielles des salles de Microsoft teams sont téléchargées automatiquement à partir du Microsoft Store pour entreprises. Voir les [conditions préalables pour le Microsoft Store pour les entreprises et l’éducation](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) pour vérifier que la console de salle est en mesure d’accéder au Windows Store et à la mise à jour automatique.  

### <a name="selecting-a-language"></a>Sélectionner une langue 

Dans la mise à jour du créateur, vous devez utiliser le script ApplyCurrentRegionAndLanguage. ps1 dans les scénarios dans lesquels la sélection de la langue implicite ne fournit pas à l’utilisateur la langue réelle de l’application (par exemple, l’application de la console peut se trouver en français, mais ce service est disponible en anglais).
  
> [!NOTE]
> Les instructions suivantes ne fonctionnent pas pour les consoles créées à l’aide de la mise à jour du créateur Windows. Les systèmes traditionnels/inactifs qui n’ont pas été configurés à l’aide de médias avec le nouveau système de mise en service ne seront pas en mesure d’utiliser ces instructions, mais qui ne font pas partie du problème initial qui nécessite cette intervention manuelle (édition anniversaire).
  
### <a name="to-apply-your-desired-language"></a>Pour appliquer la langue de votre choix

1. Passez en mode Administrateur.
    
2. Sélectionnez le menu Démarrer.
    
3. Sélectionnez l'icône d'engrenage pour lancer l'application **Paramètres** .
    
4. Sélectionnez **Time &amp; Language**.
    
5. Sélectionner **la &amp; langue de région**.
    
6. Sélectionnez **Ajouter une langue**.
    
7. Sélectionnez la langue que vous souhaitez ajouter.
    
8. Sélectionnez la langue que vous venez d’ajouter à la liste « langues ».
    
9. Sélectionnez **Définir par défaut**.
    
10. Pour supprimer une langue :
    
    a. Sélectionnez la langue que vous souhaitez supprimer.
    
    b. Sélectionnez **Supprimer**.
    
11. Lancez une invite de commande avec élévation de privilèges.
    
12. Exécutez la commande suivante : 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Redémarrez le système.
    
La langue souhaitée est désormais appliquée à la console Microsoft teams salles.
## <a name="initial-set-up-of-the-console"></a>Configuration initiale de la console
<a name="Initial"> </a>

Après l’installation de Windows, l’application console de Microsoft teams se trouve dans le processus de configuration initial lors du démarrage suivant ou si l’option/reboot a été choisie.
  
1. L’écran Compte d’utilisateur apparaît. Entrez l’adresse de connexion de Skype (en user@domain format) du compte de la salle à utiliser avec la console.
    
2. Saisissez le mot de passe du compte de la salle dé réunion, puis saisissez-le à nouveau à des fins de vérification.
    
3. Sous « configurer le domaine », définissez le FQDN du serveur Skype entreprise. Si le domaine SIP de Skype entreprise est différent de celui du domaine Exchange de l’utilisateur, entrez le domaine Exchange dans ce champ.
    
4. Cliquez sur **Suivant**.
    
5. Sélectionnez les périphériques indiqués sur l’écran fonctionnalités, puis cliquez sur **suivant**. Le défaut est d’avoir la partage d’écran automatique activé alors que les noms de réunion masqués sont désactivés. Les appareils à sélectionner sont les suivants :
    
   - Microphone pour les conférences : le microphone par défaut  pour cette salle de conférence.
    
   - Haut-parleur pour les conférences : le haut-parleur par défaut pour les conférences.  
    
   - Haut-parleur par défaut : le haut-parleur utilisé pour l’audio à partir de la réception HDMI.
    
     Chaque option possède un menu déroulant d’options à sélectionner. Vous devez effectuer une sélection pour chaque appareil.
    
6. Cliquez sur **Terminer**.
    
Dans l’application Microsoft teams de Microsoft Teams, l’application doit commencer immédiatement à se connecter à Skype entreprise Server avec les informations d’identification entrées ci-dessus, et doit également commencer à synchroniser son calendrier avec Exchange en utilisant ces mêmes informations d’identification. Pour plus d’informations sur l’utilisation de l’application console, voir l' [aide de Microsoft teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Les salles de Microsoft teams sont basées sur la présence de matériel de console certifié. Même une image correctement créée contenant l’application console de Microsoft Teams ne démarre pas après la procédure de configuration initiale, sauf si le matériel de la console est détecté. Pour les solutions basées sur les périphériques de surface, l’apparence de surface Pro doit être connectée au matériel d’accueil associé pour réussir ce contrôle.
  
> [!NOTE]
> Certains utilisateurs de langues autres que l’anglais peuvent avoir besoin d’un clavier physique connecté à la console lors de la configuration initiale dans le cas où ces symboles ne sont pas pris en charge sur le clavier visuel.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Installer un certificat d’autorité de certification privée sur la console
<a name="Certs"> </a>

La console Microsoft teams salles doit faire confiance aux certificats utilisés par les serveurs auxquels elle est connectée. Dans un environnement O365, cette opération est effectuée de manière automatique, car ces serveurs utilisent des autorités de certification publiques automatiquement approuvées par Windows 10. Dans le cas où l’autorité de certification est privée, par exemple un déploiement local avec Active Directory et l’autorité de certification Windows, vous pouvez ajouter le certificat à la console de Microsoft teams :
  
- Vous pouvez joindre la console à Active Directory et ajoutera automatiquement les certificats requis pour les autorités de certification publiées dans Active Directory (option de déploiement normale).
    
- Vous pouvez installer le certificat manuellement après le processus de création d’image. Avant cela, vous devez terminer [la configuration initiale de la console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Pour installer manuellement le certificat 

1. Téléchargez le certificat d’AC sur votre ordinateur, puis enregistrez-le sur "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Placez la console en mode administrateur (voir [mode administrateur et gestion des appareils](room-systems-v2-operations.md#AdminMode)).
    
3. Exécutez la commande suivante :
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Rejoindre un domaine Active Directory (facultatif)
<a name="Certs"> </a>

Vous pouvez joindre des consoles de Microsoft teams à votre domaine. Les consoles de salle Microsoft teams doivent être placées dans une unité d’organisation distincte de celle de votre ordinateur, car de nombreuses stratégies de station de travail ne sont pas compatibles avec les salles de Microsoft Teams. Un exemple courant est une stratégie de mise en application de mot de passe qui empêche le démarrage automatique de Microsoft Teams. Pour plus d’informations sur la gestion des paramètres d’objets de stratégie de groupe, voir [gérer les salles de Microsoft teams](room-systems-v2-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Pour joindre des salles de Microsoft teams à un domaine

1. Connectez-vous à la console à partir du compte d’administrateur (voir [mode administrateur et gestion des appareils](room-systems-v2-operations.md#AdminMode)).
    
2. Lancez l’invite de commande Powershell avec élévation de privilèges.
    
3. Saisissez la commande suivante dans Powershell :
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Par exemple, si votre domaine complet est redmond.corp.microsoft.com et que vous voulez que les consoles de Microsoft teams se trouvent dans une UO « Microsoft teams » qui est un enfant d’une unité d’organisation « Resources », la commande sera :
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si vous souhaitez renommer l’ordinateur lorsque vous le Rejoignez à un domaine, utilisez l’indicateur-NewName suivi du nouveau nom de l’ordinateur.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Liste de vérification de déploiement de Microsoft teams
<a name="Checklist"> </a>

Utilisez la liste de vérification suivante tout en effectuant une vérification finale, la console et tous ses périphériques sont entièrement configurés :
  
**Paramètres de l’application**

|||
|:-----|:-----|
|☐  <br/> |Le nom de compte et le numéro de téléphone de la salle de réunion (si la fonction PSTN est activée) sont correctement affichés dans la partie supérieure droite de l’écran de la console.  <br/> |
|☐  <br/> |Le nom de l’ordinateur Windows est correctement défini (utile pour l’administration à distance).  <br/> |
|☐  <br/> |Le mot de passe du compte de l’administrateur est défini et vérifié.  <br/> |
|☐  <br/> |Toutes les mises à jour de microprogrammes ont été appliquées.  <br/> |
   
**Périphériques audio/vidéo**

|||
|:-----|:-----|
|☐  <br/> |La version du microprogramme de la caméra est correcte (le cas échéant).  <br/> |
|☐  <br/> |Fonctionnement de la caméra et positionnement optimal  <br/> |
|☐  <br/> |Les paramètres des périphériques de lecture et de communication par défaut sont définis sur les périphériques audio choisis.  <br/> |
|☐  <br/> |Les paramètres du périphérique d’enregistrement de communication par défaut est défini sur le périphérique audio choisi.  <br/> |
|☐  <br/> |La version du microprogramme du périphérique audio est correcte (le cas échéant).  <br/> |
|☐  <br/> |Le périphérique d’entrée audio est fonctionnel et positionné de manière optimale.  <br/> |
|☐  <br/> |Le périphérique de sortie audio est fonctionnel et positionné de manière optimale.  <br/> |
   
**Dock**

|||
|:-----|:-----|
|☐  <br/> |Les câbles sont sécurisés et ne sont pas pincés.  <br/> |
|☐  <br/> |La réception audio via HDMI est fonctionnelle.  <br/> |
|☐  <br/> |La réception vidéo via HDMI est fonctionnelle.  <br/> |
|☐  <br/> |Le dock peut pivoter librement.  <br/> |
|☐  <br/> |La luminosité de l’affichage est acceptable pour l’environnement.  <br/> |
   
## <a name="see-also"></a>Voir aussi
<a name="Checklist"> </a>

[Plan pour les salles de Microsoft teams](skype-room-systems-v2-0.md)
  
[Déploiement de salles de Microsoft teams](room-systems-v2.md)
  
[Configurer une console de salle Microsoft teams](console.md)
  
[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)
