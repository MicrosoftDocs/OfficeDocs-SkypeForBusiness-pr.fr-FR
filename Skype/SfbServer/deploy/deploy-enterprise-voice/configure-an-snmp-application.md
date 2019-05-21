---
title: Configurer une application SNMP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurer une application SNMP pour qu’elle fonctionne avec E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303417"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="ff56f-103">Configurer une application SNMP dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ff56f-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="ff56f-104">Configurer une application SNMP pour qu’elle fonctionne avec E9-1-1 dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="ff56f-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="ff56f-105">Skype entreprise Server inclut une interface de service Web standard que vous pouvez utiliser pour connecter le service d’information d’emplacement aux applications SNMP (simple Network Management Protocol) qui correspondent aux adresses MAC et aux informations sur les ports et aux commutateurs.</span><span class="sxs-lookup"><span data-stu-id="ff56f-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="ff56f-106">Si une application SNMP est installée et que le service des informations de géolocalisation ne trouve pas de correspondance dans la base de données de localisation, le service d’information d’emplacement interroge automatiquement l’application à l’aide de l’adresse MAC fournie par le client.</span><span class="sxs-lookup"><span data-stu-id="ff56f-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="ff56f-107">Le service d’information d’emplacement utilise alors le port et les informations de commutation renvoyées par l’application SNMP pour interroger de nouveau la base de données d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="ff56f-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff56f-108">Les adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8.</span><span class="sxs-lookup"><span data-stu-id="ff56f-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="ff56f-109">Pour configurer l’URL de l’application SNMP</span><span class="sxs-lookup"><span data-stu-id="ff56f-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="ff56f-110">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ff56f-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ff56f-111">Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP.</span><span class="sxs-lookup"><span data-stu-id="ff56f-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="ff56f-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff56f-112">See also</span></span>

[<span data-ttu-id="ff56f-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff56f-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

