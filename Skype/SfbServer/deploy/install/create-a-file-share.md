---
title: Création d’un partage de fichiers dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Résumé: Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverMicrosoft pour:.'
ms.openlocfilehash: d6a34ad4807948a5580fc572628a4fd6333dd9f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292164"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>Création d’un partage de fichiers dans Skype entreprise Server
 
**Résumé:** Découvrez comment créer un partage de fichiers Windows Server dans le cadre de l’installation de Skype entreprise Server. Télécharger une version d’évaluation gratuite de Skype entreprise Server à partir du centre d’évaluation[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Microsoft pour:.
  
Pour pouvoir échanger des fichiers, Skype entreprise Server a besoin d’un partage de fichiers. La création d’un partage de fichiers est l’étape 2 sur 8 du processus d’installation de Skype entreprise Server. Vous pouvez effectuer les étapes 1 à 5 dans n’importe quel ordre. Cependant, vous devez exécuter les étapes 6, 7 et 8 dans l’ordre, et après les étapes 1 à 5 comme indiqué sur le diagramme. Pour plus d’informations sur la planification du partage de fichiers, voir la [Configuration requise pour Skype entreprise Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [serveur requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Schéma de vue d’ensemble](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>Créer un partage de fichiers basique

Cette section vous indique comment créer un partage de fichiers Serveur Windows basique. Un partage de fichiers Windows Server de base est pris en charge avec Skype entreprise Server. Toutefois, elle ne fournit pas explicitement une haute disponibilité. Pour un environnement à haute disponibilité, un partage de fichiers Système de fichiers distribué DFS est recommandé. Pour plus d’informations sur le partage de fichiers et le système de fichiers DFS de haute disponibilité, voir [planifier une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Windows Server 2012 R2 a effectué un bond de géant en offrant des solutions de partage de fichiers de type SAN (Storage Area Network) à l’aide de la plateforme Windows Server. Comparée à un dispositif SAN traditionnel, une solution de stockage Windows Server 2012 R2 permet de diviser les coûts par deux sans réelles incidences sur les performances. Pour plus d’informations sur les options de partage de fichiers dans Windows Server 2012 R2, voir le livre blanc téléchargeable [Windows server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf). 
  
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
  
> [!NOTE]
>Si le magasin de fichiers est hébergé sur un partage DFS, le message d’avertissement suivant est reçu:

AVERTISSEMENT: impossible d’accéder aux autorisations de partage\\<domain>\<pour «share>».

>Cela peut se produire si vous n’êtes pas administrateur sur le serveur de fichiers ou s’il s’agit d’un partage du système de fichiers DFS. Si les autorisations de partage ont déjà été configurées, cet avertissement peut être ignoré. S’il s’agit d’un nouveau partage, reportez-vous à la documentation pour plus d’informations sur la configuration manuelle des autorisations de partage.

>En raison de l’incapacité d’accéder aux autorisations de partage sur un partage DFS, Skype entreprise Server ne peut pas définir explicitement les groupes sur le partage de fichiers. Pour vous assurer que les composants de Skype entreprise Server peuvent accéder au partage de fichiers avec les autorisations appropriées, assurez-vous que les groupes RTC suivants sont ajoutés en plus des autorisations de partage de niveau supérieur.

RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins
