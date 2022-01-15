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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Les administrateurs peuvent obtenir une liste des problèmes connus pour Salles Microsoft Teams, notamment les mises à jour, l’interface utilisateur, le matériel et les limitations, ainsi que les comportements attendus.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2476753f5945217157336a814c8d498242c0eef1
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055104"
---
# <a name="known-issues"></a>Problèmes connus 
 
Cet article répertorie les problèmes connus concernant Microsoft Teams Rooms, par fonctionnalité spécifique.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Mettre à jour 

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            | --- |
| Lancement automatique du navigateur Edge | Le navigateur Edge antérieur à la build 97.0.1072.62 est lancé automatiquement en même temps que l’application Microsoft Teams Room au démarrage de l’appareil. | Ce problème doit se résoudre automatiquement, sans interaction de l’utilisateur nécessaire, le lundi 17 janvier 2022 ou avant. Si une résolution plus rapide est requise : lorsque Edge est lancé en même temps que la salle Microsoft Teams, consultez la edge://settings/help d’URL. Une mise à jour devrait démarrer automatiquement le téléchargement et l’application. Sélectionnez le bouton « redémarrer » du navigateur une fois l’application de la mise à jour terminée. Fermez Edge, redémarrez le système. Le problème devrait être résolu. | Aucun |
| Vidéo sur les participants à la galerie fractionnement   | En mode d’affichage à deux facex, lorsqu’il n’y a pas de contenu partagé dans une réunion qui compte plus de 9 participants vidéo distants, 1 vidéo au premier plan avec l’aperçu automatique peut apparaître en tant qu’audio en raison d’un problème connu. Par ailleurs, le nombre de participants audio est inférieur au nombre réel de participants audio affichés sur deux fronts de salle. | Le problème sera résolu dans la prochaine mise à jour. | Aucun |
| L’application ne se lance pas |  Après la mise à jour vers la version 4.4.41.0 de l’application, le système démarre sur un écran noir ou passe à l’écran de inscription après quelques minutes. | Suivez les étapes de Salles Microsoft Teams application ne démarre pas après la mise à jour vers la [version 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) pour résoudre ce problème.  | Aucun |
|  Faible volume de réunion après le partage de contenu         |   Salles Microsoft Teams les appareils sur Windows 10 20H2 baissent le volume des médias et des réunions après le partage de contenu via HDMI en salle. Ce problème est dû à un problème audio dans Windows 10 20H2. | Le correctif pour résoudre ce problème est disponible dans l’application version [4.9.12.0.](/microsoftteams/rooms/rooms-release-note#49120-7282021) | Aucun |
|  Application obsolète         |    La console Microsoft Teams Rooms affiche une erreur « système config obsolète ».                |   [Utiliser l’outil de récupération de Microsoft Teams Rooms](recovery-tool.md)             |  Aucun |
|  Appareil mis à jour vers une version d’Windows 10   |    Windows 10 appareil mis à jour de la version 1803 à la version 1809, laquelle n’est pas prise en charge. La version prise en charge est 1903. |   Cela peut se produire si le paramètre [DeferFeatureUpdatesPeriodinDays,](/windows/deployment/update/waas-configure-wufb) qui vous permet de différer les mises à jour des fonctionnalités pour un nombre de jours spécifié, est réglé sur un nombre maximal de 365 jours. <br><br> Windows 10 version 1809 n’est pas prise en charge avec Salles Microsoft Teams, tandis que la version 1903 est prise en charge. Toutefois, depuis le 27 mars 2020, la version 1809 a plus de 365 jours. Si ce paramètre n’est pas modifié, vous Windows installer la version 1809, ce qui peut entraîner des problèmes de Salles Microsoft Teams.<br><br>Pour éviter cette situation, **supprimez tout** paramètre de stratégie de groupe ou de gestion des paramètres de gestion des derniers paramètres pour différer les mises à jour. Cela permet aux utilisateurs Windows mise à jour vers la dernière version du système d’exploitation prise en charge. <br><br>**IMPORTANT :** Le paramètre De stratégie de groupe ou MDM doit **être** supprimé (non configuré) et non définir **sur 0.** Si la stratégie est définie sur 0, Windows la dernière version disponible qui n’est peut-être pas prise en charge. |  Aucun |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface utilisateur 

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            | --- |
|Clavier virtuel manquant   | Le clavier virtuel n’apparaît pas lorsque vous devez entrer des informations dans Microsoft Teams Rooms. Ce problème se produit dans Windows 10, version 1903. | Installer la mise à jour cumulative 2020-04 Windows 10, version 1903 pour les systèmes x64 par le biais Windows mises à jour.  | Aucun | 

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

Si vous souhaitez qu’un écran avant de la salle bascule automatiquement vers une source vidéo active (par exemple, une console MTR) lorsque la source extraite du mode veille, certaines conditions doivent être remplies. Cette fonctionnalité est facultative mais prise en charge Salles Microsoft Teams logiciel, à condition que le matériel sous-jacent la prend en charge. Un téléviseur grand public utilisé comme avant d’affichage doit prendre en charge la fonctionnalité CEC (Consumer Electronics Control) de HDMI.  En fonction de la station d’accueil ou de la console sélectionnée (qui ne peut pas prendre en charge la cec, consultez la documentation du support technique du fabricant), un contrôleur tel qu’un [contrôleur HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) d’Extron peut être nécessaire pour activer le comportement souhaité.

Par ailleurs, un téléviseur grand public utilisé comme devant l’affichage de la salle peut entraîner des problèmes de stabilité avec Salles Microsoft Teams logiciels. Cela est dû à une implémentation incohérente des modes de veille, à la sélection active de la source vidéo et à la communication d’informations d’EDID défaillante sur l Salles Microsoft Teams appareil. Les symptômes connus sont un écran noir/gris au premier plan de l’affichage de la salle ou la console Salles Microsoft Teams qui ne répond plus après la veille.  Si vous rencontrez des problèmes lors de l’utilisation de téléviseurs grand public, nous vous recommandons d’installer un contrôleur EDID configurable ou un émulateur EDID, tel que [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [DR-EDID Emulator](https://fsrinc.com/fsr-products/product/dr-edid-manager-learner/category_pathway-143) à partir du groupe de produits vidéo FSR.

***

Utilisez toujours une connexion réseau câblé 1-Gbps pour vous assurer de avoir la bande passante nécessaire. 

***

Si votre Salles Microsoft Teams perd la confiance avec le domaine, vous ne pourrez pas vous authentifier sur l’appareil et ouvrir les Paramètres. Par exemple, si vous supprimez l’Salles Microsoft Teams du domaine une fois qu’il a été joint au domaine, l’confiance est perdue. La solution consiste à se connecter avec le compte d’administrateur local. 
***
Salles Microsoft Teams est une application à plusieurs fenêtres et nécessite un affichage avant de salle pour être connecté au port HDMI de l’appareil, pour que l’application fonctionne correctement. Assurez-vous que vous avez un écran HDMI connecté ou utilisez une prise HDMI factice si vous testez et que vous n’avez pas encore acheté d’écran.
***
<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](rooms-manage.md)
