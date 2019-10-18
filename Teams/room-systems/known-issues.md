---
title: Problèmes connus
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Cet article répertorie les problèmes connus concernant Microsoft Teams Rooms, par fonctionnalité spécifique.
ms.openlocfilehash: 79bebf69c0d4fc8dabff3e294166e7ab08b79166
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571388"
---
# <a name="known-issues"></a>Problèmes connus 
 
Cet article répertorie les problèmes connus concernant Microsoft Teams Rooms, par fonctionnalité spécifique.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Mettre à jour 

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            | --- |
|  Application obsolète         |    La console Microsoft Teams Rooms affiche une erreur « système config obsolète ».                |   [Utiliser l’outil de récupération de Microsoft Teams Rooms](recovery-tool.md)             |  Aucun |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface utilisateur 

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            | --- |
|Clavier virtuel manquant   | Le clavier virtuel n’apparaît pas lorsque vous devez entrer des informations dans Microsoft Teams Rooms. Ce problème se produit après l’installation de Windows 10 Creators Update (version 1703) soit sur le Surface Pro 4, sur lequel Microsoft Teams Rooms est en cours d’exécution. | Pour contourner ce problème, ouvrez manuellement le clavier virtuel. Pour cela, procédez comme suit :<br><br> **1.** fois et maintenez la touche de la barre des tâches, puis sur le bouton**Afficher le clavier tactile de diaporama**. Une icône clavier doit apparaître sur le côté droit de la barre des tâches. <br><br> **2.** Appuyez sur l’icône du clavier pour ouvrir le clavier virtuel. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Matériel

| Titre du problème |  Comportement\/Symptôme | Solution connue | Article Ko |
|  ---        |      ---             |   ---            |   --- |
| Moniteurs non détectés | Lorsque vous exécutez Microsoft Teams Rooms sur un appareil Surface Pro (modèle 2017), les moniteurs ne sont pas détectés. |  Maintenez le bouton marche du Surface Pro pendant 20 ou plusieurs secondes. Lorsque vous effectuez cette opération, l’appareil redémarre et efface le cache de graphiques. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitations et comportements prévus

***

Microsoft Teams Rooms ne prend pas en charge les entrées HDCP, qui entraînent visiblement des problèmes avec la fonctionnalité de réception HDMI (vidéo, audio). Assurez-vous que les options HDCP des commutateurs connectés à Microsoft Teams sont désactivées. 

***

Si vous souhaitez qu’un écran de façade de la salle bascule automatiquement vers une source vidéo active (par exemple, une console MTR) lorsque la source quitte le mode veille, certaines conditions doivent être remplies. Cette fonctionnalité n’est pas disponible, mais elle est prise en charge par le logiciel de salle Microsoft teams ; Une télévision grand public utilisée comme devant l’écran de la salle doit prendre en charge la fonctionnalité de contrôle Consumer Electronics (CEC) de l’interface HDMI.  En fonction du Dock ou de la console sélectionné (qui peut ne pas prendre en charge CEC, voir documentation du fabricant), un contrôleur d’espace de travail tel qu’un [EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad) peut être nécessaire pour activer le comportement souhaité. 

***

Utilisez toujours une connexion réseau 1 Gbit/s câblée pour vous assurer que vous disposez de la bande passante nécessaire. 

***

Si votre périphérique Microsoft teams se bloque en toute sécurité, vous ne pourrez pas vous authentifier auprès de l’appareil et ouvrir les paramètres. Par exemple, si vous supprimez les salles de Microsoft teams du domaine après qu’il est joint au domaine, l’approbation est perdue. La solution consiste à se connecter avec le compte d’administrateur local. 
***
La version 64 bits de l’édition anniversaire de Windows 10 Entreprise (en anglais, version 1607) est n’est plus prise en charge depuis la publication Microsoft Teams Rooms 3.0.12.0. 
***
Les salles de Microsoft teams sont une application multifenêtre et nécessitent l’affichage d’une salle avant pour être connectés au port HDMI de l’appareil, afin que l’application fonctionne correctement. Vérifiez que vous disposez d’un écran HDMI branché ou que vous utilisez un câble HDMI si vous effectuez des tests et que vous n’avez pas encore d’affichage acheté.
***
Windows 10 1903 n’est pas encore disponible sur les appareils Microsoft teams en Crestron en raison de problèmes liés à un pilote graphique.

***
<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi

[Aide Microsoft Teams Rooms](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)
