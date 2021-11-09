---
title: Configurer les options d’archivage pour gérer les défaillances dans Skype Entreprise Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Résumé : Découvrez comment bloquer les sessions de messagerie instantanée et de conférence en cas d’Skype Entreprise Server qui empêcherait l’archivage.'
ms.openlocfilehash: f3f20bf53a784972c720ce5578d78462cbb222c8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836466"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurer les options d’archivage pour gérer les défaillances dans Skype Entreprise Server

**Résumé :** Découvrez comment bloquer les sessions de messagerie instantanée et de conférence en cas de Skype Entreprise Server d’archivage.
  
Si l’archivage est une condition requise pour votre organisation, vous pouvez bloquer les sessions de messagerie instantanée et de conférence en cas d’échec Skype Entreprise Server qui empêcherait l’archivage. Ce mode est parfois appelé mode critique. Par exemple, en cas de problème avec un service de stockage, la messagerie instantanée est bloquée pour les utilisateurs dont les communications sont activées pour l’archivage. La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurer le mode critique à l’aide du Panneau de configuration

Pour spécifier si les sessions de communication doivent être autorisées en cas de défaillance qui empêcherait l’archivage :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
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
