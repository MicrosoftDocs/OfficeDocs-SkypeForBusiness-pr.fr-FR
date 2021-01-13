---
title: Déployer le rôle serveur VIS dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Résumé : Déployez le rôle vis (Video Interop Server) dans Skype Entreprise Server.'
ms.openlocfilehash: 773e2ddf790aa1b6c36ff6926d8bc4d16ea613f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801964"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="e1e7b-103">Déployer le rôle serveur VIS dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e1e7b-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="e1e7b-104">**Résumé :** Déployez le rôle VIS (Video Interop Server) dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="e1e7b-105">Pour configurer le service VIS sur le serveur qui vient d’être créé dans le Générateur de topologie, démarrez l’Assistant Déploiement de Skype Entreprise Server, appuyez sur Installer ou mettre à jour le système Skype Entreprise **Server** et suivez les étapes suivantes dans l’Assistant :</span><span class="sxs-lookup"><span data-stu-id="e1e7b-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="e1e7b-106">Sélectionnez **Installer le magasin de configurations local.**</span><span class="sxs-lookup"><span data-stu-id="e1e7b-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="e1e7b-107">Sélectionnez **Le programme d’installation ou supprimez les composants Skype Entreprise Server.**</span><span class="sxs-lookup"><span data-stu-id="e1e7b-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="e1e7b-108">Select **Request, Install or Assign Certificates**.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="e1e7b-109">Sélectionnez **Démarrer les services.**</span><span class="sxs-lookup"><span data-stu-id="e1e7b-109">Select **Start services**.</span></span>
    
<span data-ttu-id="e1e7b-110">Le logiciel de ce service est maintenant installé et en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="e1e7b-111">Vous pouvez ouvrir l’outil MMC Services pour voir si le service **Skype Entreprise Server Video Interop Server** est en cours d’exécution avec d’autres services Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="e1e7b-112">Ensuite, vous devez configurer le serveur VIS ou le pool.</span><span class="sxs-lookup"><span data-stu-id="e1e7b-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="e1e7b-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e1e7b-113">See also</span></span>

[<span data-ttu-id="e1e7b-114">Configurer le serveur d’opation vidéo dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e1e7b-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
