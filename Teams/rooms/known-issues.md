---
title: Problèmes connus
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Les administrateurs peuvent obtenir une liste des problèmes connus pour les salles Microsoft Teams, notamment les mises à jour, l’interface utilisateur, le matériel et les limitations, ainsi que les comportements attendus.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02e7d2411fa1d8a86fe20dcab3013be758f22a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117532"
---
# <a name="known-issues"></a>Problèmes connus 
 
Cet article répertorie les problèmes connus concernant Microsoft Teams Rooms, par fonctionnalité spécifique.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Mettre à jour 

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            | --- |
| L’application ne se lance pas |  Après la mise à jour vers la version 4.4.41.0 de l’application, le système démarre sur un écran noir ou passe à l’écran de logo après quelques minutes. | Pour résoudre ce problème, suivez les étapes de l’application Salles Microsoft Teams ne démarre pas après la mise à jour vers la [version 4.4.41.0.](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update)  | Aucun |
|  Le partage de contenu de réunions SfB ne s’affiche pas en plein écran         |    Dans les réunions Skype Entreprise, les salles avec affichage en avant-plan à l’aide de paramètres d’ID élevé peuvent rencontrer des problèmes où le contenu partagé dans une réunion n’affiche pas l’intégralité de l’écran à l’avant de l’affichage de la salle. Ce problème est dû à un problème sous-jacent dans l’API Windows 10 Remote Desktop Protocol (RDP). | Utilisez le `<WinRTRdpEnabled>` paramètre XML pour désactiver l’API RDP Windows 10 afin de résoudre ce problème. Pour la désactiver, vous devez spécifier la valeur en tant que `false` . Pour plus d’informations, [voir Gérer les paramètres de la console avec un fichier de configuration XML.](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) | Aucun |
|  Application obsolète         |    La console Microsoft Teams Rooms affiche une erreur « système config obsolète ».                |   [Utiliser l’outil de récupération de Microsoft Teams Rooms](recovery-tool.md)             |  Aucun |
|  Appareil mis à jour vers une version de Windows 10 non pris en place   |    Appareil Windows 10 mis à jour de la version 1803 à la version 1809 (non prise en charge). La version prise en charge est 1903. |   Cela peut se produire si le paramètre [DeferFeatureUpdatesPeriodinDays,](/windows/deployment/update/waas-configure-wufb) qui vous permet de différer les mises à jour des fonctionnalités pour un nombre de jours spécifié, est réglé sur un nombre maximal de 365 jours. <br><br> Windows 10 version 1809 n’est pas pris en charge avec Salles Microsoft Teams, tandis que la version 1903 est prise en charge. Toutefois, depuis le 27 mars 2020, la version 1809 a plus de 365 jours. Si ce paramètre n’est pas modifié, Windows tente d’installer la version 1809, ce qui peut entraîner des problèmes avec les salles Microsoft Teams.<br><br>Pour éviter cette situation, **supprimez tout** paramètre de stratégie de groupe ou de gestion des paramètres de gestion des biens et des stratégies de groupe pour différer les mises à jour. Cela permet à Windows de mettre à jour vers la dernière version du système d’exploitation prise en charge. <br><br>**IMPORTANT** Le paramètre de stratégie de groupe ou de gestion des jamais-êtres **doit** être supprimé (non configuré) et non définir **sur 0.** Si la stratégie est définie sur 0, Windows prend la dernière version disponible qui n’est peut-être pas prise en charge. |  Aucun |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface utilisateur 

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            | --- |
|Clavier virtuel manquant   | Le clavier virtuel n’apparaît pas lorsque vous devez entrer des informations dans Microsoft Teams Rooms. Ce problème se produit dans Windows 10, version 1903. | Installer la mise à jour cumulative 2020-04 pour Windows 10, version 1903 pour les systèmes x64 par le biais de Windows Update.  | Aucun | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Matériel

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            |   --- |
| Moniteurs non détectés | Lorsque vous exécutez Microsoft Teams Rooms sur un appareil Surface Pro (modèle 2017), les moniteurs ne sont pas détectés. |  Maintenez le bouton marche du Surface Pro pendant 20 ou plusieurs secondes. Lorsque vous effectuez cette opération, l’appareil redémarre et efface le cache de graphiques. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitations et comportements prévus

***

Microsoft Teams Rooms ne prend pas en charge les entrées HDCP, qui entraînent visiblement des problèmes avec la fonctionnalité de réception HDMI (vidéo, audio). Assurez-vous que les options HDCP des commutateurs connectés à Microsoft Teams sont désactivées. 

***

Si vous souhaitez qu’un écran avant de la salle bascule automatiquement vers une source vidéo active (par exemple, une console MTR) lorsque la source extraite du mode veille, certaines conditions doivent être remplies. Cette fonctionnalité est facultative mais prise en charge par le logiciel Salles Microsoft Teams, à condition que le matériel sous-jacent la prend en charge. Un téléviseur grand public utilisé comme avant d’affichage de salle doit prendre en charge la fonctionnalité CEC (Consumer Electronics Control) de HDMI.  En fonction de la station d’accueil ou de la console sélectionnée (qui ne peut pas prendre en charge la cec, consultez la documentation du support technique du fabricant), un contrôleur tel qu’un [contrôleur HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) d’Extron peut être nécessaire pour activer le comportement souhaité. 

***

Utilisez toujours une connexion réseau câblé 1-Gbps pour vous assurer de avoir la bande passante nécessaire. 

***

Si votre appareil Salles Microsoft Teams perd la confiance avec le domaine, vous ne pourrez pas vous authentifier sur l’appareil et ouvrir les Paramètres. Par exemple, si vous supprimez les salles Microsoft Teams du domaine une fois qu’il a été joint au domaine, l’confiance est perdue. La solution consiste à se connecter avec le compte d’administrateur local. 
***
Salles Microsoft Teams est une application à plusieurs fenêtres et nécessite un affichage avant de salle pour être connecté au port HDMI de l’appareil, pour que l’application fonctionne correctement. Assurez-vous que vous avez un écran HDMI connecté ou utilisez une prise HDMI factice si vous testez et que vous n’avez pas encore acheté d’écran.
***
<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](rooms-manage.md)