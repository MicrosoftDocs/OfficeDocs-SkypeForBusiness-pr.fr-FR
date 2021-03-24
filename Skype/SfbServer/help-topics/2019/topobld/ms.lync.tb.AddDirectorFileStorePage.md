---
title: Ajouter un magasin de fichiers pour les directeurs
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: Vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les directeurs. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: 56fb33653f2f463e9b336ae447a1c665680ed6df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100140"
---
# <a name="add-director-file-store"></a><span data-ttu-id="0f0f0-104">Ajouter un magasin de fichiers pour les directeurs</span><span class="sxs-lookup"><span data-stu-id="0f0f0-104">Add Director File Store</span></span>

<span data-ttu-id="0f0f0-105">Vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les directeurs.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-105">You must specify a file share to be used as the file store for Directors.</span></span> <span data-ttu-id="0f0f0-106">Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-106">You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f0f0-p103">Lorsque vous ajoutez des directeurs à une topologie, la publication de la topologie a besoin d’un accès approprié pour installer le magasin de fichiers et configurer des listes de contrôle d’accès discrétionnaire (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers. Pour cela, lorsque vous exécutez le Générateur de topologies et publiez la nouvelle topologie, vous devez être connecté avec un compte qui dispose des autorisations de contrôle complètes (lecture/écriture/modification) pour le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="0f0f0-109">Pour plus d’informations sur la [](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) prise en charge du stockage pour les partages de fichiers, voir La prise en charge du stockage de fichiers dans la documentation de prise en charge et SQL Server Données et [emplacement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) des fichiers journaux dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-109">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="0f0f0-110">Pour plus d’informations sur la colocalisation du partage de fichiers, voir [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-110">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span> <span data-ttu-id="0f0f0-111">Pour plus d’informations sur la conception de la topologie pour les directeurs, voir [Définir](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) un directeur unique dans le Générateur de topologies dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0f0f0-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) in the Deployment documentation.</span></span>