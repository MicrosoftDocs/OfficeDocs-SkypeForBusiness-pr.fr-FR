---
title: Créer un partage de fichiers dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Résumé : Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft à l’adresse suivante :.'
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028295"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Créer un partage de fichiers dans Skype entreprise Server
 
**Résumé :** Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype entreprise Server. Téléchargez une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft à l’adresse suivante :.
  
Skype entreprise Server nécessite un partage de fichiers pour que les ordinateurs de la topologie puissent échanger des fichiers. La création d’un partage de fichiers est l’étape 2 sur 8 du processus d’installation de Skype entreprise Server. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez effectuer les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5 comme indiqué dans le diagramme. Pour plus d’informations sur la planification du partage de fichiers, voir [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagramme de vue d’ensemble](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Créer un partage de fichiers de base

Cette section vous guide tout au long de la création d’un partage de fichiers Windows Server de base. Un partage de fichiers Windows Server de base est pris en charge avec Skype entreprise Server. Toutefois, il ne fournit pas de manière explicite la haute disponibilité. Pour un environnement à haute disponibilité, un partage de fichiers DFS (Distributed File System) est recommandé. Pour plus d’informations sur un partage de fichiers haute disponibilité et DFS, reportez-vous à la rubrique [plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 a fait des bonds importants en fournissant des solutions de partage de fichiers de type SAN (Storage Area Network) à l’aide de la plateforme Windows Server. Par rapport à un appareil SAN traditionnel, une solution de stockage Windows Server 2012 R2 peut réduire les coûts en deux, avec un impact minime sur les performances. Pour plus d’informations sur les options de partage de fichiers dans Windows Server 2012 R2, reportez-vous au livre blanc téléchargeable [Windows server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Regardez les étapes vidéo pour **créer un partage de fichiers**:
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Créer un partage de fichiers de base

1. Ouvrez une session sur l’ordinateur qui hébergera le partage de fichiers.
    
2. Cliquez avec le bouton droit sur le dossier que vous prévoyez de partager, puis sélectionnez **Propriétés**.
    
3. Sélectionnez l’onglet **partage** , puis cliquez sur **partage avancé**.
    
4. Cliquez sur **partager ce dossier**.
    
5. Cliquez sur **Autorisations**.
    
6. Ajoutez le groupe **administrateurs** local du serveur qui héberge le partage de fichiers, octroyez les droits de **contrôle total, de modification et de lecture** , puis cliquez sur **OK**.
    
7. Cliquez de nouveau sur **OK** et prenez note du chemin d’accès réseau.
    
8. Cliquez sur **Terminer** pour fermer l’Assistant.
    
     ![Onglet partage pour le partage d’un dossier.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Si le magasin de fichiers est hébergé sur un partage DFS, l’avertissement suivant s’affiche :

AVERTISSEMENT : impossible d’accéder aux autorisations de partage\\<domain>\<pour « partager> ».

>Cela est attendu si vous n’êtes pas administrateur sur le serveur de fichiers ou s’il s’agit d’un partage de système de fichiers DFS (Distributed File System). Si les autorisations de partage ont déjà été configurées, cet avertissement peut être ignoré. S’il s’agit d’un nouveau partage, reportez-vous à la documentation pour plus d’informations sur la configuration manuelle des autorisations de partage.

>En raison de l’impossibilité d’accéder aux autorisations de partage sur un partage DFS, Skype entreprise Server ne peut pas définir explicitement les groupes sur le partage de fichiers. Pour vous assurer que les composants Skype entreprise Server peuvent accéder au partage de fichiers avec les autorisations appropriées, vérifiez que les groupes RTC suivants sont ajoutés avec des autorisations de partage de lecture et de modification en plus des autorisations de partage de contrôle total des administrateurs locaux autorisations.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
