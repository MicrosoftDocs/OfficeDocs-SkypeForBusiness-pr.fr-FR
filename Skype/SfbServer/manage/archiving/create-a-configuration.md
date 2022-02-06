---
title: Créer une configuration d’archivage dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Résumé : Découvrez comment créer une configuration d’archivage pour Skype Entreprise Server.'
---

# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Créer une configuration d’archivage dans Skype Entreprise Server

**Résumé :** Découvrez comment créer une configuration d’archivage pour Skype Entreprise Server.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurer les options d’archivage à l’aide du Panneau de configuration

Pour configurer les options d’archivage pour un site ou un pool spécifique : 
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Dans la page **Configuration de l’archivage** , cliquez sur **Nouveau**, puis faites l’une des opérations suivantes : 
    
   - Pour créer une configuration d’archivage de site, cliquez sur **Configuration** du site, puis dans Sélectionner un **site**, sélectionnez le site à configurer pour l’archivage.
    
   - Pour créer une configuration d’archivage de pool, cliquez sur **Configuration** du pool, puis dans Sélectionner un **pool**, sélectionnez le pool à configurer pour l’archivage.
    
5. Dans **Créer un paramètre d’archivage**, dans la liste déroulante **Paramètre d’archivage**, effectuez l’une des actions suivantes :
    
   - Afin d’activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
   - Pour activer l’archivage pour les sessions de messagerie instantanée et les conférences web, cliquez sur **Archiver les sessions** de messagerie instantanée et de conférence web.
    
   - Pour désactiver l’archivage pour cette configuration, cliquez **sur Désactiver l’archivage**.
    
6. Dans **Créer un paramètre d’archivage**, procédez comme suit :
    
   - Pour bloquer toute activité quand l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.
    
   - Pour utiliser Microsoft Exchange Server stocker les données d’archivage, cliquez sur la case à **cocher** Intégration Exchange Microsoft.
    
   - Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :
    
     - Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.
    
     - Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
7. Cliquez sur **Valider**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurer les options d’archivage à l’aide Windows PowerShell

Vous pouvez également configurer les options d’archivage d’un site ou d’un pool  spécifique à l’aide de l';
  
La commande suivante crée une collection de paramètres de configuration d’archivage pour le site Redmond :
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. 
  
Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. L’exemple suivant crée une collection de paramètres de configuration d’archivage qui, par défaut, autorisent uniquement l’archivage des sessions de messagerie instantanée :
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres pour archiver les sessions de messagerie instantanée et pour bloquer la messagerie instantanée du service d’archivage n’est pas disponible :
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .