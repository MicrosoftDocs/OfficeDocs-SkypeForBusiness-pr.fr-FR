---
title: Ajouter un magasin fichiers de conversation permanente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: c77087520e51fffcad8c8341fe33103327e17799
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818674"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="0ec0d-104">Ajouter un magasin fichiers de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="0ec0d-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="0ec0d-p102">Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0ec0d-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0ec0d-107">Le partage de fichiers pour Skype Entreprise Server ne peut pas se trouver sur le serveur frontal Enterprise Edition, mais peut se trouver sur un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0ec0d-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0ec0d-108">Avant de créer le partage de fichiers, vous pouvez le définir dans le Générateur de topologie, mais vous devez créer le partage de fichiers à l’emplacement que vous définissez avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="0ec0d-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0ec0d-109">Lorsque vous ajoutez un serveur de conversation permanente ou un pool de serveurs de conversation permanente à votre topologie, le Générateur de topologie doit pouvoir configurer le magasin de fichiers et configurer des listes de contrôle d’accès discrétionnaire (DAC) sur le partage de fichiers à utiliser pour le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0ec0d-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="0ec0d-110">Pour cela, lorsque vous exécutez le Générateur de topologie pour publier la nouvelle topologie, vous devez être connecté avec un compte qui dispose des autorisations de contrôle complètes (lecture/écriture/modification) pour le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0ec0d-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0ec0d-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ec0d-111">See also</span></span>

[<span data-ttu-id="0ec0d-112">Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0ec0d-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="0ec0d-113">Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0ec0d-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="0ec0d-114">Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0ec0d-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="0ec0d-115">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0ec0d-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="0ec0d-116">Topology Basics for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0ec0d-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
