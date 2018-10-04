---
title: Déployer les équipes Microsoft Surface concentrateur
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 09/26/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Configurer les paramètres d’administration pour Microsoft Teams concentrateur de la surface d’exposition.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: aca03693a7abea6e26f175cc49f0142894749160
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372180"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Déployer les équipes Microsoft Surface concentrateur
======================================

Avant de déployer Microsoft Teams Microsoft Surface concentrateur, assurez-vous que le matériel, système d’exploitation et autres conditions sont réunies. Pour plus d’informations, consultez le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installer des équipes pour exposer Hub à partir du magasin de Microsoft 

Ces instructions sont pour l’installation des équipes concentrateur de Surface à partir de Microsoft Store. 
 
1. Démarrer la banque Microsoft :<br>
   a. Cliquez sur **Démarrer** > **toutes les applications** > **paramètres**.<br> b. Cliquez sur **compte de Surface Hub DISPOSITIF, la gestion**.<br>
   c. Sur la gauche, cliquez sur l’onglet **applications et fonctionnalités** .<br> d. Sur la droite, appuyez sur le bouton **Ouvrir un magasin** . 
2. Dans le Store Microsoft, recherchez les *Équipes Microsoft*. Les **Équipes Microsoft Surface concentrateur** s’affichera. Appuyez sur le bouton **obtenir l’application** à installer.  
3. Une fois l’installation terminée, redémarrez le Hub de la surface d’exposition. 

> [!NOTE]
> Ne cliquez pas sur la **barre de lancement** de la page de liste des magasins.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Rendre les équipes l’appel par défaut et l’application de réunions
 
Il existe deux options pour la configuration de la stratégie d’application appelant et réunions par défaut : 

- **Option 1**: configurer via une clé USB. 
- **Option 2**: configurer via Mobile Device Manager tels que Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Option 1 : Configurer via une clé USB 
 
Les packages se trouvent sur cette [page de téléchargement](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Choisissez celui qui convient pour le programme que vous prévoyez d’installer et de le copier sur une clé USB. Le fichier .ppkg correct à utiliser dépend de la stratégie d’application par défaut que voulez-vous appliquer comme suit : 

|Numéro  |Description  |
|---------|---------|
|0     | Application préférée Skype sur l’écran de démarrage, équipes de réunions disponibles        |
|1     | Application préférée équipes sur l’écran de démarrage, Skype réunions disponibles        |
|2     | Application exclusive équipes sur l’écran d’accueil (Skype app n’est pas disponible)        |
 
1. Attacher la clé USB à l’appareil Hub de la surface d’exposition. 
2. Ouvrez l’application de **paramètres** sur un appareil Hub de la surface d’exposition. 
3. Ouvrez **gestion de compte Hub Surface périphérique**.
4. Ouvrez **Gestion des périphériques**. 
5. Cliquez sur **Ajouter ou supprimer un package de mise en service**. 
6. Cliquez sur **Ajouter un Package**.
7. Sélectionnez l’option **Support amovible** dans le menu déroulant. 
8. Ajoutez le package <strong>TeamsRTMMode*.ppkg</strong> approprié qui a été précédemment copié à la clé USB. 
9. Redémarrez le dispositif Hub de la surface d’exposition. 
10. Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Option 2 : Configurer via Mobile Device Manager tels que Intune 

Utilisez ce qui suit pour configurer la stratégie par défaut les réunions et les appels d’application via Intune. Consultez également le blog, [déployer les équipes Microsoft pour Hub de la Surface d’application à l’aide de Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).

|Paramètre   |Valeur    |Description    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Type de données | nombre entier (0-2)   |0 - application préféré Skype sur l’écran de démarrage, équipes de réunions disponibles<br>1 - teams préféré application sur l’écran de démarrage, Skype réunions disponibles<br>2 - application exclusive d’équipes sur l’écran d’accueil (Skype app n’est pas disponible) |
|Opérations| Obtenir, définir        |

|Paramètre   |Valeur    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Type de données | chaîne - ensemble chaîne aux équipes des ID de package d’application en tant que **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe ! Les équipes** |
|Opérations| Obtenir, définir        |

Redémarrez le dispositif Hub de la surface d’exposition. Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier.

