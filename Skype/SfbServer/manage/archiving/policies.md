---
title: Gérer les stratégies d’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Résumé : Découvrez comment gérer les stratégies utilisateur pour l’archivage des Skype Entreprise Server.'
ms.openlocfilehash: c4d5278ece9c812254c67d2d783b5a9f9175330c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397798"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gérer les stratégies d’archivage dans Skype Entreprise Server

**Résumé :** Découvrez comment gérer les stratégies utilisateur pour l’archivage des Skype Entreprise Server.
  
Vous définissez initialement les stratégies d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Les stratégies d’archivage déterminent s’il faut archiver : 
  
- Communications internes
    
- Communications externes
    
Les stratégies d’archivage peuvent être définies au niveau global, du site ou de l’utilisateur.
  
> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies Exchange contrôlent si l’archivage est activé pour les utilisateurs qui sont Exchange et dont les boîtes aux lettres sont mises en In-Place. Pour plus d’informations, voir [Plan for archiving in Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype Entreprise Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gérer les stratégies d’archivage à l’aide du Panneau de contrôle

Vous pouvez gérer les stratégies d’archivage à l’aide du Panneau de contrôle comme suit :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Stratégie d’archivage**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gérer les stratégies d’archivage à l’aide Windows PowerShell

Vous pouvez également configurer des stratégies d’archivage à l’aide Windows PowerShell cmdlets répertoriées dans le tableau suivant. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, [voir Skype Entreprise Server Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Retourne des informations sur les stratégies d’archivage des sessions de messagerie instantanée de votre organisation.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Affecte des stratégies d’archivage de session de messagerie instantanée à des utilisateurs ou à des ensembles d’utilisateurs. Ces stratégies vous donnent la possibilité d’archiver les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes, et/ou d’archiver toutes les sessions de messagerie instantanée qui ont lieu entre des utilisateurs internes et des partenaires extérieurs.  <br/> |
|New-CsArchivingPolicy  <br/> |Crée des stratégies d’archivage des sessions de messagerie instantanée. Ces stratégies permettent d’archiver toutes les sessions entre les utilisateurs internes et/ou d’archiver toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires externes.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Supprime la stratégie d’archivage de messagerie instantanée spécifiée qui détermine si Skype Entreprise Server enregistre automatiquement toutes les sessions de messagerie instantanée qui ont lieu entre les utilisateurs internes et/ou toutes les sessions de messagerie instantanée entre les utilisateurs internes et les partenaires fédérés.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifie une stratégie d’archivage de messagerie instantanée existante. Une stratégie d’archivage vous permet d’archiver toutes les sessions de messagerie instantanée et les conférences qui ont lieu entre des utilisateurs internes ; vous pouvez également archiver les sessions qui ont lieu entre les utilisateurs internes et les partenaires fédérés.  <br/> |
   

