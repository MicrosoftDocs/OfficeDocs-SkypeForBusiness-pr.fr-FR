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
description: Découvrez comment installer et configurer l’application Teams for Surface Hub pour que Teams’application d’appel et de réunion par défaut.
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
ms.openlocfilehash: 38202fcbb4c2147baae3f745bc2455da6fdff3e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093934"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Déployer Microsoft Teams pour Surface Hub
======================================

Avant d’installer Teams pour Surface Hub, assurez-vous de faire les choses suivantes :

 □ assurez-vous que le matériel, le système d’exploitation et d’autres conditions sont satisfaits. Pour plus d’informations, voir le [guide Microsoft Surface Hub’administration des utilisateurs.](/surface-hub/)<br>
 □ assurez-vous que la mise à jour minimale du système d’exploitation requise pour Teams est installée - [KB4343889.](https://support.microsoft.com/help/4343889)<br>
 □ attribuer une licence Teams utilisateur au compte d’appareil Hub.<br>
 □ si vous faites la transition à partir de Skype Entreprise Online, confirmez qu’une licence Teams licence est affectée à l’utilisateur.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installer Teams pour l Surface Hub installer à partir du Microsoft Store 

Ces instructions s’Teams pour l Surface Hub à partir du Microsoft Store. 
 
1. Démarrez la Microsoft Store :<br>
   a. Appuyez **sur**  >  **Démarrer toutes les** applications  >  **Paramètres.**<br> b. Appuyez **Surface Hub Compte d’appareil, gestion.**<br>
   c. Sur la gauche, appuyez sur **l’onglet Applications & Fonctionnalités.**<br> d. Sur la droite, appuyez sur **le bouton Ouvrir le** Store. 
2. Dans la Microsoft Store, recherchez des *Microsoft Teams.* Les **Microsoft Teams de Surface Hub** s’affichent. Appuyez sur **le bouton Obtenir l’application** pour l’installer.  
3. Une fois l’installation terminée, redémarrez l’Surface Hub. 

> [!NOTE]
> N’appuyez **pas sur Lancer à** partir de la page de la liste dans le Store.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Faire de Teams’application d’appels et de réunions par défaut
 
Il existe deux options pour configurer la stratégie d’application par défaut pour les appels et les réunions : 

- **Option 1**: configurer via une clé USB. 
- **Option 2**: configurer via la gestion des appareil photo tels que Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Option 1 : configurer via une clé USB 
 
Vous pouvez trouver les packages sur cette [page de téléchargement.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) Sélectionnez le package approprié pour le package que vous envisagez d’installer et copiez-le sur une clé USB. Le fichier .ppkg correct à utiliser dépend de la stratégie d’application par défaut que vous voulez appliquer comme suit : 

|Numéro  |Description  |
|---------|---------|
|0     | Skype application préférée sur l’écran de démarrage, Teams réunions disponibles        |
|1     | Teams application préférée sur l’écran de démarrage, Skype réunions disponibles        |
|2     | Teams’application exclusive sur l’écran d’accueil (Skype app n’est pas disponible)        |
 
1. Branchez la clé USB à l Surface Hub appareil. 
2. Ouvrez **l Paramètres appappe** de messagerie sur un Surface Hub appareil. 
3. Ouvrez **Surface Hub gestion des comptes d’appareils.**
4. Ouvrez **la gestion des appareils.** 
5. Cliquez **sur Ajouter ou supprimer un package d’approvisionnement.** 
6. Cliquez **sur Ajouter un package.**
7. Sélectionnez **l’option de** média amovible dans le menu déroulant. 
8. Ajoutez le package <strong>TeamsRTMMode*.ppkg</strong> approprié précédemment copié sur la clé USB. 
9. Redémarrez le Surface Hub appareil. 
10. Après le redémarrage de l’appareil, vous devriez être en mesure de démarrer l’application Teams à partir de l’écran d’accueil et de participer à une réunion à partir du calendrier. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Option 2 : configurer via la gestion des appareil photo, par exemple, Intune 

Utilisez la procédure suivante pour configurer la stratégie d’application par défaut pour les appels et les réunions via Intune. Consultez également le blog sur [le déploiement Microsoft Teams’application Surface Hub à l’aide d’Intune.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|Paramètres   |Valeur    |Description    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Type de données | integer (0-2)   |0 - Skype application préférée sur l’écran de démarrage, Teams réunions disponibles<br>1 - Teams application préférée sur l’écran de démarrage, Skype réunions disponibles<br>2 - Teams’application exclusive sur l’écran d’accueil (Skype’application non disponible) |
|Opérations| Obtenir, Définir        |

|Paramètres   |Valeur    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Type de données | string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams** |
|Opérations| Obtenir, Définir        |

Redémarrez le Surface Hub appareil. Après le redémarrage de l’appareil, vous devriez être en mesure de démarrer l’application Teams à partir de l’écran d’accueil et de participer à une réunion à partir du calendrier.