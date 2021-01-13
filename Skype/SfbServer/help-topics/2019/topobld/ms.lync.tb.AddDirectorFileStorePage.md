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
ms.openlocfilehash: f134d561a948dbdb89ce655d59e5d5fc205bcbf4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811884"
---
# <a name="add-director-file-store"></a><span data-ttu-id="70a16-104">Ajouter un magasin de fichiers pour les directeurs</span><span class="sxs-lookup"><span data-stu-id="70a16-104">Add Director File Store</span></span>

<span data-ttu-id="70a16-105">Vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les directeurs.</span><span class="sxs-lookup"><span data-stu-id="70a16-105">You must specify a file share to be used as the file store for Directors.</span></span> <span data-ttu-id="70a16-106">Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="70a16-106">You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70a16-p103">Lorsque vous ajoutez des directeurs à une topologie, la publication de la topologie a besoin d’un accès approprié pour installer le magasin de fichiers et configurer des listes de contrôle d’accès discrétionnaire (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers. Pour cela, lorsque vous exécutez le Générateur de topologies et publiez la nouvelle topologie, vous devez être connecté avec un compte qui dispose des autorisations de contrôle complètes (lecture/écriture/modification) pour le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="70a16-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="70a16-109">Pour plus d’informations sur la [](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) prise en charge du stockage pour les partages de fichiers, voir La prise en charge du stockage de fichiers dans la documentation de prise en charge et SQL Server Données et [emplacement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) des fichiers journaux dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="70a16-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="70a16-110">Pour plus d’informations sur la colocalisation du partage de fichiers, voir [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="70a16-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="70a16-111">Pour plus d’informations sur la conception de la topologie pour les directeurs, voir [Définir](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) un directeur unique dans le Générateur de topologies dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="70a16-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


