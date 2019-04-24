---
title: Gérer les options d’archivage dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Résumé : Découvrez comment configurer les options d’archivage pour Skype pour Business Server.'
ms.openlocfilehash: db0fbe113f38065e85419b05d39fd0176b5ba845
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232367"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Gérer les options d’archivage dans Skype pour Business Server

**Résumé :** Découvrez comment configurer les options d’archivage pour Skype pour Business Server.
  
Si l’archivage est initialement configuré au déploiement, vous pouvez modifier, ajouter et supprimer des configurations par la suite. Les options d’archivage déterminent : 
  
- l’activation ou la désactivation de l’archivage
    
- Archiver les sessions de messagerie instantanée
    
- Archiver les sessions de conférence Web
    
- Bloquer l’activité lorsque l’archivage n’est pas disponible
    
- Utiliser l’intégration à Exchange
    
- Configurer la purge et l’exportation des données
    
Vous pouvez préciser les options de configuration aux niveaux suivants :
  
- Configuration au niveau global qui est créée par défaut lorsque vous déployez Skype pour Business Server
    
- Configurations facultatives au niveau du site qui déterminent la mise en œuvre de l’archivage d’un site spécifique
    
- Configurations facultatives au niveau du pool qui spécifient comment l’archivage est implémenté pour un pool spécifique
    
Vous pouvez supprimer une configuration de site ou une configuration de pool, mais vous ne pouvez pas supprimer la configuration globale. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies. Pour plus d’informations sur l’implémentation des configurations d’archivage et la hiérarchie des configurations, d’archivage voir [planifier l’archivage dans Skype pour Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurer les options d’archivage à l’aide du panneau de configuration

Vous pouvez configurer les options d’archivage à l’aide du panneau de configuration comme suit :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Configuration d’archivage**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurer les options d’archivage à l’aide de Windows PowerShell

Vous pouvez également configurer les options d’archivage à l’aide des applets de commande de Windows PowerShell figurant dans le tableau ci-après. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, voir [Skype pour Business Server Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Retourne des informations sur les paramètres de configuration d’archivage de votre organisation.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crée un nouveau jeu de paramètres pour la messagerie instantanée qui peuvent être utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer les messages instantanés qu’il n’est pas possible d’archiver.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Supprime la collection spécifiée de paramètres d’archivage utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer éventuellement tout message instantané ne pouvant pas être archivé.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifie une collection existante d’options de configuration d’archivage de la messagerie instantanée.  <br/> |
