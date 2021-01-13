---
title: Ajouter un magasin de fichiers du serveur d’archivage
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Pour activer l’archivage du contenu de messagerie instantanée et de conférence web (réunion), vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les copies de l’ensemble du contenu de conférence web (réunion). Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers d’archivage ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: a35bf3f7c1ef066aec1139ab2e886073ab65e23b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807144"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="1117b-104">Ajouter un magasin de fichiers du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="1117b-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="1117b-p102">Pour activer l’archivage du contenu de messagerie instantanée et de conférence web (réunion), vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les copies de l’ensemble du contenu de conférence web (réunion). Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers d’archivage ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1117b-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1117b-107">Avant de créer le partage de fichiers, vous pouvez le définir dans le Générateur de topologie, mais vous devez créer le partage de fichiers à l’emplacement défini avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="1117b-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="1117b-108">> Lorsque vous ajoutez un serveur d’archivage à votre topologie, le Générateur de topologie doit être en mesure de configurer le magasin de fichiers d’archivage et de configurer des listes de contrôle d’accès discrétionnaire (DAC) sur le partage de fichiers à utiliser pour le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1117b-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="1117b-109">Pour cela, lorsque vous exécutez le Générateur de topologie pour publier la nouvelle topologie, vous devez être connecté avec un compte qui dispose des autorisations de contrôle complètes (lecture/écriture/modification) pour le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1117b-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="1117b-110">Pour plus d’informations sur la [](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) prise en charge du stockage pour les partages de fichiers, voir La prise en charge du stockage de fichiers dans la documentation de prise en charge et SQL Server Données et [emplacement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) des fichiers journaux dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1117b-110">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="1117b-111">Pour plus d’informations sur la colocalisation du partage de fichiers, voir [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="1117b-111">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


