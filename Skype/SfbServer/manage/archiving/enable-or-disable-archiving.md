---
title: Activer ou désactiver l’archivage dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Résumé : Découvrez comment activer ou désactiver l’archivage dans Skype pour Business Server.'
ms.openlocfilehash: a0d32a3bacb604c326db13034bf5315c7f3d4d99
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965890"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Activer ou désactiver l’archivage dans Skype pour Business Server

**Résumé :** Découvrez comment activer ou désactiver l’archivage dans Skype pour Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Activer ou désactiver l’archivage à l’aide du panneau de configuration

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Sélectionnez la configuration de pool, de site ou globale appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :
    
   - Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
   - Pour activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.
    
   - Afin de désactiver l’archivage pour la configuration, cliquez sur **Désactiver l’archivage**.
    
5. Cliquez sur **Valider**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Activer ou désactiver l’archivage à l’aide de Windows PowerShell

Vous pouvez activer ou désactiver l’archivage à l’aide de l’applet de commande **Set-CsArchivingConfiguration**. Par exemple, la commande suivante modifie tous les paramètres de configuration de l’archivage pour que seules les sessions de messagerie instantanée soient archivées. La commande appelle l’applet de commande **Get-CsArchivingConfiguration** sans aucun paramètre afin de retourner tous les paramètres de configuration d’archivage actuellement utilisées dans l’organisation. Cette collection est ensuite redirigée vers la cmdlet **Where-Object** , qui sélectionne uniquement les paramètres dont la propriété EnableArchiving est égale à (-eq) « ImAndWebConf ». La collection filtrée est ensuite redirigée vers la cmdlet **Set-CsArchivingConfiguration** , qui prend chaque élément dans la collection et modifie la valeur de EnableArchiving sur « ImOnly » :
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```