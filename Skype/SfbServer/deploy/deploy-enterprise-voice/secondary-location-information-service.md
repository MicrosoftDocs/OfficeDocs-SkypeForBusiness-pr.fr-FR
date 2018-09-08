---
title: Configurer un service informations d’emplacement secondaire dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurer une base de données source (SLS) emplacement secondaire pour E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: e811062bbec9e3b6caf368e010b751e496c1b305
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885121"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="54e75-103">Configurer un service informations d’emplacement secondaire dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="54e75-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="54e75-104">Configurer une base de données source (SLS) emplacement secondaire pour E9-1-1 dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="54e75-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="54e75-105">Skype pour Business Server fournit une interface de service web que vous pouvez utiliser pour faire pointer le service d’informations sur l’emplacement des bases de données Source d’emplacement secondaire (SLS).</span><span class="sxs-lookup"><span data-stu-id="54e75-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="54e75-106">L’interface du service web qui se connecte à la base de données SLS doit être conforme à WSDL du service informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="54e75-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="54e75-107">Si une base de données de l’emplacement et la base de données d’emplacements secondaires sont configurés, le service informations d’emplacement tout d’abord interroge la base de données d’emplacement et si aucune correspondance n’est trouvée, envoie la demande d’emplacement à partir du client à la base de données SLS.</span><span class="sxs-lookup"><span data-stu-id="54e75-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="54e75-108">Si l’emplacement existe dans le SLS, le service informations d’emplacement envoie ensuite l’emplacement sur le client.</span><span class="sxs-lookup"><span data-stu-id="54e75-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="54e75-109">Pour configurer une base de données d’emplacements secondaires</span><span class="sxs-lookup"><span data-stu-id="54e75-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="54e75-110">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="54e75-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="54e75-111">Exécutez l’applet de commande ci-dessous pour configurer l’URL de l’emplacement de la base de données d’emplacements secondaires.</span><span class="sxs-lookup"><span data-stu-id="54e75-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="54e75-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54e75-112">See also</span></span>

[<span data-ttu-id="54e75-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="54e75-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

