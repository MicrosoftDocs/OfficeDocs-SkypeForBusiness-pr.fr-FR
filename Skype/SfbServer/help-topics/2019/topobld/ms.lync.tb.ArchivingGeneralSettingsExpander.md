---
title: Développeur des paramètres généraux du serveur d’archivage
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Dans le générateur de topologie, vous pouvez modifier les propriétés d’un serveur individuel exécutant l’archivage en cliquant sur le serveur avec le bouton droit dans l’arborescence de la console, puis sur Action dans la barre d’outils ou en cliquant sur une tâche dans le volet Actions, puis sur Modifier les propriétés pour modifier l’une des options suivantes :'
ms.openlocfilehash: f75614f1720466a4a4d4ba27ef5542e2cfd4036e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887096"
---
# <a name="archiving-server-general-settings-expander"></a>Développeur des paramètres généraux du serveur d’archivage
 
Dans le générateur de topologie, vous pouvez modifier les propriétés d’un serveur individuel exécutant l’archivage en cliquant sur le serveur avec le bouton droit dans l’arborescence de la console, puis sur **Action** dans la barre d’outils ou en cliquant sur une tâche dans le volet Actions, puis sur **Modifier les propriétés** pour modifier l’une des options suivantes :
  
- **Nom de domaine complet (FQDN)**  : permet de modifier le nom de domaine complet (FQDN) du serveur que vous souhaitez déployer comme serveur exécutant l’archivage.
    
- **Magasin SQL** : permet de modifier l’instance SQL Server à utiliser pour la base de données SQL Server d’archivage. Si vous modifiez la base de données SQL Server d’un serveur exécutant l’archivage, vous devez relancer le serveur exécutant l’archivage pour que la modification prenne effet.
    
- **Partage de fichiers** : permet de modifier le dossier utilisé pour l’archivage du magasin de fichiers. Si vous modifiez le partage de fichiers d’un serveur exécutant l’archivage, vous devez relancer le serveur exécutant l’archivage pour que la modification prenne effet. De plus, vous devez déplacer les fichiers de conférence précédents vers le nouveau dossier du magasin de fichiers pour éviter de perdre des fichiers de conférence archivés.
    
> [!NOTE]
> Pour modifier les pools associés à un serveur exécutant l’archivage, sélectionnez l’option **Modifier les propriétés** du nœud du pool frontal individuel ou du nœud Survivable Branch Appliance actuellement associé au serveur exécutant l’archivage.
  
> [!NOTE]
> Le nœud Archivage contient un serveur exécutant l’archivage si vous avez ajouté précédemment un serveur exécutant l’archivage à la topologie dans le générateur de topologie. Vous pouvez modifier les propriétés des serveurs exécutant l’archivage dans la liste. Cependant, les conversations de messagerie instantanée ou de conférence web (messagerie) ne peuvent pas être archivées tant que le service n’a pas été également configuré pour le serveur exécutant l’archivage. 
  

