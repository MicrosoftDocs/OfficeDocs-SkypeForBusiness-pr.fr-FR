---
title: Gérer les stratégies d’archivage de Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Résumé : Découvrez comment gérer les stratégies d’utilisateur pour l’archivage pour Skype pour Business Server.'
ms.openlocfilehash: 289902ded6f1530c74f9c945517a3c853c99d364
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873239"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gérer les stratégies d’archivage de Skype pour Business Server

**Résumé :** Découvrez comment gérer les stratégies d’utilisateur pour l’archivage pour Skype pour Business Server.
  
Vous définissez initialement des stratégies d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Si vous souhaitez archiver déterminent les stratégies d’archivage : 
  
- Communications internes
    
- Communications externes
    
Les stratégies d’archivage peuvent être définies au niveau global, site ou au niveau utilisateur.
  
> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, le contrôle des stratégies Exchange si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et mettre les boîtes aux lettres en blocage sur Place. Pour plus d’informations, voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md) et [configurer l’intégration avec le stockage Exchange pour Skype pour Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gérer les options d’archivage via le Panneau de configuration

Vous pouvez gérer les stratégies d’archivage via le Panneau de configuration comme suit :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Stratégie d’archivage**.
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gérer les stratégies d’archivage via Windows PowerShell

Vous pouvez également configurer les stratégies d’archivage via les applets de commande Windows PowerShell répertoriées dans le tableau suivant. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, voir [Skype pour Business Server Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Retourne des informations sur les stratégies d’archivage des sessions de messagerie instantanée de votre organisation.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à un groupe d’utilisateurs. Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.  <br/> |
|New-CsArchivingPolicy  <br/> |Crée des stratégies d’archivage des sessions de messagerie instantanée. Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Supprime le spécifié messagerie instantanée (MI) qui détermine si Skype pour Business Server doit enregistrer automatiquement toutes les sessions de messagerie instantanée qui ont lieu entre les utilisateurs internes et/ou toutes les sessions de messagerie instantanée entre utilisateurs internes et des partenaires fédérés stratégie d’archivage.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifie une existante la messagerie instantanée (MI) stratégie d’archivage. Une stratégie d’archivage vous donne la possibilité d’archiver tous les sessions de messagerie instantanée et les conférences qui ont lieu entre les utilisateurs internes ; Vous pouvez également archiver les sessions qui ont lieu entre les utilisateurs internes et des partenaires fédérés.  <br/> |
   

