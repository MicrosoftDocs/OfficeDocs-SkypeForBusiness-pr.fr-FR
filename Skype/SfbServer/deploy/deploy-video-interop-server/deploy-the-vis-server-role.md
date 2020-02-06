---
title: Déploiement du rôle serveur sur Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Résumé : déploiement du rôle serveur d’interopérabilité vidéo (à) dans Skype entreprise Server.'
ms.openlocfilehash: 1fadab718a37dba2ffee5338d4dc898316b4d24d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798041"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="e495e-103">Déploiement du rôle serveur sur Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e495e-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="e495e-104">**Résumé :** Déploiement du rôle serveur d’interopérabilité de vidéo dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e495e-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="e495e-105">Pour configurer le service à l’aide du service sur le serveur que vous venez de créer dans le générateur de topologie, démarrez l’Assistant Déploiement de Skype entreprise, appuyez sur **installer ou mettre à jour le système Skype entreprise Server** et suivez les étapes de l’Assistant :</span><span class="sxs-lookup"><span data-stu-id="e495e-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="e495e-106">Sélectionnez **Installer le magasin de configurations local**.</span><span class="sxs-lookup"><span data-stu-id="e495e-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="e495e-107">Sélectionnez **configurer ou supprimer les composants Skype entreprise Server**.</span><span class="sxs-lookup"><span data-stu-id="e495e-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="e495e-108">Sélectionnez **Demander, installer ou assigner les certificats**.</span><span class="sxs-lookup"><span data-stu-id="e495e-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="e495e-109">Sélectionnez **Démarrer les services**.</span><span class="sxs-lookup"><span data-stu-id="e495e-109">Select **Start services**.</span></span>
    
<span data-ttu-id="e495e-110">The software for this service is now installed and running.</span><span class="sxs-lookup"><span data-stu-id="e495e-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="e495e-111">Vous pouvez ouvrir l’outil MMC services pour vérifier si le service **serveur vidéo Interop de Skype entreprise Server** s’exécute avec d’autres services Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e495e-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="e495e-112">Next, you must configure the VIS server or pool.</span><span class="sxs-lookup"><span data-stu-id="e495e-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="e495e-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e495e-113">See also</span></span>

[<span data-ttu-id="e495e-114">Configurer le serveur Video Interop dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e495e-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
