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
description: Découvrez comment installer et configurer l’application teams surface Hub de sorte que teams soit l’application par défaut pour les appels et les réunions.
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

Avant d’installer teams pour surface Hub, veillez à effectuer les opérations suivantes :

 □ Vérifiez que le matériel, le système d’exploitation et les autres exigences sont satisfaits. Pour plus d’informations, consultez le [Guide d’administration Microsoft surface Hub](https://docs.microsoft.com/surface-hub/).<br>
 □ Vérifiez que la mise à jour du système d’exploitation minimum nécessaire pour teams est installée- [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ Affecter une licence d’équipes au compte de l’appareil concentrateur.<br>
 □ Si vous passez de Skype entreprise Online, vérifiez qu’une licence teams est affectée à l’utilisateur.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installer teams pour surface Hub à partir de la boutique Microsoft 

Les instructions suivantes s’appliquent à l’installation d’teams surface Hub à partir du Microsoft Store. 
 
1. Démarrez Microsoft Store :<br>
   a. Appuyez sur **Démarrer** > **tous les** > **paramètres**d’application.<br> b. Appuyez sur **compte surface Hub, gestion**.<br>
   c. Sur la gauche, appuyez sur l’onglet **applications & fonctionnalités** .<br> d. À droite, appuyez sur le bouton **ouvrir la boutique** . 
2. Dans la boutique Microsoft, recherchez *Microsoft teams*. **Microsoft teams surface Hub** est affiché. Appuyez sur le bouton **obtenir l’application** pour procéder à l’installation.  
3. Lorsque l’installation est terminée, redémarrez surface Hub. 

> [!NOTE]
> N’appuyez pas sur **lancer** à partir de la page Description dans le Windows Store.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Définir teams comme application par défaut pour les appels et les réunions
 
Deux options s’offrent à vous pour configurer la stratégie d’appel et de réunion par défaut : 

- **Option 1**: configuration via la clé USB. 
- **Option 2**: configurer via le GPM (par exemple, Intune).
 
### <a name="option-1-configure-via-usb-key"></a>Option 1 : configurer via une clé USB 
 
Les packages sont disponibles sur cette [page de téléchargement](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Sélectionnez l’application appropriée pour le package que vous envisagez d’installer et copiez-la sur une clé USB. Le fichier. ppkg approprié à utiliser dépend de la stratégie d’application par défaut que vous souhaitez appliquer en procédant comme suit : 

|Numéro  |Description  |
|---------|---------|
|0,4     | Application préférée Skype sur l’écran d’accueil, réunions teams disponibles        |
|1     | Application par défaut teams dans l’écran d’accueil, réunions Skype disponibles        |
|2     | Application Skype pour les équipes sur l’écran d’accueil (l’application Skype n’est pas disponible)        |
 
1. Associez la clé USB à l’appareil surface Hub. 
2. Ouvrez l’application **paramètres** sur un appareil surface Hub. 
3. Ouvrez **gestion de compte de l’appareil surface Hub**.
4. Ouvrez la **gestion des appareils**. 
5. Cliquez sur **Ajouter ou supprimer un package de mise à service**. 
6. Cliquez sur **Ajouter un package**.
7. Sélectionnez l’option **média amovible** dans le menu déroulant. 
8. Ajoutez le package <strong>TeamsRTMMode *. ppkg</strong> approprié précédemment copié sur la clé USB. 
9. Redémarrez l’appareil surface Hub. 
10. Après le redémarrage de l’appareil, vous devriez être en mesure de démarrer l’application teams à partir de l’écran d’accueil et de participer à une réunion à partir du calendrier. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Option 2 : configurer via le GPM (par exemple, Intune) 

Procédez comme suit pour configurer la stratégie d’application pour les appels et les réunions par défaut via Intune. Consultez également le blog, [déploiement de l’application Microsoft teams pour surface Hub à l’aide de Intune](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/).

|Paramètres   |Valeur    |Description    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Type de données | entier (0-2)   |0-application préférée de Skype sur l’écran d’accueil, réunions teams disponibles<br>1-l’application préférée d’équipes sur l’écran d’accueil, réunions Skype disponibles<br>2-application exclusive pour les équipes sur l’écran d’accueil (l’application Skype n’est pas disponible) |
|Opérations| Obtenir, définir        |

|Paramètres   |Valeur    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Type de données | Définissez chaîne-donnez une chaîne à l’ID de package d’application teams en tant que **Microsoft. MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe. Teams** |
|Opérations| Obtenir, définir        |

Redémarrez l’appareil surface Hub. Après le redémarrage de l’appareil, vous devriez être en mesure de démarrer l’application teams à partir de l’écran d’accueil et de participer à une réunion à partir du calendrier.

