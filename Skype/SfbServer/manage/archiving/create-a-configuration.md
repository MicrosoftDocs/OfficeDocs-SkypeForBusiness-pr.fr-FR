---
title: Créer une configuration d’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Résumé : Découvrez comment créer une configuration d’archivage pour Skype entreprise Server.'
ms.openlocfilehash: bc7319f2de8398dd3d9e9a79948d1af6eaeb98bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818956"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Créer une configuration d’archivage dans Skype entreprise Server

**Résumé :** Découvrez comment créer une configuration d’archivage pour Skype entreprise Server.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurer les options d’archivage à l’aide du panneau de configuration

Pour configurer des options d’archivage pour un site ou un pool : 
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.
    
4. Dans la page **Configuration de l’archivage**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes : 
    
   - Pour créer une configuration d’archivage de site, cliquez sur **Configuration du site** et, dans **Sélectionner un site**, indiquez le site à configurer pour l’archivage.
    
   - Pour créer une configuration d’archivage de pool, cliquez sur **Configuration du pool** et, dans **Sélectionner un pool**, indiquez le pool à configurer pour l’archivage.
    
5. Dans **Nouveau paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
   - Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
   - Afin d’activer l’archivage aussi bien pour les sessions de messagerie instantanée que les conférences web, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.
    
   - Afin de désactiver l’archivage pour cette configuration, cliquez sur **Désactiver l’archivage**.
    
6. Aussi, dans **Créer un paramètre d’archivage**, procédez comme suit :
    
   - Pour bloquer toute activité si l’archivage n’est pas disponible, cochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server pour stocker des données d’archivage, activez la case à cocher **intégration Microsoft Exchange** .
    
   - Pour activer la fonctionnalité de vidage des données, cochez la case **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
     - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
     - Pour limiter le vidage aux données d’archivage exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
7. Cliquez sur **Valider**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurer les options d’archivage à l’aide de Windows PowerShell

Vous pouvez aussi configurer des options d’archivage pour un site ou un pool spécifique en utilisant l’applet de commande **New-CsArchivingConfiguration**.
  
La commande suivante crée une collection de paramètres de configuration d’archivage pour le site Redmond :
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. 
  
Pour créer des paramètres qui utilisent des valeurs de propriété différentes, il suffit d’inclure le paramètre et la valeur de paramètre appropriés. L’exemple suivant crée une collection de paramètres de configuration d’archivage qui, par défaut, autorise uniquement l’archivage des sessions de messagerie instantanée :
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour archiver les sessions de messagerie instantanée et pour bloquer la messagerie du service d’archivage afin de le rendre non disponible :
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .
