---
title: Créer un partage de fichiers dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Résumé : Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype pour Business Server. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a84e37c3d069c3f51570b600d5ec4804d2a5ee3c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967113"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Créer un partage de fichiers dans Skype pour Business Server
 
**Résumé :** Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype pour Business Server. Téléchargez une version d’évaluation gratuite de Skype pour Business Server depuis le centre d’évaluation Microsoft à :[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype pour Business Server requiert un partage de fichiers afin que tous les ordinateurs de la topologie peuvent échanger des fichiers. Création d’un partage de fichiers est l’étape 2 de 8 dans le processus d’installation pour Skype pour Business Server. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5 comme indiqué sur le diagramme. Pour plus d’informations sur le partage de fichiers la planification, consultez [exigences pour Skype pour Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Schéma de vue d’ensemble](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Créer un partage de fichiers basique

Cette section vous indique comment créer un partage de fichiers Serveur Windows basique. Un partage de fichiers Windows Server base est pris en charge avec Skype pour Business Server. Toutefois, il ne fournit pas explicitement une haute disponibilité. Pour un environnement à haute disponibilité, un partage de fichiers Système de fichiers distribué DFS est recommandé. Pour plus d’informations sur un partage de fichiers haute disponibilité et de DFS, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 a effectué un bond de géant en offrant des solutions de partage de fichiers de type SAN (Storage Area Network) à l’aide de la plateforme Windows Server. Comparée à un dispositif SAN traditionnel, une solution de stockage Windows Server 2012 R2 permet de diviser les coûts par deux sans réelles incidences sur les performances. Pour plus d’informations sur les options de partage de fichiers dans Windows Server 2012 R2, voir le livre blanc [Stockage de Windows Server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Regardez la vidéo des étapes pour **créer un partage de fichiers** :
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Créer un partage de fichiers basique

1. Connectez-vous à l’ordinateur qui hébergera le partage de fichiers.
    
2. Cliquez avec le bouton droit sur le dossier que vous souhaitez partager, puis sélectionnez **Propriétés**.
    
3. Sélectionnez l’onglet **Partage**, puis cliquez sur **Partage avancé**.
    
4. Cliquez sur **Partager ce dossier**.
    
5. Cliquez sur **Autorisations**.
    
6. Ajoutez le groupe **Administrateurs** local sur le serveur qui héberge le partage de fichiers, accordez les droits d’**Autorisation : Contrôle intégral, Changement et Lecture**, puis cliquez sur **OK**.
    
7. Cliquez de nouveau sur **OK** et notez le chemin d’accès réseau.
    
8. Cliquez sur **Terminé** pour fermer l’Assistant.
    
     ![Partage d’onglets pour partager des dossiers.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

