---
title: Créer un partage de fichiers dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Résumé : Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype Entreprise Server. Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du Centre d’évaluation Microsoft à l’adresse : https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812234"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Créer un partage de fichiers dans Skype Entreprise Server
 
**Résumé :** Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype Entreprise Server. Téléchargez une version d’évaluation gratuite de Skype Entreprise Server à partir du Centre d’évaluation Microsoft à l’adresse : [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Skype Entreprise Server nécessite un partage de fichiers afin que les ordinateurs de la topologie peuvent échanger des fichiers. La création d’un partage de fichiers est l’étape 2 sur 8 du processus d’installation de Skype Entreprise Server. Vous pouvez suivre les étapes 1 à 5 dans n’importe quel ordre. Toutefois, vous devez suivre les étapes 6, 7 et 8 dans l’ordre et après les étapes 1 à 5, comme indiqué dans le diagramme. Pour plus d’informations sur la planification du partage de fichiers, voir [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Diagramme de vue d’ensemble](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Créer un partage de fichiers de base

Cette section vous présente la création d’un partage de fichiers Windows Server de base. Un partage de fichiers Windows Server de base est pris en charge avec Skype Entreprise Server. Toutefois, il ne fournit pas explicitement la haute disponibilité. Pour un environnement de haute disponibilité, un partage de fichiers DFS (Distributed File System) est recommandé. Pour plus d’informations sur un partage de fichiers haute disponibilité et DFS, voir Planifier la haute disponibilité et la récupération d’urgence [dans Skype Entreprise Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
> [!NOTE]
> Windows Server 2012 R2 a réalisé des sauts majeurs dans la fourniture de solutions de partage de fichiers de même qu’un réseau de zone de stockage (SAN) à l’aide de la plateforme Windows Server. Comparée à une appliance SAN traditionnelle, une solution de stockage Windows Server 2012 R2 peut réduire les coûts de moitié avec un impact minime sur les performances. Pour plus d’informations sur les options de partage de fichiers dans Windows Server 2012 R2, voir le livre blanc [téléchargeable Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
Regardez les étapes de la vidéo **pour créer un partage de fichiers**:
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>Créer un partage de fichiers de base

1. Connectez-vous à l’ordinateur qui hébergera le partage de fichiers.
    
2. Cliquez avec le bouton droit sur le dossier que vous prévoyez de partager, puis sélectionnez **Propriétés.**
    
3. Sélectionnez **l’onglet** Partage, puis cliquez **sur Partage avancé.**
    
4. Cliquez **sur Partager ce dossier.**
    
5. Cliquez sur **Autorisations**.
    
6. Ajoutez le groupe **Administrateurs** local du serveur hébergeant le partage de fichiers, accordez les droits Autoriser : Contrôle **total,** Modification et Lecture, puis cliquez sur **OK.**
    
7. Cliquez **à nouveau** sur OK et notez le chemin d’accès réseau.
    
8. Cliquez **sur Terminé** pour fermer l’Assistant.
    
     ![Onglet de partage pour le partage d’un dossier.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>Si le magasin de fichiers est hébergé sur un partage DFS, l’avertissement suivant est reçu :

Avertissement : Impossible d’accéder aux autorisations de partage pour « \\ <domain> \<share> ».

>Cela est attendu si vous n’êtes pas administrateur sur le serveur de fichiers ou s’il s’agit d’un partage de système de fichiers distribués (DFS). Si les autorisations de partage ont déjà été configurées, cet avertissement peut être ignoré. S’il s’agit d’un nouveau partage, reportez-vous à la documentation pour plus d’informations sur la configuration manuelle des autorisations de partage.

>En raison de l’impossibilité d’accéder aux autorisations de partage sur un partage DFS, Skype Entreprise Server ne sera pas en mesure de définir explicitement des groupes sur le partage de fichiers. Pour vous assurer que les composants Skype Entreprise Server peuvent accéder au partage de fichiers avec les autorisations appropriées, assurez-vous que les groupes RTC suivants sont ajoutés avec les autorisations de partage de niveau Lecture et Modification en plus des autorisations de partage Administrateurs locaux avec contrôle total.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
