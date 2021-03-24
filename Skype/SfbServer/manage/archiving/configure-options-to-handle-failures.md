---
title: Configurer les options d’archivage pour gérer les défaillances dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Résumé : Découvrez comment bloquer les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server qui empêcherait l’archivage.'
ms.openlocfilehash: 8bfe4d3f8e02fa0d7d7d3f1f6b55f224aaa1451a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095448"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurer les options d’archivage pour gérer les défaillances dans Skype Entreprise Server

**Résumé :** Découvrez comment bloquer les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server qui empêcherait l’archivage.
  
Si l’archivage est une condition requise pour votre organisation, vous pouvez bloquer les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server qui empêcherait l’archivage. Ce mode est parfois appelé mode critique. Par exemple, en cas de problème avec un service de stockage, la messagerie instantanée est bloquée pour les utilisateurs dont les communications sont activées pour l’archivage. La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurer le mode critique à l’aide du Panneau de configuration

Pour spécifier si les sessions de communication doivent être autorisées en cas de défaillance qui empêcherait l’archivage :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration globale, de site ou de pool appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**
    
5. Pour définir le comportement de l’archivage en cas d’échec, cochez ou décochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
6. Cliquez sur **Valider**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurer le mode critique à l’aide Windows PowerShell

Vous pouvez également spécifier si les sessions de communication doivent être autorisées en cas de défaillance qui empêcherait l’archivage à l’aide de l';cmdlet **Set-CsArchivingConfiguration** avec le paramètre BlockOnArchiveFailure.
  
Par exemple, la commande suivante désactive les communications en cas de défaillance de l’archivage :
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

La commande suivante active les communications en cas d’échec de l’archivage :
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Set-CsArchivingConfiguration.](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
