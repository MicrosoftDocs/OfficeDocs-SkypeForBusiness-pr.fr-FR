---
title: Gestion des stratégies d’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Résumé : Apprenez à gérer les stratégies de l’utilisateur pour l’archivage de Skype pour Business Server 2015.'
ms.openlocfilehash: 584849862e106098bc4bbad92ed4e0b87be410e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-policies-in-skype-for-business-server-2015"></a>Gestion des stratégies d’archivage dans Skype Entreprise Server 2015

**Résumé :** Découvrez comment gérer les stratégies de l’utilisateur pour l’archivage de Skype pour Business Server 2015.
  
Vous définissez initialement politiques d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations d’après le déploiement. Les stratégies d’archivage déterminent s’il faut archiver : 
  
- Communications internes
    
- Communications externes
    
Politiques d’archivage peuvent être définies au niveau global, du site ou niveau de l’utilisateur.
  
> [!NOTE]
> Si vous activé l’intégration de Microsoft Exchange pour votre déploiement, le contrôle des stratégies Exchange si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et que leurs boîtes aux lettres sur Place maintenez. Pour plus d’informations, consultez [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md) et [configurer une intégration avec le stockage Exchange pour Skype pour Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gérer les options d’archivage via le Panneau de configuration

Vous pouvez gérer les stratégies d’archivage via le Panneau de configuration comme suit :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Stratégie d’archivage**.
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gérer les stratégies d’archivage via Windows PowerShell

Vous pouvez également configurer les stratégies d’archivage via les applets de commande Windows PowerShell répertoriées dans le tableau suivant. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, consultez [Skype pour Business Server 2015 Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Retourne des informations sur les stratégies d’archivage des sessions de messagerie instantanée de votre organisation.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à un groupe d’utilisateurs. Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.  <br/> |
|Nouvelle-CsArchivingPolicy  <br/> |Crée des stratégies d’archivage des sessions de messagerie instantanée. Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.  <br/> |
|Supprimer-CsArchivingPolicy  <br/> |Supprime le spécifié messagerie instantanée (MI) d’archivage de stratégie qui détermine si les Skype pour Business Server enregistre automatiquement toutes les sessions de messagerie instantanée qui ont lieu entre les utilisateurs internes, ou toutes les sessions de messagerie instantanée entre des utilisateurs internes et des partenaires fédérés.  <br/> |
|Ensemble-CsArchivingPolicy  <br/> |Modifie un existant messagerie instantanée (MI stratégie d’archivage). Une stratégie d’archivage vous donne la possibilité d’archiver toutes les sessions de messagerie instantanée et les conférences qui ont lieu entre des utilisateurs internes ; Vous pouvez également archiver les sessions qui ont lieu entre les utilisateurs internes et des partenaires fédérés.  <br/> |
   

