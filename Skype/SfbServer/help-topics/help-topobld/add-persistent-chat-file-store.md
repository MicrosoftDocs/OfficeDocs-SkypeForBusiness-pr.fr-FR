---
title: Ajouter un magasin de fichiers de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: f11443f8c10db35d5ffb8bfdbfc03d9826700b7c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820676"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="0b309-104">Ajouter un magasin de fichiers de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="0b309-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="0b309-p102">Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b309-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0b309-107">Le partage de fichiers pour Skype entreprise Server ne peut pas être localisé sur le serveur frontal Enterprise Edition, mais peut être localisé sur un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="0b309-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0b309-108">Avant de créer le partage de fichiers, vous pouvez le définir dans le générateur de topologie, mais vous devez créer le partage de fichiers à l’emplacement défini avant la publication de la topologie.</span><span class="sxs-lookup"><span data-stu-id="0b309-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0b309-109">Lorsque vous ajoutez un serveur de chat permanent ou un pool de serveurs de chat permanent à votre topologie, le générateur de topologie doit être en mesure de configurer le magasin de fichiers et de configurer les listes de contrôle d’accès discrétionnaire (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b309-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="0b309-110">À cet effet, lorsque vous exécutez le générateur de topologie pour publier la nouvelle topologie, vous devez être connecté avec un compte disposant d’autorisations de contrôle intégrales (lecture/écriture/modification) pour le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b309-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0b309-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b309-111">See also</span></span>

[<span data-ttu-id="0b309-112">Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0b309-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="0b309-113">Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0b309-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="0b309-114">Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0b309-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="0b309-115">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0b309-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="0b309-116">Concepts de base de topologie pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0b309-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
