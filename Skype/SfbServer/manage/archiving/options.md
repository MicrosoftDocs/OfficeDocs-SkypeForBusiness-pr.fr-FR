---
title: Gérer les options d’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Résumé : Découvrez comment configurer les options d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: d382cd829a9db8472df286580f6bd5d4b3baf036
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856771"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Gérer les options d’archivage dans Skype Entreprise Server

**Résumé :** Découvrez comment configurer les options d’archivage pour Skype Entreprise Server.
  
Vous configurez initialement l’archivage lors du déploiement, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Les options d’archivage déterminent s’il faut : 
  
- Activation ou désactivation de l’archivage
    
- Archiver les sessions de messagerie instantanée
    
- Archiver les sessions de conférence web
    
- Bloquer l’activité lorsque l’archivage n’est pas disponible
    
- Utiliser l’intégration Exchange des données
    
- Configurer le purgement et l’exportation des données
    
Vous pouvez spécifier des options de configuration aux niveaux suivants :
  
- Configuration au niveau global créée par défaut lorsque vous déployez Skype Entreprise Server
    
- Configurations facultatives au niveau du site qui spécifient la façon dont l’archivage est implémenté pour un site spécifique
    
- Configurations facultatives au niveau du pool qui spécifient comment l’archivage est implémenté pour un pool spécifique
    
Vous pouvez supprimer une configuration de site ou de pool, mais vous ne pouvez pas supprimer la configuration globale. Si vous supprimez la configuration globale, elle est réinitialisée automatiquement aux valeurs par défaut. Pour plus d’informations sur la façon dont les configurations d’archivage sont implémentées et la hiérarchie des configurations d’archivage, voir Planifier l’archivage [dans Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurer les options d’archivage à l’aide du Panneau de configuration

Vous pouvez configurer les options d’archivage à l’aide du Panneau de configuration comme suit :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Configuration de l’archivage.**
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurer les options d’archivage à l’aide Windows PowerShell

Vous pouvez également configurer les options d’archivage à l’aide Windows PowerShell cmdlets répertoriées dans le tableau suivant. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, [voir Skype Entreprise Server Management Shell.](../management-shell.md)
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Retourne des informations sur les paramètres de configuration de l’archivage dans votre organisation.  <br/> |
|New-CsArchivingConfiguration  <br/> |Crée un nouvel ensemble de paramètres de messagerie instantanée, qui peuvent être utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer les messages instantanés qui ne peuvent pas être archivés.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Supprime la collection spécifiée de paramètres d’archivage utilisés pour activer ou désactiver l’enregistrement automatique des sessions de messagerie instantanée et pour bloquer éventuellement les messages instantanés qui ne peuvent pas être archivés.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifie une collection existante d’options de configuration de l’archivage de la messagerie instantanée.  <br/> |
