---
title: Activer ou désactiver l’archivage dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Résumé : Découvrez comment activer ou désactiver l’archivage dans Skype pour Business Server.'
ms.openlocfilehash: 27cb7aab08c6a85f21e058848963bb42de6e1635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885030"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Activer ou désactiver l’archivage dans Skype pour Business Server

**Résumé :** Découvrez comment activer ou désactiver l’archivage dans Skype pour Business Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Activer ou désactiver l’archivage à l’aide du panneau de configuration

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.
    
4. Sélectionnez la configuration de pool, de site ou globale appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :
    
   - Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
   - Pour activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.
    
   - Afin de désactiver l’archivage pour la configuration, cliquez sur **Désactiver l’archivage**.
    
5. Cliquez sur **Valider**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Activer ou désactiver l’archivage à l’aide de Windows PowerShell

Vous pouvez activer ou désactiver l’archivage à l’aide de l’applet de commande **Set-CsArchivingConfiguration**. Par exemple, la commande suivante modifie tous les paramètres de configuration de l’archivage pour que seules les sessions de messagerie instantanée soient archivées. Pour cela, la commande appelle d’abord l’applet de commande **Get-CsArchivingConfiguration** sans paramètre afin de retourner une collection de tous les paramètres de configuration de l’archivage utilisés dans l’organisation. Cette collection est alors redirigée vers l’applet de commande **Where-Object** qui sélectionne uniquement les paramètres dont la propriété EnableArchiving est égale à (-eq) « ImAndWebConf ». La collection filtrée est ensuite redirigée vers l’applet de commande **Set-CsArchivingConfiguration** qui extrait chaque élément de la collection et définit la valeur de la propriété EnableArchiving sur « ImOnly » :
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
