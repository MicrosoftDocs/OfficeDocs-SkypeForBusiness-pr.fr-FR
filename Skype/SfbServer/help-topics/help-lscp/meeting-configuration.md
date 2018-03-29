---
title: Configuration de la réunion
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Meeting configuration settings define the type of conferences (also calledmeetings) that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. Ces paramètres ne concernent que les réunions planifiées. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.
ms.openlocfilehash: 1318f2eee75809e736ce04af01eb2f2563b86f0f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="meeting-configuration"></a>Configuration de la réunion
 
Les paramètres de configuration de réunion définissent le type de conférence (également appelées « réunions ») que les utilisateurs peuvent créer. Ils contrôlent également la façon dont les utilisateurs anonymes et les utilisateurs de conférences rendez-vous peuvent participer aux conférences et s’ils peuvent y participer. Ces paramètres concernent uniquement les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client. 
  
Les configurations de réunion s’appliquent au niveau du site, au niveau du pool ou au niveau global :
  
- **Global meeting configuration:** The global meeting configuration is created by default. You can edit the global meeting configuration, but you cannot delete it. If you try to remove the global meeting configuration, all the settings are reset to the default values.
    
- **Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site. Site configurations override the global configuration.
    
- **Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool. Pool configurations override the global configuration and site configurations.
    
La page **Configuration de la réunion** affiche la liste de toutes les configurations de réunion définies pour votre organisation.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Configuration de la réunion**, vous pouvez effectuer les tâches suivantes :
  
- Création d’une configuration de réunion de site ou configuration de réunion de pool
    
- Modification de la configuration globale ou d’une configuration de site ou de pool existante
    
- Suppression d’une configuration de site ou de pool
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.
  
- **New** Starts a new site meeting configuration or pool meeting configuration.
    
- **Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.
    
    > [!NOTE]
    > Pour la configuration de réunion globale, la commande **Supprimer** restaure les valeurs par défaut des paramètres.
  
- **Refresh** Refreshes the list of meeting configurations.
    
La liste ci-dessous décrit les champs de la page.
  
- **Name** Identifies the meeting configuration.
    
- **Scope** Identifies the scope of the meeting configuration: global, site, or pool.
    
For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.
  

