---
title: Gérer les stratégies d’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Résumé: Découvrez comment gérer les stratégies utilisateur pour l’archivage de Skype entreprise Server.'
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278425"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gérer les stratégies d’archivage dans Skype entreprise Server

**Résumé:** Découvrez comment gérer les stratégies utilisateur pour l’archivage de Skype entreprise Server.
  
Vous définissez initialement des stratégies d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Les stratégies d’archivage déterminent s’il convient d’archiver les éléments suivants: 
  
- Communications internes
    
- Communications externes
    
Les stratégies d’archivage peuvent être définies au niveau global, de site ou d’utilisateur.
  
> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies Exchange contrôlent la mise en place de l’archivage pour les utilisateurs hébergés sur Exchange et ayant leurs boîtes aux lettres en attente. Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md) et configuration de l' [intégration avec le stockage Exchange pour Skype entreprise Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gérer les options d’archivage via le Panneau de configuration

Vous pouvez gérer les stratégies d’archivage via le Panneau de configuration comme suit :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Stratégie d’archivage**.
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gérer les stratégies d’archivage via Windows PowerShell

Vous pouvez également configurer les stratégies d’archivage via les applets de commande Windows PowerShell répertoriées dans le tableau suivant. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, reportez-vous à la rubrique [Skype entreprise Server Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Retourne des informations sur les stratégies d’archivage des sessions de messagerie instantanée de votre organisation.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à un groupe d’utilisateurs. Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.  <br/> |
|New-CsArchivingPolicy  <br/> |Crée des stratégies d’archivage des sessions de messagerie instantanée. Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Supprime la stratégie d’archivage de messagerie instantanée spécifiée qui détermine si Skype entreprise Server enregistre automatiquement toutes les sessions de messagerie instantanée qui se produisent entre les utilisateurs internes et/ou toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires fédérés.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifie une stratégie d’archivage de messagerie instantanée existante. Une stratégie d’archivage vous donne la possibilité d’archiver toutes les sessions et conférences de messagerie instantanée qui se produisent entre les utilisateurs internes; vous pouvez également archiver des sessions qui interviennent entre des utilisateurs internes et des partenaires fédérés.  <br/> |
   

