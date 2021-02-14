---
title: Déployer Microsoft Teams pour Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Découvrez comment installer et configurer l’application Teams pour Surface Hub afin que Teams soit l’application d’appels et de réunions par défaut.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 589bbfe75f0beea88066b5a6188b1d29c98ddd5f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905646"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Déployer Microsoft Teams pour Surface Hub
======================================

Avant d’installer Teams pour Surface Hub, assurez-vous de faire les choses suivantes :

 □ assurez-vous que le matériel, le système d’exploitation et les autres conditions requises sont respectées. Pour plus d’informations, voir le [guide d’administration de La Microsoft Surface Hub.](https://docs.microsoft.com/surface-hub/)<br>
 □ assurez-vous que la mise à jour minimale du système d’exploitation requise pour Teams est installée - [KB4343889.](https://support.microsoft.com/help/4343889)<br>
 □ attribuer une licence Teams au compte d’appareil Hub.<br>
 □ si vous faites la transition de Skype Entreprise Online, confirmez qu’une licence Teams est affectée à l’utilisateur.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installer Teams pour Surface Hub à partir du Microsoft Store 

Ces instructions s’utilisent pour installer Teams pour Surface Hub à partir du Microsoft Store. 
 
1. Démarrez le Microsoft Store :<br>
   a. Appuyez **sur**  >  **Démarrer tous les**  >  **paramètres de l’application.**<br> b. Appuyez **sur le compte d’appareil Surface Hub, gestion.**<br>
   c. Sur la gauche, appuyez sur **l’onglet Applications & Fonctionnalités.**<br> d. Sur la droite, appuyez sur **le bouton Ouvrir le** Store. 
2. Dans le Microsoft Store, recherchez *Microsoft Teams.* **Microsoft Teams pour Surface Hub** s’affiche. Appuyez sur **le bouton Obtenir l’application** pour l’installer.  
3. Une fois l’installation terminée, redémarrez le Surface Hub. 

> [!NOTE]
> N’appuyez **pas sur Lancer à** partir de la page de la liste dans le Store.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Faire de Teams l’application d’appels et de réunions par défaut
 
Il existe deux options pour configurer la stratégie d’application par défaut pour les appels et les réunions : 

- **Option 1**: configurer via une clé USB. 
- **Option 2**: configurer via la gestion des appareil photo tels qu’Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Option 1 : configurer via une clé USB 
 
Vous pouvez trouver les packages sur cette [page de téléchargement.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) Sélectionnez le package approprié pour le package que vous envisagez d’installer et copiez-le sur une clé USB. Le fichier .ppkg correct à utiliser dépend de la stratégie d’application par défaut que vous voulez appliquer comme suit : 

|Numéro  |Description  |
|---------|---------|
|0     | Application Skype préférée sur l’écran de démarrage, Réunions Teams disponible        |
|1     | Application teams préférée sur l’écran de démarrage, Réunions Skype disponible        |
|2     | Application exclusive Teams sur l’écran de démarrage (l’application Skype n’est pas disponible)        |
 
1. Branchez la clé USB à l’appareil Surface Hub. 
2. Ouvrez **l’application Paramètres** sur un appareil Surface Hub. 
3. Ouvrez **la gestion des comptes d’appareil Surface Hub.**
4. Ouvrez **la gestion des appareils.** 
5. Cliquez **sur Ajouter ou supprimer un package d’approvisionnement.** 
6. Cliquez **sur Ajouter un package.**
7. Sélectionnez **l’option de** média amovible dans le menu déroulant. 
8. Ajoutez le package <strong>TeamsRTMMode*.ppkg</strong> approprié précédemment copié sur la clé USB. 
9. Redémarrez l’appareil Surface Hub. 
10. Après le redémarrage de l’appareil, vous devriez être en mesure de démarrer l’application Teams à partir de l’écran de démarrage et de rejoindre une réunion à partir du calendrier. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Option 2 : configurer via la gestion des appareil photo tels que Intune 

Utilisez la procédure suivante pour configurer la stratégie d’application par défaut pour les appels et les réunions via Intune. Consultez également le blog sur [le déploiement de l’application Microsoft Teams pour Surface Hub à l’aide d’Intune.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|Paramètres   |Valeur    |Description    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Type de données | integer (0-2)   |0 - Application Skype préférée sur l’écran de démarrage, Réunions Teams disponible<br>1 - Application teams préférée sur l’écran de démarrage, Réunions Skype disponible<br>2 - Application exclusive Teams sur l’écran de démarrage (l’application Skype n’est pas disponible) |
|Opérations| Obtenir, Définir        |

|Paramètres   |Valeur    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Type de données | string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Opérations| Obtenir, Définir        |

Redémarrez l’appareil Surface Hub. Après le redémarrage de l’appareil, vous devriez être en mesure de démarrer l’application Teams à partir de l’écran de démarrage et de rejoindre une réunion à partir du calendrier.

