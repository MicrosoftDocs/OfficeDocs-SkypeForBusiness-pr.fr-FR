---
title: Déploiement du rôle de serveur d’interopérabilité vidéo (VIS) dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Résumé : Déployer le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 4df688fa3c94f287269297ee895db192c1b924ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server-2015"></a><span data-ttu-id="105ff-103">Déploiement du rôle de serveur d’interopérabilité vidéo (VIS) dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="105ff-103">Deploy the VIS server role in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="105ff-104">**Résumé :** Déployer le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="105ff-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="105ff-105">Pour configurer le service de rapport sur le serveur créé dans le Générateur de topologies, démarrer le Skype pour l’Assistant de déploiement de serveur d’entreprise, appuyez sur **installer ou Skype de mise à jour pour système de serveur d’entreprise** et suivez ces étapes dans l’Assistant :</span><span class="sxs-lookup"><span data-stu-id="105ff-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="105ff-106">Sélectionnez **Installer le magasin de configurations local**.</span><span class="sxs-lookup"><span data-stu-id="105ff-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="105ff-107">Sélectionnez **installer ou supprimer Skype pour les composants de serveur d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="105ff-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="105ff-108">Sélectionnez **Demander, installer ou assigner les certificats**.</span><span class="sxs-lookup"><span data-stu-id="105ff-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="105ff-109">Sélectionnez **Démarrer les services**.</span><span class="sxs-lookup"><span data-stu-id="105ff-109">Select **Start services**.</span></span>
    
<span data-ttu-id="105ff-110">Le logiciel de ce service est maintenant installé et opérationnel.</span><span class="sxs-lookup"><span data-stu-id="105ff-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="105ff-111">Vous pouvez ouvrir l’outil mmc Services pour voir si le service **Skype pour Business Server vidéo Interop Server** est exécuté en même temps que les autre Skype pour les services de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="105ff-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="105ff-112">Vous devez ensuite configurer le serveur ou le pool VIS.</span><span class="sxs-lookup"><span data-stu-id="105ff-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="105ff-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="105ff-113">See also</span></span>

#### 

[<span data-ttu-id="105ff-114">Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="105ff-114">Configure the Video Interop Server in Skype for Business Server 2015</span></span>](configure-the-vis.md)

