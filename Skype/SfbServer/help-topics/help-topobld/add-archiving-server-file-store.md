---
title: Ajouter un magasin de fichiers du serveur d’archivage
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Pour activer l’archivage du contenu de messagerie instantanée et de conférence web (réunion), vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les copies de l’ensemble du contenu de conférence web (réunion). Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers d’archivage ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: 99527455af38211ab788676b1072069924da9935
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304925"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="f61dd-104">Ajouter un magasin de fichiers du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="f61dd-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="f61dd-p102">Pour activer l’archivage du contenu de messagerie instantanée et de conférence web (réunion), vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les copies de l’ensemble du contenu de conférence web (réunion). Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers d’archivage ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f61dd-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f61dd-107">Avant de créer le partage de fichiers, vous pouvez le définir dans le générateur de topologie, mais vous devez créer le partage de fichiers à l’emplacement défini avant la publication de la topologie.</span><span class="sxs-lookup"><span data-stu-id="f61dd-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="f61dd-108">> lors de l’ajout d’un serveur d’archivage à votre topologie, le générateur de topologie doit être en mesure de configurer le stockage des fichiers d’archivage et de configurer les listes de contrôle d’accès discrétionnaire (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f61dd-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="f61dd-109">À cet effet, lorsque vous exécutez le générateur de topologie pour publier la nouvelle topologie, vous devez être connecté avec un compte disposant d’autorisations de contrôle intégrales (lecture/écriture/modification) pour le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f61dd-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="f61dd-p104">Pour plus d’informations sur la prise en charge du stockage pour les partages de fichiers, reportez-vous à la rubrique [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) de la documentation de prise en charge et à la rubrique [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) de la documentation de déploiement. Pour plus d’informations sur la colocalisation du partage de fichiers, reportez-vous à la rubrique [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) de la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f61dd-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


