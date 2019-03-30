---
title: Problèmes connus
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: Cet article traite des problèmes connus pour les salles d’équipes Microsoft, par fonctionnalité.
ms.openlocfilehash: d71b209784f4737ac4433e2eececb1f9ada3ebc8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013086"
---
# <a name="known-issues"></a>Problèmes connus 
 
Cet article répertorie les problèmes connus pour les salles d’équipes Microsoft, par fonctionnalité.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>mettre à jour 

| Intitulé du problème |  Comportement \/ symptôme | Solution | Base de connaissances |
|  ---        |      ---             |   ---            | --- |
|  Application obsolète         |    La console Microsoft équipes salles affiche une erreur « configuration de système obsolète ».                |   [Utiliser l’outil de récupération Microsoft équipes salles](recovery-tool.md)             |  Aucun |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface utilisateur 

| Intitulé du problème |  Comportement \/ symptôme | Solution | Base de connaissances |
|  ---        |      ---             |   ---            | --- |
|Clavier virtuel manquant   | Le clavier virtuel n’apparaît pas lorsque vous avez besoin d’entrer des informations dans les salles d’équipes Microsoft. Ce problème se produit après que la mise à jour créateurs Windows 10 (version 1703) est installé sur le 4 Surface Pro sur lequel est exécuté Microsoft équipes salles. | Pour contourner ce problème, ouvrez manuellement le clavier virtuel. Pour ce faire, procédez comme suit :<br><br> Appuyez sur **1.** et maintenez la barre des tâches, puis appuyez sur le bouton **Afficher tactile clavier** . Une icône de clavier doit apparaître sur le côté droit de la barre des tâches. <br><br> **2.** cliquez sur l’icône de clavier pour ouvrir le clavier virtuel. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>Configuration matérielle

| Intitulé du problème |  Comportement \/ symptôme | Solution | Base de connaissances |
|  ---        |      ---             |   ---            |   --- |
| Moniteurs non détectés | Lorsque vous exécutez Microsoft équipes salles sur un appareil Surface Pro (modèle 2017), les moniteurs ne sont pas détectées. |  Maintenez le bouton d’alimentation Surface Pro au moins 20 secondes. Lorsque vous effectuez cette opération, l’appareil redémarre et efface le cache de graphiques. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Comportements attendus et limitations
***
Salles d’équipes Microsoft ne gère pas les entrées d’HDCP qui a été observée provoquer problèmes avec HDMI acquisition des fonctionnalités (vidéo, audio). Veiller à ce que commutateurs connectés aux salles d’équipes Microsoft ont options HDCP désactivées. 
***
Un téléviseur utilisé comme écran à l’avant de la salle doit prendre en charge/permettre la fonctionnalité CEC (Consumer Electronics Control ) HDMI afin de pouvoir basculer automatiquement sur une source vidéo active depuis le mode veille. Cette fonctionnalité n’est pas prise en charge sur tous les téléviseurs. 
***
Toujours utiliser une connexion de réseau 1 Gbit/s câblée afin de garantir que la bande passante requise avoir. 
***
Si votre appareil Microsoft équipes salles perd approbation avec le domaine (par exemple, si vous supprimez les salles d’équipes Microsoft du domaine une fois qu’il est joint au domaine), vous ne pourrez pas s’authentifier sur le périphérique et ouvrir des paramètres. La méthode de contournement consiste à vous connecter avec le compte d’administrateur local. 
***
La version 64 bits de Windows 10 entreprise anniversaire edition (en anglais, version 1607) n’est plus pris en charge à compter de salles d’équipes Microsoft version 3.0.12.0. 
***

<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi

[Aide Microsoft équipes salles](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer les équipes Microsoft salles](skype-room-systems-v2.md)