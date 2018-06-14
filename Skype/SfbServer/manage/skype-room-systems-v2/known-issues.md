---
title: Problèmes connus
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cet article traite des problèmes connus pour v2 Skype salle systèmes, par fonctionnalité.
ms.openlocfilehash: 2fde12d616260963dc342df2d9cef94acf616756
ms.sourcegitcommit: dc7a7da270121c3702f38614158c9067ad38f12a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2018
ms.locfileid: "19881541"
---
# <a name="known-issues"></a>Problèmes connus 
 
Cet article répertorie les problèmes connus pour v2 Skype salle systèmes, par fonctionnalité.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Mise à jour 

| Titre du problème |  Comportement \/ symptôme | Solution de contournement | Base de connaissances |
|  ---        |      ---             |   ---            | --- |
|  Application obsolète         |    La console de v2 Skype salle systèmes affiche une erreur « configuration de système obsolète ».                |   [Utiliser l’outil de récupération de systèmes de salle Skype v2](recovery-tool.md)             |  Aucun |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interface utilisateur 

| Titre du problème |  Comportement \/ symptôme | Solution de contournement | Base de connaissances |
|  ---        |      ---             |   ---            | --- |
|Clavier virtuel manquant   | Le clavier virtuel n’apparaît pas lorsque vous devez entrer des informations dans les systèmes de salle Skype v2. Ce problème se produit après que la mise à jour créateurs Windows 10 (version 1703) est installé sur le 4 Surface Pro sur lequel Skype salle systèmes v2 est en cours d’exécution. | Pour contourner ce problème, ouvrez manuellement le clavier virtuel. Pour ce faire, procédez comme suit :<br><br> Appuyez sur **1.** et maintenez la barre des tâches, puis appuyez sur le bouton **Afficher tactile clavier** . Une icône de clavier doit apparaître sur le côté droit de la barre des tâches. <br><br> **2.** cliquez sur l’icône de clavier pour ouvrir le clavier virtuel. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>Configuration matérielle

| Titre du problème |  Comportement \/ symptôme | Solution de contournement | Base de connaissances |
|  ---        |      ---             |   ---            |   --- |
| Moniteurs non détectés | Lorsque vous exécutez des systèmes de salle Skype v2 sur un appareil Surface Pro (modèle 2017), les moniteurs ne sont pas détectées. |  Maintenez le bouton d’alimentation Surface Pro au moins 20 secondes. Lorsque vous effectuez cette opération, l’appareil redémarre et efface le cache de graphiques. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Comportements attendus et limitations
***
Systèmes de salle Skype v2 ne prend pas en charge entrée HDCP, qui a été observée pour provoquer des problèmes avec HDMI acquisition des fonctionnalités (vidéo, audio). Veiller à ce que les commutateurs connectés à des systèmes de salle Skype v2 ont options HDCP désactivées. 
***
Télévision utilisée comme un plan de salle d’affichage pour la prise en charge/activer la fonctionnalité de contrôle de Electronics consommateur (CCE) de HDMI afin qu’il peut basculer automatiquement à une source vidéo active du mode veille. Cette fonctionnalité n’est pas pris en charge sur tous les TV. 
***
Toujours utiliser une connexion de réseau 1 Gbit/s câblée afin de garantir que la bande passante requise avoir. 
***
Si votre appareil v2 de systèmes de salle Skype perd approbation avec le domaine (par exemple, si vous supprimez le v2 Skype salle systèmes du domaine une fois qu’il est joint au domaine), vous ne pourrez pas s’authentifier sur le périphérique et ouvrir des paramètres. La méthode de contournement consiste à vous connecter avec le compte d’administrateur local. 
***
La version 64 bits de l’édition entreprise anniversaire de mariage 10 Windows (en anglais, version 1607) n’est plus pris en charge à partir de systèmes de salle Skype v2 version 3.0.12.0. 
***

<a name="See"> </a>  
## <a name="see-also"></a>Voir aussi

[Systèmes de salle Skype version 2](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gérer les salles Skype systèmes v2](skype-room-systems-v2.md)