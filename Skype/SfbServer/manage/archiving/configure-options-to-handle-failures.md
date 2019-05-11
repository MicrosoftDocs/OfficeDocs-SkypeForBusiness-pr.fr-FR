---
title: Configurer les options d’archivage pour gérer les échecs dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Résumé : Apprenez à bloquer les sessions par messagerie instantanée et de conférence dans le cas d’un Skype de défaillance du serveur d’entreprise qui empêche l’archivage.'
ms.openlocfilehash: 356db70f9e1be630b8ff6daa8b619b13caf817b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885044"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Configurer les options d’archivage pour gérer les échecs dans Skype pour Business Server

**Résumé :** Découvrez comment bloquer les sessions par messagerie instantanée et de conférence dans le cas d’un Skype de défaillance du serveur d’entreprise qui empêche l’archivage.
  
Si l’archivage est une condition requise pour votre organisation, vous pouvez bloquer les sessions de messagerie instantanée et la conférence en cas d’un Skype pour Échec Business Server qui empêche l’archivage. Cet état est parfois appelé « mode critique ». Par exemple, en cas de problème au niveau du service de stockage, la messagerie instantanée peut être bloquée pour les utilisateurs dont l’archivage des communications est activé. La récupération des sessions de messagerie instantanée et de conférence est effectuée automatiquement après la correction des échecs. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Configurer le mode critique à l’aide du panneau de configuration

Pour préciser si des sessions de communication sont autorisées en cas de panne qui empêcherait l’archivage :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, et enfin sur **Afficher les détails**.
    
5. Pour définir le comportement de l’archivage en cas d’échec, cochez ou décochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
6. Cliquez sur **Valider**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Configurer le mode critique à l’aide de Windows PowerShell

Vous pouvez également spécifier si les sessions de communication doivent être autorisées en cas de défaillance qui empêche l’archivage à l’aide de l’applet de commande **Set-CsArchivingConfiguration** avec le paramètre BlockOnArchiveFailure.
  
Par exemple, la commande suivante désactive communications dans le cas d’un échec d’archivage :
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

La commande suivante active les communications en cas de panne d’archivage :
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .
  

