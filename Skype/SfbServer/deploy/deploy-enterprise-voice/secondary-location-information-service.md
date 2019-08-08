---
title: Configurer un service d’information d’emplacement secondaire dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurez une base de données de source d’emplacement secondaire (SLS) pour E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 47dd4015cde79536323cee3edc04ed546459a3f0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240164"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="eac20-103">Configurer un service d’information d’emplacement secondaire dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="eac20-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="eac20-104">Configurez une base de données de source d’emplacement secondaire (SLS) pour E9-1-1 dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="eac20-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="eac20-105">Skype entreprise Server fournit une interface de service Web que vous pouvez utiliser pour faire pointer le service d’information d’emplacement vers une base de données de source d’emplacement secondaire (SLS).</span><span class="sxs-lookup"><span data-stu-id="eac20-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="eac20-106">L’interface de service Web qui se connecte à la base de données SLS doit être conforme au WSDL.</span><span class="sxs-lookup"><span data-stu-id="eac20-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="eac20-107">S’il s’agit d’une base de données d’emplacement et d’une base de données d’emplacement secondaire configurées, le service des informations d’emplacement interroge d’abord la base de données de localisation, et si aucune correspondance n’est trouvée, envoie la demande d’emplacement du client vers la base de données SLS.</span><span class="sxs-lookup"><span data-stu-id="eac20-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="eac20-108">Si l’emplacement existe dans le dossier SLS, le service d’information sur l’emplacement est alors renvoyé à l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="eac20-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="eac20-109">Pour configurer une base de données d’emplacements secondaires</span><span class="sxs-lookup"><span data-stu-id="eac20-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="eac20-110">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="eac20-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="eac20-111">Exécutez l’applet de commande ci-dessous pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.</span><span class="sxs-lookup"><span data-stu-id="eac20-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="eac20-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eac20-112">See also</span></span>

[<span data-ttu-id="eac20-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="eac20-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

