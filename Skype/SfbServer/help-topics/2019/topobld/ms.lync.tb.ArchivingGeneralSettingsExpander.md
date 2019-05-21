---
title: Développeur des paramètres généraux du serveur d’archivage
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: NOINDEX, NOFOLLOW
description: 'Dans le générateur de topologie, vous pouvez modifier les propriétés d’un serveur individuel exécutant l’archivage en cliquant sur le serveur avec le bouton droit dans l’arborescence de la console, puis sur Action dans la barre d’outils ou en cliquant sur une tâche dans le volet Actions, puis sur Modifier les propriétés pour modifier l’une des options suivantes :'
ms.openlocfilehash: bf2f1304cdf3beb3c49aca93839eca5c24b277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306104"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="62d59-103">Développeur des paramètres généraux du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="62d59-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="62d59-104">Dans le générateur de topologie, vous pouvez modifier les propriétés d’un serveur individuel exécutant l’archivage en cliquant sur le serveur avec le bouton droit dans l’arborescence de la console, puis sur **Action** dans la barre d’outils ou en cliquant sur une tâche dans le volet Actions, puis sur **Modifier les propriétés** pour modifier l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="62d59-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="62d59-105">**Nom de domaine complet (FQDN)**  : permet de modifier le nom de domaine complet (FQDN) du serveur que vous souhaitez déployer comme serveur exécutant l’archivage.</span><span class="sxs-lookup"><span data-stu-id="62d59-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="62d59-p101">**Magasin SQL** : permet de modifier l’instance SQL Server à utiliser pour la base de données SQL Server d’archivage. Si vous modifiez la base de données SQL Server d’un serveur exécutant l’archivage, vous devez relancer le serveur exécutant l’archivage pour que la modification prenne effet.</span><span class="sxs-lookup"><span data-stu-id="62d59-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="62d59-p102">**Partage de fichiers** : permet de modifier le dossier utilisé pour l’archivage du magasin de fichiers. Si vous modifiez le partage de fichiers d’un serveur exécutant l’archivage, vous devez relancer le serveur exécutant l’archivage pour que la modification prenne effet. De plus, vous devez déplacer les fichiers de conférence précédents vers le nouveau dossier du magasin de fichiers pour éviter de perdre des fichiers de conférence archivés.</span><span class="sxs-lookup"><span data-stu-id="62d59-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="62d59-111">Pour modifier les pools associés à un serveur exécutant l’archivage, sélectionnez l’option **Modifier les propriétés** du nœud du pool frontal individuel ou du nœud Survivable Branch Appliance actuellement associé au serveur exécutant l’archivage.</span><span class="sxs-lookup"><span data-stu-id="62d59-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62d59-p103">Le nœud Archivage contient un serveur exécutant l’archivage si vous avez ajouté précédemment un serveur exécutant l’archivage à la topologie dans le générateur de topologie. Vous pouvez modifier les propriétés des serveurs exécutant l’archivage dans la liste. Cependant, les conversations de messagerie instantanée ou de conférence web (messagerie) ne peuvent pas être archivées tant que le service n’a pas été également configuré pour le serveur exécutant l’archivage.</span><span class="sxs-lookup"><span data-stu-id="62d59-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

