---
title: Expanseur des paramètres généraux du serveur d’archivage
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Dans le Générateur de topologie, vous pouvez modifier les propriétés d’un serveur individuel exécutant l’archivage en cliquant avec le bouton droit sur le serveur exécutant l’archivage dans l’arborescence de la console et en cliquant sur Action dans la barre d’outils, ou en cliquant sur une tâche dans le volet Actions, puis en cliquant sur Modifier les propriétés et en modifiant l’une des options suivantes :'
ms.openlocfilehash: a16c239706bfc83a2798f26b05386429dfa80c6b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584198"
---
# <a name="archiving-server-general-settings-expander"></a>Expandeur des paramètres généraux du serveur d’archivage
 
Dans le Générateur de topologie, vous pouvez modifier les propriétés d’un serveur individuel exécutant l’archivage en cliquant avec le bouton droit sur le serveur exécutant l’archivage dans l’arborescence de la console et en cliquant sur **Action** dans la barre d’outils, ou en cliquant sur une tâche dans le volet Actions, puis en cliquant sur Modifier les propriétés et en modifiant l’une des options suivantes : 
  
- **Nom de domaine complet (FQDN)**, pour modifier le nom de domaine complet (FQDN) du serveur que vous souhaitez déployer en tant que serveur exécutant l’archivage.
    
- **Magasin SQL**, pour modifier l’instance SQL Server à utiliser pour la base de données SQL Server d’archivage. Si vous modifiez la base de données SQL Server d’un serveur exécutant l’archivage, vous devez redémarrer le serveur exécutant l’archivage pour que la modification prenne effet.
    
- **Partage de fichiers**, pour modifier le dossier utilisé pour l’archivage du magasin de fichiers. Si vous modifiez le partage de fichiers d’un serveur exécutant l’archivage, vous devez redémarrer le serveur exécutant l’archivage pour que la modification prenne effet. En outre, vous devez déplacer les fichiers de conférence précédents vers le nouveau dossier du magasin de fichiers pour éviter de perdre des fichiers de conférence archivés.
    
> [!NOTE]
> Pour modifier les pools associés à un serveur exécutant l’archivage, sélectionnez l’option **Modifier les propriétés** du nœud du pool frontal individuel ou du nœud Survivable Branch Appliance actuellement associé au serveur exécutant l’archivage.
  
> [!NOTE]
> Le nœud Archivage contient un serveur exécutant l’archivage si vous avez précédemment ajouté un serveur exécutant l’archivage à la topologie dans le Générateur de topologie. Vous pouvez modifier les propriétés de n’importe quel serveur exécutant l’archivage dans la liste. Toutefois, la messagerie instantanée ou la conférence web (messagerie) ne peut pas être archivée tant que vous n’avez pas également mis en place le service pour le serveur exécutant l’archivage. 
  

