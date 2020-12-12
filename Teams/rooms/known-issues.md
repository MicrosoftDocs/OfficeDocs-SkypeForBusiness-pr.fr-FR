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
description: L’administrateur peut en savoir plus sur une liste des problèmes connus de Microsoft Teams, notamment les mises à jour, l’interface utilisateur, le matériel et les comportements attendus.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6c32e35f0ea95d81fcb597c18a12a8f48fe4c7b2
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662629"
---
# <a name="known-issues"></a>Problèmes connus 
 
Cet article répertorie les problèmes connus concernant Microsoft Teams Rooms, par fonctionnalité spécifique.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Mettre à jour 

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            | --- |
| Application indémarrable |  Après avoir effectué la mise à jour vers la version de l’application 4.4.41.0, le système démarre sur l’écran noir ou accède à l’écran de connexion après quelques minutes. | Pour résoudre ce problème, suivez les étapes décrites dans l' [application salles de Microsoft Teams ne démarre pas après la mise à jour vers la version 4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) .  | Aucun |
|  Marketing le partage de contenu des réunions n’apparaît pas en mode plein écran         |    Dans les réunions Skype entreprise, des salles avec des paramètres ppp élevés risquent de ne pas s’afficher dans la mesure où le contenu partagé dans une réunion n’affiche pas la totalité de l’écran au premier plan de la salle. Ce problème provient d’un problème sous-jacent de l’API de protocole RDP (Remote Desktop Protocol) Windows 10. | `<WinRTRdpEnabled>`Pour résoudre ce problème, utilisez le paramètre XML pour désactiver l’API RDP Windows 10. Pour le désactiver, vous devez spécifier la valeur `false` . Pour plus d’informations, consultez [gestion des paramètres de la console à l’aide d’un fichier de configuration XML](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file). | Aucun |
|  Application obsolète         |    La console Microsoft Teams Rooms affiche une erreur « système config obsolète ».                |   [Utiliser l’outil de récupération de Microsoft Teams Rooms](recovery-tool.md)             |  Aucun |
|  Appareil mis à jour vers une version non prise en charge de Windows 10   |    Appareil Windows 10 mis à jour à partir de la version 1803 vers la version 1809, qui n’est pas prise en charge. La version prise en charge est 1903. |   Cela peut se produire si le paramètre [stratégie de groupe ou GPM pour](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) le paramètre DeferFeatureUpdatesPeriodinDays, qui vous permet de différer les mises à jour de fonctionnalités d’un nombre de jours spécifié, est défini sur le maximum de 365 jours. <br><br> La version 1809 de Windows 10 n’est pas prise en charge dans Microsoft Teams, mais la version 1903 est prise en charge. Toutefois, à compter du 27 mars 2020, la version 1809 sera de plus de 365 jours. Si ce paramètre n’est pas modifié, Windows essaie d’installer la version 1809, ce qui risque de provoquer des problèmes avec les salles de Microsoft Teams.<br><br>Pour éviter ce problème, **supprimez** un paramètre de stratégie de groupe ou d’affichage GPM pour différer les mises à jour. Cela permet à Windows de procéder à la mise à jour vers la dernière version du système d’exploitation pris en charge. <br><br>**Important** Le paramètre de stratégie de groupe ou de gestion des périphériques mobiles doit être **supprimé** (à gauche, non configuré) et **ne pas être défini sur 0**. Si la stratégie est définie sur 0, Windows utilise la version la plus récente qui n’est peut-être pas prise en charge. |  Aucun |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface utilisateur 

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            | --- |
|Clavier virtuel manquant   | Le clavier virtuel n’apparaît pas lorsque vous devez entrer des informations dans Microsoft Teams Rooms. Ce problème survient dans Windows 10, version 1903. | Installez la mise à jour cumulative 2020-04 pour Windows 10, version 1903 pour les systèmes x64 par le biais des mises à jour Windows.  | Aucun | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Matériel

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            |   --- |
| Moniteurs non détectés | Lorsque vous exécutez Microsoft Teams Rooms sur un appareil Surface Pro (modèle 2017), les moniteurs ne sont pas détectés. |  Maintenez le bouton marche du Surface Pro pendant 20 ou plusieurs secondes. Lorsque vous effectuez cette opération, l’appareil redémarre et efface le cache de graphiques. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitations et comportements prévus

**_

Microsoft Teams Rooms ne prend pas en charge les entrées HDCP, qui entraînent visiblement des problèmes avec la fonctionnalité de réception HDMI (vidéo, audio). Assurez-vous que les options HDCP des commutateurs connectés à Microsoft Teams sont désactivées. 

_*_

Si vous souhaitez qu’un écran de façade de la salle bascule automatiquement vers une source vidéo active (par exemple, une console MTR) lorsque la source quitte le mode veille, certaines conditions doivent être remplies. Cette fonctionnalité n’est pas disponible, mais elle est prise en charge par le logiciel de salle Microsoft teams ; Une télévision grand public utilisée comme devant l’écran de la salle doit prendre en charge la fonctionnalité de contrôle Consumer Electronics (CEC) de l’interface HDMI.  Selon le Dock ou la console sélectionné (qui n’est pas pris en charge par le CEC, voir documentation du fabricant), un contrôleur tel qu’une connexion [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron peut être nécessaire pour activer le comportement souhaité. 

_*_

Utilisez toujours une connexion réseau 1 Gbit/s câblée pour vous assurer que vous disposez de la bande passante nécessaire. 

_*_

Si votre périphérique Microsoft teams se bloque en toute sécurité, vous ne pourrez pas vous authentifier auprès de l’appareil et ouvrir les paramètres. Par exemple, si vous supprimez les salles de Microsoft teams du domaine après qu’il est joint au domaine, l’approbation est perdue. La solution consiste à se connecter avec le compte d’administrateur local. 
_*_ Les salles de Microsoft teams sont une application multifenêtre et nécessitent l’affichage d’une salle avant pour être connectés au port HDMI de l’appareil, afin que l’application fonctionne correctement. Vérifiez que vous disposez d’un écran HDMI branché ou que vous utilisez un câble HDMI si vous effectuez des tests et que vous n’avez pas encore d’affichage acheté.
_** <a name="See"> </a>  
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](rooms-manage.md)
