---
title: Configurer les options d’archivage pour gérer les échecs dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Résumé : Découvrez comment bloquer des sessions de messagerie instantanée et de conférence en cas de panne du serveur Skype entreprise qui empêcherait l’archivage.'
ms.openlocfilehash: ed8a59a8c19ace9a83b699e1b69515f52c3af010
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992751"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurer les options d’archivage pour gérer les échecs dans Skype entreprise Server

**Résumé :** Découvrez comment bloquer des sessions de messagerie instantanée et de conférence en cas de panne du serveur Skype entreprise qui empêcherait l’archivage.
  
Dans le cas où l’archivage est requis pour votre organisation, vous pouvez bloquer des sessions de messagerie instantanée et de conférence en cas de panne du serveur Skype entreprise qui empêcherait l’archivage. Cet état est parfois appelé « mode critique ». Par exemple, en cas de problème au niveau du service de stockage, la messagerie instantanée peut être bloquée pour les utilisateurs dont l’archivage des communications est activé. La récupération des sessions de messagerie instantanée et de conférence est effectuée automatiquement après la correction des échecs. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurer le mode critique à l’aide du panneau de configuration

Pour préciser si des sessions de communication sont autorisées en cas de panne qui empêcherait l’archivage :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, et enfin sur **Afficher les détails**.
    
5. Pour définir le comportement de l’archivage en cas d’échec, cochez ou décochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
6. Cliquez sur **Valider**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurer le mode critique à l’aide de Windows PowerShell

Vous pouvez également spécifier si les sessions de communication doivent être autorisées en cas d’échec qui empêcherait l’archivage à l’aide de la cmdlet **Set-CsArchivingConfiguration** avec le paramètre BlockOnArchiveFailure.
  
Par exemple, la commande suivante désactive les communications dans le cas d’une erreur d’archivage :
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

La commande suivante active les communications en cas de panne d’archivage :
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .
  

