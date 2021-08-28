---
title: Activer ou désactiver l’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Résumé : Découvrez comment activer ou désactiver l’archivage dans Skype Entreprise Server.'
ms.openlocfilehash: 8384c751cbcd7d5d357ca2bdefbb8821b7e282d0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621090"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Activer ou désactiver l’archivage dans Skype Entreprise Server

**Résumé :** Découvrez comment activer ou désactiver l’archivage dans Skype Entreprise Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Activer ou désactiver l’archivage à l’aide du Panneau de contrôle

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Sélectionnez la configuration de pool, de site ou globale appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :
    
   - Pour activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
   - Pour activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.
    
   - Pour désactiver l’archivage pour la configuration, cliquez **sur Désactiver l’archivage.**
    
5. Cliquez sur **Valider**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Activer ou désactiver l’archivage à l’aide Windows PowerShell

Vous pouvez également activer ou désactiver l’archivage à l’aide de l’cmdlet **Set-CsArchivingConfiguration.** Par exemple, la commande suivante modifie tous les paramètres de configuration de l’archivage afin que seules les sessions de messagerie instantanée soient archivées. La commande appelle l’cmdlet **Get-CsArchivingConfiguration** sans aucun paramètre afin de retourner tous les paramètres de configuration d’archivage actuellement utilisés dans l’organisation. Cette collection est ensuite canalisation vers l’cmdlet **Where-Object,** qui sélectionne uniquement les paramètres pour lesquels la propriété EnableArchiving est égale à (-eq) « ImAndWebConf ». La collection filtrée est ensuite canalë vers l';cmdlet **Set-CsArchivingConfiguration** qui prend chaque élément de la collection et modifie la valeur de EnableArchiving en « ImOnly » :
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
