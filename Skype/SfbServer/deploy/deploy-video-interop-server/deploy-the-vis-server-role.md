---
title: Déployer le rôle de serveur VIS Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Résumé : Déployez le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server.'
ms.openlocfilehash: b52980a727ad0ce13e45e2c833c971598afafa1e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993442"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="9f2d5-103">Déployer le rôle de serveur VIS Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9f2d5-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="9f2d5-104">**Résumé :** Déployer le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9f2d5-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="9f2d5-105">Pour configurer le service de rapport sur le serveur créé dans le Générateur de topologie, démarrer le Skype pour l’Assistant de déploiement de serveur d’entreprise, appuyez sur **installer ou mise à jour Skype pour Business Server System** et suivez ces étapes dans l’Assistant :</span><span class="sxs-lookup"><span data-stu-id="9f2d5-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="9f2d5-106">Sélectionnez **Installer le magasin de configurations local**.</span><span class="sxs-lookup"><span data-stu-id="9f2d5-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="9f2d5-107">Sélectionnez **installer ou supprimer des Skype pour les composants de serveur d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="9f2d5-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="9f2d5-108">Sélectionnez **Demander, installer ou assigner les certificats**.</span><span class="sxs-lookup"><span data-stu-id="9f2d5-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="9f2d5-109">Sélectionnez **Démarrer les services**.</span><span class="sxs-lookup"><span data-stu-id="9f2d5-109">Select **Start services**.</span></span>
    
<span data-ttu-id="9f2d5-110">Le logiciel de ce service est maintenant installé et opérationnel.</span><span class="sxs-lookup"><span data-stu-id="9f2d5-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="9f2d5-111">Vous pouvez ouvrir l’outil de mmc Services pour voir si le service **Skype pour Business interopérabilité vidéo Server** est en cours d’exécution ainsi que d’autres Skype pour les services Business Server.</span><span class="sxs-lookup"><span data-stu-id="9f2d5-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="9f2d5-112">Vous devez ensuite configurer le serveur ou le pool VIS.</span><span class="sxs-lookup"><span data-stu-id="9f2d5-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="9f2d5-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f2d5-113">See also</span></span>

[<span data-ttu-id="9f2d5-114">Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9f2d5-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)